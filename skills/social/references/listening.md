# Social listening & triage d'engagement

Comment faire remonter les bons posts à engager chaque jour — au lieu de scroller au hasard. L'objectif est une liste courte et scorable (« voici vos 10 meilleurs posts à commenter ») plutôt qu'un feed ouvert.

## Sommaire
- Quand utiliser ceci
- La boucle de triage quotidienne
- Grille de scoring
- Paliers de qualité de commentaire
- Sources & outillage léger (recettes curl)
- Notes par plateforme
- Workflows courants

---

## Quand utiliser ceci

Utiliser le listening quand l'objectif est de **commenter et créer des relations**, pas de poster. Demandes typiques :
- « Donne-moi les 10 meilleurs posts à commenter aujourd'hui »
- « Qui se plaint de [concurrent] en ce moment ? »
- « Trouve des gens qui demandent un outil comme le mien »
- « Fais remonter les posts de mes 20 comptes cibles des dernières 24 h »
- « C'est quoi la conversation autour de [sujet] cette semaine ? »

Si l'utilisateur veut **créer** du contenu, utiliser le reste du skill social. Le listening alimente la création (il fait remonter des angles, du langage, des objections), mais la sortie est différente.

---

## La boucle de triage quotidienne

Une boucle reproductible de 20 minutes que l'utilisateur (ou vous, pour son compte) peut faire tourner chaque matin.

1. **Extraire** — récupérer les nouveaux posts des sources définies (comptes cibles, mots-clés, subreddits, hashtags). Voir [outillage](#sources--light-tooling-curl-recipes).
2. **Filtrer** — écarter tout ce qui a plus de 24 h, à faible signal, ou hors sujet.
3. **Scorer** — appliquer la [grille](#scoring-rubric). Garder le top 10.
4. **Rédiger** — pour chacun, rédiger un commentaire adapté au palier du post.
5. **Poster** — l'utilisateur révise, édite, poste. Marquer ceux qui sont réellement passés en ligne.
6. **Logger** — tracer ce que vous avez commenté et ce qui a eu des réponses. C'est votre jeu de données de boucle d'engagement.

Format de sortie que Claude doit produire :

```
TOP 10 POSTS — 2026-06-05

1. [Score 9/10] @author — LinkedIn — il y a 2 h
   "We just rolled out X and the team is loving it…"
   Pourquoi : adéquation ICP (SaaS B2B, 50–200 employés), signal d'intention d'achat
   Commentaire suggéré : [brouillon]
   Lien : https://…
```

---

## Grille de scoring

Scorer chaque post de 1 à 10 sur cinq dimensions, puis additionner et classer.

| Dimension | Ce qu'elle mesure | Poids |
|-----------|------------------|--------|
| **Adéquation ICP** | L'auteur est-il votre client/influenceur cible ? | 2x |
| **Signal d'intention** | Exprime-t-il un problème, une demande, ou compare-t-il ? | 2x |
| **Potentiel de portée** | Le post prend-il (likes/commentaires en hausse) ? | 1x |
| **Opportunité de commentaire** | Pouvez-vous dire quelque chose de vraiment utile, pas générique ? | 2x |
| **Récence** | Posté dans les 1–4 dernières heures (les commentaires précoces gagnent, surtout sur LinkedIn) | 1x |

**Exemples de signaux d'intention (à forte valeur) :**
- « Looking for a tool that does X »
- « Why is [category] so painful? »
- « We just switched from [competitor] because… »
- « Anyone use [competitor] — is it worth it? »
- Une plainte au sujet d'un concurrent connu

**Écarter si l'un de ces points est vrai :**
- L'auteur n'est pas ICP et n'est pas un influenceur
- Le post a >24 h et a déjà 50+ commentaires (votre commentaire est noyé)
- Post motivationnel générique/AI-slop
- Thread d'autopromotion où les commentaires n'ont pas de portée
- Vous ne pouvez rien ajouter au-delà de « Super post ! »

---

## Paliers de qualité de commentaire

Adapter le commentaire au post. Ne pas gâcher un brouillon de palier 1 sur une opportunité de palier 3.

**Palier 1 — Constructeur de relation (comptes cibles, ICP, forte intention)**
- Ajouter un insight spécifique ou un contre-exemple
- Référencer votre propre expérience avec des spécificités (chiffres, noms, résultats)
- Poser une question de suivi pertinente qui invite à répondre
- Longueur : 2–4 phrases, sans lien

**Palier 2 — Coup de visibilité (post à forte portée, sujet adjacent)**
- Ajouter un insight tranchant en une phrase
- Pattern : « D'accord — et ce que la plupart ratent, c'est [X] »
- Longueur : 1–2 phrases

**Palier 3 — Touche légère (entretien de relation)**
- Réaction spécifique, pas « J'adore »
- Citer une phrase précise et y réagir
- Longueur : 1 phrase

**Jamais :** « Super post ! », emoji seul, « +1 », les tics LinkedIn du genre « This is gold 🔥 »

---

## Sources & outillage léger (recettes curl)

Ce sont des endpoints JSON publics — aucune auth nécessaire. Les faire tourner depuis bash, piper vers `jq`, et Claude peut parser la sortie pour scorer et rédiger des commentaires.

**Requiert :** `jq` (la plupart des recettes) et `xmllint` (RSS uniquement). Installer une fois :
```bash
# macOS
brew install jq
# xmllint est livré avec macOS ; sur Linux : apt install libxml2-utils
```

### Reddit (gratuit, scriptable)

**Nouveaux posts dans un subreddit :**
```bash
curl -s -A "listening/1.0" \
  "https://www.reddit.com/r/SaaS/new.json?limit=25" \
  | jq '.data.children[].data | {title, author, url: ("https://reddit.com"+.permalink), score, num_comments, created_utc, selftext: (.selftext | .[0:300])}'
```

**Recherche sur tout Reddit par mot-clé (dernier jour, trié par nouveau) :**
```bash
curl -s -A "listening/1.0" \
  "https://www.reddit.com/search.json?q=KEYWORD&sort=new&t=day&limit=25" \
  | jq '.data.children[].data | {subreddit, title, url: ("https://reddit.com"+.permalink), author, score, created_utc}'
```

Remplacer `KEYWORD` par des choses comme `"alternative to notion"`, `"recommend a crm"`, les noms de vos concurrents, ou votre propre marque pour les mentions. Utiliser des guillemets autour des expressions de plusieurs mots.

### Hacker News (recherche Algolia)

**Histoires récentes mentionnant un mot-clé (dernières 24 h) :**
```bash
SINCE=$(($(date +%s) - 86400))
curl -s "https://hn.algolia.com/api/v1/search_by_date?query=KEYWORD&tags=story&numericFilters=created_at_i>${SINCE}" \
  | jq '.hits[] | {title, url, author, points, num_comments, created_at, story_id: .objectID, hn_url: ("https://news.ycombinator.com/item?id="+.objectID)}'
```

**Commentaires récents mentionnant un mot-clé :**
```bash
curl -s "https://hn.algolia.com/api/v1/search_by_date?query=KEYWORD&tags=comment&numericFilters=created_at_i>${SINCE}" \
  | jq '.hits[] | {author, comment_text, story_title, hn_url: ("https://news.ycombinator.com/item?id="+.objectID)}'
```

### Bluesky (gratuit, API publique)

**Rechercher des posts par mot-clé :**
```bash
curl -s "https://public.api.bsky.app/xrpc/app.bsky.feed.searchPosts?q=KEYWORD&limit=25&sort=latest" \
  | jq '.posts[] | {author: .author.handle, text: .record.text, likes: .likeCount, replies: .replyCount, url: ("https://bsky.app/profile/"+.author.handle+"/post/"+(.uri | split("/") | last))}'
```

### RSS pour blogs, podcasts, chaînes YouTube

Pour les comptes cibles qui publient en RSS (la plupart des blogs, toutes les chaînes YouTube) :
```bash
# Feed de chaîne YouTube (remplacer CHANNEL_ID)
curl -s "https://www.youtube.com/feeds/videos.xml?channel_id=CHANNEL_ID"

# Feed de blog générique
curl -s "https://example.com/feed/" | xmllint --xpath "//item[position()<6]" - 2>/dev/null
```

### LinkedIn & X — utiliser le navigateur

LinkedIn et X n'exposent pas d'API publiques utiles, mais vous pouvez piloter une vraie session navigateur. **dev-browser** (MCP, déjà dans la configuration globale) et **Playwright** maintiennent tous deux un état persistant — connectez-vous une fois, la session reste active, Claude peut naviguer dans le feed authentifié.

**Workflow dev-browser (préféré — déjà câblé) :**
1. L'utilisateur se connecte une fois à LinkedIn / X dans la session dev-browser
2. Claude navigue vers une URL cible (feed, profil, recherche sauvegardée, hashtag)
3. Claude lit l'arbre d'accessibilité / le texte de la page, extrait les posts
4. Claude score à l'aide de la [grille](#scoring-rubric) et rédige des commentaires
5. L'utilisateur révise et poste manuellement (ne pas auto-poster — enjeu fort, risque de détection de bot)

**URL utiles à donner à dev-browser :**

| Pattern d'URL | Ce qu'il affiche |
|-------------|---------------|
| `linkedin.com/in/HANDLE/recent-activity/all/` | Les posts récents d'un compte cible |
| `linkedin.com/feed/hashtag/TOPIC/` | Feed de hashtag |
| `linkedin.com/feed/` | Votre feed principal (algorithmique — moins utile pour le triage) |
| `x.com/HANDLE` | Le profil d'un compte cible |
| `x.com/search?q=QUERY&f=live` | Recherche en temps réel (utiliser `f=live` pour le chronologique) |
| `x.com/i/lists/LIST_ID` | Une liste curatée — idéale pour les comptes cibles |

**Astuces :**
- Sur X, construire une liste privée de comptes cibles et utiliser l'URL de la liste. Bien plus propre que le feed algorithmique.
- L'URL `/recent-activity/all/` de LinkedIn est la façon la plus propre de voir les posts d'une personne sans l'algorithme.
- Pour les deux plateformes, scroller de façon programmatique (dev-browser le permet) pour charger plus de posts avant l'extraction.

**Alternatives payantes si vous ne voulez pas piloter un navigateur :**

| Plateforme | Outils |
|----------|-------|
| LinkedIn | Sales Navigator (recherches sauvegardées), Taplio (engagement) |
| X | TweetDeck/X Pro (colonnes sauvegardées), Typefully, Taplio, Tweet Hunter |

**Toujours fermé (pas de bon chemin) :**
- Instagram & TikTok — API fermées, l'automatisation de navigateur est détectable et risquée. Utiliser les recherches sauvegardées / suivis de hashtags natifs.

---

## Notes par plateforme

### LinkedIn
- **Browser-driven** (dev-browser avec session persistante) — voir [LinkedIn & X — utiliser le navigateur](#linkedin--x--use-the-browser)
- **Les commentaires de la première heure comptent le plus** — l'algorithme pondère lourdement l'engagement précoce. Prioriser les posts de <2 h des comptes cibles.
- Les commentaires de 5+ mots ont plus de portée que les réactions
- Répondre à d'autres commentateurs peut vous placer devant leur réseau
- Taguer l'auteur dans votre réponse uniquement si ça ajoute du contexte

### Twitter/X
- **Browser-driven** (dev-browser) — construire une liste privée de comptes cibles et pointer dev-browser sur l'URL de la liste
- Répondre dans les 30 premières minutes pour une portée max sur les gros comptes
- Le quote-tweet > la réponse quand vous ajoutez une valeur substantielle
- Threader votre réponse (multi-tweets) signale l'effort
- Ne pas s'acharner dans les attaques — relations > clout

### Reddit
- Lire les règles du subreddit avant de commenter (certains bannissent l'autopromotion d'office)
- Gagner du karma dans le sub avant de linker quoi que ce soit que vous possédez
- Les réponses longues et spécifiques gagnent. Les AMA et threads « help me decide » sont en or
- Ne jamais mener avec votre produit — répondre à la question d'abord

### Hacker News
- La barre de qualité des commentaires est haute ; le low-effort se fait downvoter vite
- Les fondateurs qui commentent sur des threads à propos de leur produit sont les bienvenus si vous êtes transparent
- Rechercher les discussions passées de votre catégorie — ce sont souvent des mines d'or dormantes

### Bluesky
- Volume plus petit mais fort ratio engagement/follower
- Les communautés tech et indie-hacker sont actives
- Les feeds personnalisés (comme le feed « Following » + feeds de sujets de Bluesky) remplacent la recherche algorithmique

---

## Workflows courants

### « Donne-moi mes 10 meilleurs posts à commenter aujourd'hui »
1. Extraire de : RSS/recherches sauvegardées des comptes cibles + Reddit (subs pertinents) + HN (dernières 24 h)
2. Scorer avec la [grille](#scoring-rubric)
3. Produire le top 10 avec commentaires suggérés

### « Trouve des gens qui se plaignent de [concurrent] »
1. Recherche Reddit : `"competitor name" -site:competitor.com` triée par nouveau
2. Recherche de commentaires HN pour le nom du concurrent
3. Recherche Bluesky pour le handle/nom du concurrent
4. Scorer par signal d'intention (élevé si langage de migration : « moving from », « alternatives to », « frustrated with »)

### « Fais remonter les mentions de marque de la dernière semaine »
1. Recherche Reddit pour le nom de marque
2. Recherche HN (histoires + commentaires) pour le nom de marque
3. Recherche Bluesky pour le nom de marque + handle
4. Produire sous la forme : réponse nécessaire (oui/non), ton (positif/négatif/neutre), réponse suggérée

### « Trouve les posts de comptes cibles que j'ai ratés »
1. Maintenir une liste de comptes cibles avec leur RSS / usernames Reddit / handles Bluesky
2. Récupérer les posts récents de chaque source
3. Filtrer aux dernières 24 h, produire trié par score

---

## Mettre en place la liste de sources

L'utilisateur devrait maintenir une liste de sources quelque part de persistant, à `.agents/listening-sources.md` (ou `.claude/listening-sources.md`). Claude la lit lors de l'exécution de la boucle quotidienne.

**Un template prêt à remplir se trouve à [listening-sources-template.md](listening-sources-template.md).** Copiez-le dans le projet et éditez. Le chemin source dépend de la façon dont le skill a été installé :

```bash
# Installation plugin / marketplace (la plus courante) :
cp .agents/skills/social/references/listening-sources-template.md .agents/listening-sources.md
# Installation .claude/ :
cp .claude/skills/social/references/listening-sources-template.md .agents/listening-sources.md
# En travaillant dans le repo marketingskills :
cp skills/social/references/listening-sources-template.md .agents/listening-sources.md
```

Le template couvre : marque/catégorie, ICP (pour le scoring), comptes cibles par plateforme, mots-clés d'intention, subreddits, URL de recherches sauvegardées, et une liste de comptes à ne pas engager.
