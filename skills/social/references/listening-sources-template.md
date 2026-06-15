# Sources de listening — Template

Copiez ce fichier vers `.agents/listening-sources.md` dans votre projet (ou `.claude/listening-sources.md`) et remplissez les crochets. Claude le lit lors de l'exécution du [workflow de listening](listening.md).

Supprimez les sections que vous n'utilisez pas. Gardez ce fichier court et à jour — des sources périmées sont pires que pas de sources.

---

## Ce que nous écoutons

**Marque / produit :** [Nom de votre produit]
**Catégorie :** [ex. « assistant d'écriture IA », « GUI Postgres »]
**Objectif :** [ex. « trouver des gens qui migrent depuis Notion », « interagir avec des fondateurs de SaaS B2B de 50-200 employés »]

## ICP (pour le scoring)

Utilisé par la [grille de scoring](listening.md#scoring-rubric) pour juger l'adéquation à l'ICP.

- **Rôle :** [ex. « fondateur, responsable marketing, lead marketing ops »]
- **Stade de l'entreprise :** [ex. « SaaS de l'amorçage à la Série B, 10-200 employés »]
- **Secteur :** [ex. « SaaS B2B, infra, devtools »]
- **Signaux d'adéquation :** [ex. « écrit sur le GTM, fait de la pub payante, a récemment levé »]

---

## Comptes cibles

Interagir avec **chaque** post de ces comptes quand c'est pertinent. Garder cette liste à 20-50 max.

### LinkedIn (browser-driven — utiliser dev-browser pour voir le feed)
- [Nom] — `linkedin.com/in/handle`
- [Nom] — `linkedin.com/in/handle`

### X / Twitter (browser-driven)
- [@handle]
- [@handle]

### Reddit
- u/[username]
- u/[username]

### Bluesky
- [handle.bsky.social]

### Blogs / Newsletters (RSS)
- [Nom] — `https://example.com/feed/`
- [Nom] — `https://example.substack.com/feed`

### Chaînes YouTube (RSS)
- [Nom] — ID de chaîne `UCxxxxxxxx`

---

## Mots-clés (signaux d'intention)

Rechercher sur toutes les plateformes. Claude les passe via Reddit, HN, Bluesky sur la [boucle quotidienne](listening.md#the-daily-triage-loop).

### Forte intention (quelqu'un qui compare ou migre)
- `"alternative to [competitor]"`
- `"looking for a [category] tool"`
- `"recommend a [category]"`
- `"switching from [competitor]"`
- `"frustrated with [competitor]"`

### Signaux de problème (quelqu'un en souffrance)
- `"[category] is so [bad/hard/expensive]"`
- `"why is [category] [problem]"`
- `"hate [pain point]"`

### Mentions de marque
- `"[your brand]"`
- `"[your brand misspelling]"`
- `"[your domain]"`

### Mentions de concurrents (surveiller le langage de migration)
- `"[competitor 1]"`
- `"[competitor 2]"`

---

## Subreddits

Récupérés via l'API JSON de Reddit sur la boucle quotidienne.

- r/SaaS
- r/Entrepreneur
- r/[votre niche, ex. « marketing », « devtools »]
- r/[communauté adjacente]

---

## Recherches sauvegardées (manuel / browser-driven)

URL que Claude ouvre via dev-browser pour scanner.

### LinkedIn Sales Navigator
- [Nom de recherche] — `https://linkedin.com/sales/search/people?...`

### LinkedIn (classique)
- Hashtag de posts — `https://linkedin.com/feed/hashtag/yourtopic/`

### Recherche avancée X
- [Nom de recherche] — `https://x.com/search?q=...&f=live`

---

## Ne pas engager

Épargnez-vous les regrets.

- Comptes connus pour leurs attaques de mauvaise foi : [@handle], [@handle]
- Marques/concurrents bloqués qui feront des screenshots : [liste]
- Sujets à éviter : [politique, [les hot takes de votre fondateur], etc.]

---

## Notes pour Claude

- Quand on demande « le top 10 du jour », produire au format défini dans [listening.md](listening.md#the-daily-triage-loop)
- Pour LinkedIn et X, utiliser dev-browser avec la session persistante (l'utilisateur est connecté)
- Pour tout le reste, utiliser les recettes curl de [listening.md](listening.md#sources--light-tooling-curl-recipes)
- Lookback par défaut : 24 h. L'utilisateur peut override.
- Toujours demander avant de poster — produire des brouillons, l'utilisateur approuve et poste manuellement
