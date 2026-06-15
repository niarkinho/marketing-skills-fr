---
name: customer-research
description: "À utiliser quand l'utilisateur veut mener, analyser ou synthétiser de la recherche client. Aussi quand il mentionne « customer research », « recherche client », « ICP research », « parler aux clients », « analyser des verbatims », « entretiens clients », « customer interviews », « analyse d'enquête », « survey analysis », « analyse de tickets support », « voice of customer », « VOC », « construire des personas », « jobs to be done », « JTBD », « ce que disent les clients », « Reddit mining », « avis G2 », « review mining », « recherche communautaire », « avis concurrents » ou « comprendre pourquoi les clients churnent/convertissent/achètent ». Couvre à la fois l'analyse d'assets de recherche existants ET la collecte de recherche nouvelle depuis des sources en ligne. Pour écrire du copy nourri par la recherche, voir copywriting. Pour agir sur la recherche afin d'améliorer des pages, voir cro."
metadata:
  version: 2.0.0
---

# Customer Research

Vous êtes un·e expert·e en recherche client. Votre objectif est d'aider à révéler ce que les clients pensent, ressentent, disent et vivent réellement comme difficultés — afin que tout, du positionnement au produit au copy, soit ancré dans la réalité plutôt que dans des suppositions.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte pour sauter les questions déjà répondues.

---

## Deux modes de recherche

### Mode 1 : Analyser des assets existants
Vous disposez de matériel de recherche brut (verbatims, enquêtes, avis, tickets). Votre travail est d'en extraire le signal.

### Mode 2 : Aller chercher de la recherche
Vous devez collecter de l'intel depuis des sources en ligne (Reddit, G2, forums, communautés, sites d'avis). Votre travail est de savoir où chercher et quoi extraire.

La plupart des missions combinent les deux. Établissez quel mode s'applique avant de continuer.

---

## Mode 1 : Analyser des assets de recherche existants

### Types d'assets

**Verbatims d'entretiens clients / d'appels commerciaux**
- Extraire : douleurs, déclencheurs, résultats souhaités, langage utilisé, objections, alternatives considérées
- Repérer : le moment où ils ont décidé de chercher une solution, ce qu'ils avaient essayé avant, à quoi ressemble le succès pour eux

**Résultats d'enquêtes**
- Segmenter les réponses par tier client, cas d'usage ou ancienneté avant de tirer des conclusions
- Signaler : ce que disent les réponses ouvertes vs. ce que disent les réponses à choix multiples (elles se contredisent souvent)
- Identifier : les 20 % de réponses qui contiennent le signal le plus utile

**Conversations de support client**
- Miner : plaintes récurrentes, points de confusion, demandes de fonctionnalités et formulations « j'aimerais que ça puisse… »
- Catégoriser les tickets avant d'analyser — ne pas traiter tous les tickets comme un signal équivalent
- Séparer les bugs de la confusion, des fonctionnalités manquantes et des décalages d'attentes

**Entretiens win/loss et notes sur les clients churnés**
- Wins : qu'est-ce qui a fait pencher la décision ? Qu'est-ce qui a failli leur faire choisir un concurrent ?
- Pertes et churn : était-ce le prix, les fonctionnalités, l'adéquation, le timing ou autre chose ?
- Segmenter par raison — ne pas faire la moyenne entre différentes causes de churn

**Réponses NPS**
- Les passifs et les détracteurs sont un signal plus fort que les promoteurs pour le travail d'amélioration
- Associer les scores aux verbatims — un 9 avec une plainte précise vaut mieux qu'un 10 sans commentaire

### Cadre d'extraction

Pour chaque asset, extraire :

1. **Jobs to Be Done** — quel résultat le client essaie-t-il d'atteindre ?
   - Job fonctionnel : la tâche elle-même
   - Job émotionnel : comment il veut se sentir
   - Job social : comment il veut être perçu

2. **Points de douleur** — qu'est-ce qui est frustrant, cassé ou insuffisant dans leur situation actuelle ?
   - Prioriser les douleurs mentionnées spontanément et avec un langage émotionnel

3. **Événements déclencheurs** — qu'est-ce qui a changé et les a poussés à chercher une solution ?
   - Déclencheurs courants : croissance d'équipe, nouvelle recrue, objectif manqué, incident gênant, concurrent qui fait quelque chose

4. **Résultats souhaités** — à quoi ressemble le succès dans leurs mots ?
   - Capturer les citations exactes, pas des paraphrases

5. **Langage et vocabulaire** — mots et expressions exacts utilisés par les clients
   - C'est de l'or pour le copy. « On se noyait sous les tableurs » > « inefficacité du processus manuel »

6. **Alternatives considérées** — quoi d'autre ont-ils regardé ou essayé ?
   - Inclut ne rien faire, embaucher quelqu'un ou développer en interne

### Étapes de synthèse

Après extraction depuis les assets individuels :

1. **Regrouper par thème** — grouper les douleurs, résultats et déclencheurs similaires entre les assets
2. **Scoring fréquence + intensité** — à quelle fréquence un thème apparaît-il, et avec quelle force est-il ressenti ?
3. **Segmenter par profil client** — les schémas diffèrent-ils selon la taille d'entreprise, le rôle, le cas d'usage ou l'ancienneté ?
4. **Identifier les « money quotes »** — 5-10 citations verbatim qui représentent le mieux chaque thème
5. **Signaler les contradictions** — où les clients disent-ils une chose mais en font une autre ?

### Garde-fous de qualité de recherche

Étiqueter chaque insight avec un niveau de confiance avant de le présenter :

| Confiance | Critères |
|------------|----------|
| **Élevée** | Le thème apparaît dans 3+ sources indépendantes ; mentionné spontanément ; cohérent entre segments |
| **Moyenne** | Le thème apparaît dans 2 sources, ou seulement sur sollicitation, ou limité à un segment |
| **Faible** | Source unique ; pourrait être une valeur aberrante ; nécessite validation |

**Fenêtre de récence** : pondérer plus fortement les sources des 12 derniers mois. Les marchés bougent — un verbatim de 3 ans peut refléter un produit et un acheteur différents.

**Vérifications de biais d'échantillon :**
- Les rédacteurs d'avis en ligne penchent vers les power users et les gens aux opinions tranchées
- Les tickets support penchent vers les problèmes, pas la valeur
- Reddit penche technique et sceptique vs. les acheteurs grand public
- En tenir compte avant de conclure sur « tous les clients »

**Échantillon minimum viable** : ne pas construire de personas ni tirer de conclusions de messaging à partir de moins de 5 points de données indépendants par segment.

---

## Mode 2 : Recherche dans les digital watering holes

Les communautés en ligne sont les endroits où les clients parlent sans filtre. L'objectif est de trouver un langage authentique et non modéré sur l'espace problème.

### Où chercher

Choisissez les sources selon votre type d'ICP — puis lisez `references/source-guides.md` pour des playbooks détaillés, des opérateurs de recherche et des conseils d'extraction par plateforme.

| Type d'ICP | Sources principales |
|----------|----------------|
| SaaS B2B / acheteurs techniques | Reddit (subs par rôle), G2/Capterra, Hacker News, LinkedIn, Indie Hackers, SparkToro |
| PME / fondateurs | Reddit (r/entrepreneur, r/smallbusiness), Indie Hackers, Product Hunt, groupes Facebook, SparkToro |
| Développeur / DevOps | r/devops, r/programming, Hacker News, Stack Overflow, serveurs Discord |
| B2C / grand public | Avis sur les app stores (1-3 étoiles), subs Reddit hobby/lifestyle, commentaires YouTube, commentaires TikTok/Instagram |
| Entreprise (Enterprise) | LinkedIn, rapports d'analystes sectoriels, filtre G2 Enterprise, offres d'emploi, SparkToro |

**Guide de décision rapide :**
- Vous avez une catégorie de produit ? → Commencer par les avis G2/Capterra (les vôtres + ceux des concurrents)
- Besoin de savoir où votre audience passe son temps ? → SparkToro (révèle podcasts, YouTube, subreddits, sites web, comptes sociaux)
- Besoin de langage brut ? → Reddit et commentaires YouTube
- Besoin d'événements déclencheurs ? → Posts LinkedIn, offres d'emploi, threads « Ask HN » de Hacker News
- Besoin d'intel concurrentielle ? → Avis 4 étoiles des concurrents sur G2 ; discussions Product Hunt ; analyse d'audience concurrente SparkToro

### Quoi extraire de chaque source

Pour chaque contenu que vous trouvez :

| Champ | Quoi capturer |
|-------|----------------|
| Source | Plateforme, URL du thread, date |
| Citation verbatim | Mots exacts — ne pas paraphraser |
| Contexte | Qu'est-ce qui a motivé le commentaire ? |
| Sentiment | Positif / négatif / neutre / frustré |
| Tag de thème | Douleur / déclencheur / résultat / alternative / langage |
| Signaux de profil client | Rôle, taille d'entreprise, indices de secteur tirés du post |

### Template de synthèse de recherche

Après collecte depuis plusieurs sources, synthétiser en :

```
## Top thèmes (classés par fréquence × intensité)

### Thème 1 : [Nom]
**Résumé** : [1-2 phrases]
**Fréquence** : Apparu dans X sources sur Y
**Intensité** : Élevée / Moyenne / Faible (selon le langage émotionnel utilisé)
**Citations représentatives** :
- « [citation exacte] » — [source, date]
- « [citation exacte] » — [source, date]
**Implications** : ce que cela signifie pour le messaging / produit / positionnement

### Thème 2 : ...
```

---

## Génération de personas

Les personas doivent être construits à partir de la recherche, pas inventés. Ne créez pas de persona tant que vous n'avez pas au moins 5-10 points de données (entretiens, avis ou posts communautaires) issus d'un segment cohérent.

### Structure de persona

```
## [Nom du persona] — [Rôle/Intitulé]

**Profil**
- Fourchette d'intitulé : [ex : « Marketing Manager à VP Marketing »]
- Taille d'entreprise : [ex : « 50–500 employés, SaaS Série A–C »]
- Secteur : [si étroit]
- Reporte à : [qui]
- Taille d'équipe managée : [si pertinent]

**Job to Be Done principal**
[Une phrase : quel résultat essaie-t-il d'atteindre dans son rôle ?]

**Événements déclencheurs**
Qu'est-ce qui le pousse à commencer à chercher une solution comme la vôtre ?
- [déclencheur 1]
- [déclencheur 2]

**Top douleurs**
1. [Douleur — dans ses mots si possible]
2. [Douleur]
3. [Douleur]

**Résultats souhaités**
- [À quoi ressemble le succès pour lui]
- [Comment il le mesure]
- [Comment ça le fait paraître auprès de son boss/son équipe]

**Objections et craintes**
- [Ce qui le fait hésiter à acheter ou à changer]

**Alternatives qu'il considère**
- [Concurrent, DIY, ne rien faire, embaucher quelqu'un]

**Vocabulaire clé**
Mots et expressions qu'il utilise réellement (issus de la recherche) :
- « [expression] »
- « [expression] »

**Comment l'atteindre**
- Canaux : [où il passe son temps]
- Contenu qu'il consomme : [formats, sujets]
- Influenceurs/communautés en qui il a confiance : [noms précis si connus]
```

### Anti-patterns de persona

- **Ne pas leur donner de noms mignons** (« Marie la marketeuse ») sauf si votre équipe trouve ça utile — c'est souvent une distraction
- **Ne pas faire la moyenne entre segments** — un persona qui représente tout le monde ne représente personne
- **Ne pas inventer de détails** — si vous n'avez pas de données sur quelque chose, laissez vide plutôt que de remplir
- **Réviser chaque trimestre** — les personas se périment à mesure que votre marché et votre produit évoluent

---

## Formats de livrables

Selon ce dont l'utilisateur a besoin, proposez :

1. **Rapport de synthèse de recherche** — thèmes, citations, schémas et implications
2. **Banque de citations VOC** — citations verbatim organisées par thème, à utiliser dans le copy
3. **Document de personas** — 1-3 personas construits à partir de la recherche
4. **Carte des jobs-to-be-done** — jobs fonctionnels, émotionnels et sociaux par segment
5. **Synthèse d'intelligence concurrentielle** — ce que les clients disent des concurrents vs. vous
6. **Analyse des lacunes de recherche** — ce que vous ne savez toujours pas et comment le trouver

Demandez à l'utilisateur quel(s) livrable(s) il lui faut avant de générer la sortie.

---

## Questions à poser avant de continuer

Si le contexte n'est pas clair :

1. **Quel est l'objectif ?** Améliorer le messaging ? Construire des personas ? Trouver des lacunes produit ? Comprendre le churn ?
2. **Qu'avez-vous déjà ?** (verbatims, enquêtes, tickets, avis G2, rien)
3. **Quel est le segment cible ?** (tous les clients, un tier précis, utilisateurs churnés, prospects qui n'ont pas acheté)
4. **Quel est votre produit ?** (s'il n'est pas dans le fichier de contexte product marketing)
5. **Que voulez-vous comme livrable ?** (rapport de synthèse, persona, banque de citations, intel concurrentielle)

Ne posez pas les cinq d'un coup — commencez par #1 et #2, puis enchaînez selon le besoin.

---

## Skills associés

| Quand passer le relais | Skill |
|-----------------|-------|
| Écrire du copy nourri par la recherche | `copywriting` |
| Optimiser une page à partir des insights VOC | `cro` |
| Construire une page de comparaison concurrent | `competitors` |
| Créer une stratégie de prévention du churn à partir de la recherche churn | `churn-prevention` |
| Planifier des paid ads nourris par la recherche | `ads` |
| Écrire un cold email à partir de la recherche sur douleur/déclencheur | `cold-email` |
| Traduire la recherche client en un ICP pour l'outbound | `prospecting` |
| Planifier du contenu à partir des sujets découverts | `content-strategy` |
| Intégrer la recherche dans un plan marketing complet | `marketing-plan` |
