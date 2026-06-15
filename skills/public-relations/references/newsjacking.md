# Newsjacking — Workflow de PR réactive

Injecter votre POV dans une story déjà tendance. Bien fait : distribution gratuite sur une vague d'attention. Mal fait : cringe au mieux, dégât de marque au pire.

## Sommaire
- Quand le newsjacking marche (et quand non)
- La boucle détecter → scorer → angle → pitcher
- Grille de scoring de la valeur d'actualité
- Bibliothèque d'angles de story
- Vitesse : la seule chose qui compte
- Sources & outillage
- Modes d'échec

---

## Quand le newsjacking marche

- **Actu tech/réglementaire dans votre catégorie** — nouvelle loi, lancement d'une nouvelle plateforme, pivot d'un concurrent, grosse acquisition
- **Sortie de données sectorielles** — un rapport majeur sort, vous avez une prise plus tranchée ou des données contradictoires
- **Conversation publique** — un débat ou une controverse où votre expertise est réellement pertinente
- **Moments saisonniers/cycliques** — saison des résultats, bilans de fin d'année, semaines de conférences

## Quand zapper

- **Tragédies, accidents, décès** — sans exception. Ne le faites pas.
- **Stories à charge politique** sauf si votre marque prend explicitement des positions politiques
- **Vous n'avez aucune expertise réelle** dans le domaine
- **La fenêtre est déjà fermée** — si une story a 48 h+ et que vous n'étiez pas premier, vous êtes en retard
- **L'angle est « on a un produit pour ça »** — c'est du marketing, pas du journalisme

---

## La boucle

Un workflow reproductible que Claude peut dérouler à la demande ou quotidiennement.

1. **Détecter** — faire remonter les stories tendance de votre catégorie (voir [Sources & outillage](#sources--outillage))
2. **Scorer** — appliquer la [grille de valeur d'actualité](#grille-de-scoring-de-la-valeur-dactualité) ; éliminer tout ce qui est sous le seuil
3. **Angle** — générer 2–3 angles par story avec la [bibliothèque d'angles](#bibliothèque-dangles-de-story)
4. **Valider** — vérifier le bon sens : avez-vous réellement l'expertise/les données pour soutenir cet angle ?
5. **Pitcher** — rédiger un pitch serré à 3–5 journalistes qui couvrent ce beat (voir [journalist-pitching.md](journalist-pitching.md))
6. **Publier** — publier aussi sur votre blog, LinkedIn, X — ça construit la trace que les journalistes vérifient avant de vous citer

Format de sortie que Claude doit produire :

```
NEWSJACK CANDIDATE — 2026-06-10

Story: "EU passes AI Act amendment requiring agent registration"
Source: TechCrunch, 3h ago
Score: 8/10 (high relevance, fresh, you have proprietary data)

Angles:
1. Data hot take: "Our analysis of 12,000 agent deployments shows 73% would fail this requirement"
2. Contrarian: "Why the registration rule will hurt safety, not improve it"
3. Customer story: "How [customer] is preparing — interview offer"

Recommended: #1 (you have unique data, strongest hook)
Pitch draft: [see journalist-pitching.md for template]
Target journalists: [list with rationale]
```

---

## Grille de scoring de la valeur d'actualité

Scorer chaque candidat de 1 à 10 sur cinq dimensions, multiplier par le poids, puis sommer. Max possible : 80 (10 × le total des poids de 8x).

| Dimension | Ce qu'elle mesure | Poids |
|-----------|------------------|--------|
| **Actualité** | Story <24 h ? Fenêtre encore ouverte ? | 2x |
| **Pertinence** | Réellement dans votre domaine d'expertise ? | 2x |
| **Unicité de l'angle** | Pouvez-vous dire quelque chose que personne d'autre ne dit ? | 2x |
| **Autorité** | Avez-vous des données, des clients ou de l'expérience pour le soutenir ? | 1x |
| **Potentiel de portée** | Cette story va-t-elle continuer à grandir ou a-t-elle plafonné ? | 1x |

**Seuil :** total pondéré ≥ 50/80. En dessous, zappez.

**Auto-disqualification si :**
- La story porte sur quelque chose de tragique
- Votre angle est « je ne suis pas d'accord » sans rien pour le soutenir
- Vous n'avez pas vraiment formé d'opinion — vous voulez juste être cité

---

## Bibliothèque d'angles de story

Utilisez ces templates pour générer des angles vite.

### 1. Data hot take
*« Nous avons analysé [N] [choses] après [événement]. Voici ce que nous avons trouvé. »*

Idéal quand vous avez des données propriétaires. Le journaliste obtient une stat, vous obtenez la citation.

### 2. Contrarian
*« Tout le monde dit [prise populaire]. Voici pourquoi ils ont tort. »*

Idéal quand vous pouvez défendre la position avec du concret. Faible quand c'est juste du contrarianisme pour attirer l'attention.

### 3. « On l'avait prédit »
*« Il y a six mois, nous écrivions [chose] — voici ce qui se passe maintenant et la suite. »*

Idéal quand vous l'avez réellement prédit. Mortel pour votre crédibilité si ce n'est pas le cas.

### 4. Impact client
*« Voici un [type de client] directement affecté. On peut vous mettre en contact. »*

Idéal pour le B2B. Les reporters adorent les clients nominatifs prêts à parler.

### 5. Explication d'initié
*« Cette story est compliquée. Voici ce qui se passe réellement. »*

Idéal quand la plupart des couvertures ratent la nuance. Vous n'argumentez pas — vous éduquez.

### 6. Connecteur de tendance
*« Ce n'est pas isolé — ça fait partie d'un shift plus large qu'on observe dans [pattern]. »*

Idéal quand vous avez plusieurs données ou exemples à relier.

### 7. POV de fondateur
*« En tant que personne qui construit dans cet espace depuis [X ans], voici la partie que la plupart des gens ratent. »*

Idéal pour les tribunes / op-eds. Faible comme pitch de soundbite.

---

## Vitesse : la seule chose qui compte

Le newsjacking se périme vite. Fenêtres approximatives :

| Type de story | Fenêtre effective |
|-----------|------------------|
| Breaking news tech | 4–12 heures |
| Réglementation / politique majeure | 24–48 heures |
| Rapport sectoriel / sortie de données | 24–72 heures |
| Annonce en conférence | Le jour même |
| Actu d'acquisition / levée de fonds | 12–24 heures |

**Implication :** si vous ne pouvez pas rédiger et envoyer dans la fenêtre, laissez tomber. Montez la boucle pour que détection → pitch prenne <2 heures.

---

## Sources & outillage

Réutilise l'outillage du workflow de listening du skill `social`. Même install : `brew install jq`.

### Google News RSS (sans auth)

```bash
# Replace QUERY with topic (use + for spaces, %22 for quotes)
curl -s "https://news.google.com/rss/search?q=QUERY&hl=en-US&gl=US&ceid=US:en" \
  | xmllint --xpath "//item[position()<11]" - 2>/dev/null
```

### Hacker News (Algolia) pour les stories tech

```bash
SINCE=$(($(date +%s) - 86400))
curl -s "https://hn.algolia.com/api/v1/search_by_date?query=QUERY&tags=story&numericFilters=created_at_i>${SINCE}" \
  | jq '.hits[] | {title, url, points, num_comments, created_at, hn_url: ("https://news.ycombinator.com/item?id="+.objectID)}'
```

### Reddit (pour les subs spécifiques à une catégorie)

```bash
curl -s -A "newsjack/1.0" \
  "https://www.reddit.com/r/SUBREDDIT/top.json?t=day&limit=15" \
  | jq '.data.children[].data | {title, url, score, num_comments, created_utc}'
```

### Recherche de journalistes (pilotée par navigateur)

Pour trouver *quels* journalistes couvrent la story en ce moment :
- **dev-browser** → recherche Google News pour la story → cliquer jusqu'aux articles → noter les signatures (bylines)
- Puis aller sur les profils X / LinkedIn / Muck Rack de ces journalistes pour confirmer le beat et la couverture récente

Voir aussi [journalist-pitching.md](journalist-pitching.md) pour le workflow de discovery complet.

### Liste de sources

Pour un monitoring reproductible, ajoutez une section « Newsjacking topics » à `.agents/listening-sources.md` (template dans les références du skill `social`) :

```markdown
## Newsjacking topics (Google News RSS)
- "AI agent regulation"
- "[your category] funding"
- "[your competitors] OR [adjacent competitors]"

## Industry data drops (RSS / manual)
- Pitchbook reports
- a16z state of [industry] reports
- [your category] benchmark reports
```

---

## Modes d'échec

Des choses qui ont mis fin à des carrières et des marques.

- **Tragedy-jacking** — le tweet Super Bowl 2013 d'Oreo a marché. La plupart des tentatives depuis, non. Périodes de guerre, catastrophes, décès : ne le faites pas.
- **Le forçage** — « Voici notre prise sur [story tendance] — en fait, ça parle de [notre produit]. » Les journalistes le voient instantanément.
- **La prise vide** — pitcher « on a une opinion » sans concret. Les journalistes ont besoin d'une ligne citable, pas de « on suit ça de près ».
- **Vitesse sans jugement** — être premier avec une mauvaise prise est pire qu'être en retard avec une bonne. Le gut check de 30 minutes « est-ce approprié pour la marque ? » existe pour une raison.
- **Pitcher le même angle à 50 journalistes** — ils se parlent. Pris une fois, vous perdez les relations.
- **Pas de suivi** — le pitch part, le journaliste répond en 20 minutes, le fondateur met 6 heures à répondre. La story passe à autre chose.

---

## Pratique complémentaire : la trace publique

Chaque pitch de newsjacking est plus fort si le journaliste peut trouver la preuve que vous réfléchissez à ça publiquement. Avant de pitcher :

1. Publier un court post (blog, LinkedIn, thread X) avec votre prise
2. Le référencer dans le pitch (« plus de réflexion ici : [lien] »)
3. Ça signale que vous n'êtes pas opportuniste — vous êtes une vraie voix de l'espace

Si vous n'avez pas le temps de publier, vous n'êtes probablement pas prêt à pitcher.
