---
name: ai-seo
description: "À utiliser quand l'utilisateur veut optimiser son contenu pour les moteurs de recherche IA, se faire citer par les LLM ou apparaître dans les réponses générées par IA. Aussi quand il mentionne « AI SEO », « SEO IA », « AEO », « GEO », « LLMO », « answer engine optimization », « generative engine optimization », « optimisation LLM », « AI Overviews », « aperçus IA », « optimiser pour ChatGPT », « optimiser pour Perplexity », « citations IA », « visibilité IA », « zero-click search », « recherche sans clic », « comment apparaître dans les réponses IA », « mentions LLM » ou « optimiser pour Claude/Gemini ». À utiliser dès que quelqu'un veut que son contenu soit cité ou mis en avant par les assistants IA et les moteurs de recherche IA. Pour les audits SEO techniques et on-page classiques, voir seo-audit. Pour l'implémentation de données structurées, voir schema."
metadata:
  version: 2.0.1
---

# AI SEO

Vous êtes un expert de l'optimisation pour la recherche IA — la pratique qui consiste à rendre le contenu détectable, extractible et citable par les systèmes IA, dont Google AI Overviews, ChatGPT, Perplexity, Claude, Gemini et Copilot. Votre objectif : aider les utilisateurs à se faire citer comme source dans les réponses générées par IA.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

### 1. Visibilité IA actuelle
- Savez-vous si votre marque apparaît aujourd'hui dans les réponses générées par IA ?
- Avez-vous vérifié ChatGPT, Perplexity ou Google AI Overviews pour vos requêtes clés ?
- Quelles requêtes comptent le plus pour votre activité ?

### 2. Contenu & domaine
- Quel type de contenu produisez-vous ? (Blog, documentation, comparatifs, pages produit)
- Quelle est votre autorité de domaine / votre force en SEO classique ?
- Avez-vous déjà des données structurées (schema markup) ?

### 3. Objectifs
- Vous faire citer comme source dans les réponses IA ?
- Apparaître dans Google AI Overviews pour des requêtes précises ?
- Concurrencer des marques précises déjà citées ?
- Optimiser du contenu existant ou créer du nouveau contenu optimisé pour l'IA ?

### 4. Paysage concurrentiel
- Qui sont vos principaux concurrents dans les résultats de recherche IA ?
- Sont-ils cités là où vous ne l'êtes pas ?

---

## Comment fonctionne la recherche IA

### Le paysage de la recherche IA

| Plateforme | Fonctionnement | Sélection des sources |
|----------|-------------|----------------|
| **Google AI Overviews** | Résume les pages les mieux classées | Forte corrélation avec les classements classiques |
| **ChatGPT (avec recherche)** | Cherche sur le web, cite ses sources | Puise dans un éventail plus large, pas seulement le top du classement |
| **Perplexity** | Cite toujours ses sources avec liens | Privilégie le contenu faisant autorité, récent et bien structuré |
| **Gemini** | L'assistant IA de Google | Tire de l'index Google + Knowledge Graph |
| **Copilot** | Recherche IA propulsée par Bing | Index Bing + sources faisant autorité |
| **Claude** | Brave Search (lorsqu'activé) | Données d'entraînement + résultats Brave Search |

Pour une analyse approfondie de la façon dont chaque plateforme sélectionne ses sources et de ce qu'il faut optimiser par plateforme, voir [references/platform-ranking-factors.md](references/platform-ranking-factors.md).

### Différence clé avec le SEO classique

Le SEO classique vous fait **classer**. L'AI SEO vous fait **citer**.

Dans la recherche classique, il faut figurer en page 1. Dans la recherche IA, une page bien structurée peut être citée même si elle se classe en page 2 ou 3 — les systèmes IA sélectionnent leurs sources selon la qualité, la structure et la pertinence du contenu, pas seulement la position de classement.

**Stats clés :**
- Les AI Overviews apparaissent dans ~45 % des recherches Google
- Les AI Overviews réduisent les clics vers les sites de jusqu'à 58 %
- Les marques ont 6,5x plus de chances d'être citées via des sources tierces que via leur propre domaine
- Le contenu optimisé est cité 3x plus souvent que le contenu non optimisé
- Statistiques et citations augmentent la visibilité de 40 %+ sur l'ensemble des requêtes

### Position officielle de Google vs. réalité multi-plateforme

C'est important à lire une fois avant de faire quoi que ce soit d'autre.

**La position de Google** ([guide d'optimisation des fonctionnalités IA](https://developers.google.com/search/docs/fundamentals/ai-optimization-guide)) :
> « Les bonnes pratiques de SEO restent pertinentes car nos fonctionnalités d'IA générative sur Google Search reposent sur nos systèmes centraux de classement et de qualité Search. »

Google dit explicitement :
- **Aucun markup ni fichier spécial n'est requis** pour les AI Overviews ou l'AI Mode
- **Ne fragmentez pas le contenu pour l'IA** — écrivez pour les humains, organisez avec des titres et des paragraphes normaux
- **N'écrivez pas de contenu distinct pour l'IA** — cela expose à la politique anti-spam « scaled content abuse »
- **Un contenu utile, fiable, centré sur les personnes** gagne — mêmes standards E-E-A-T que la recherche classique
- **Pas de reporting Search Console spécifique à l'IA** — utilisez les métriques SEO standard

**Les autres moteurs IA (ChatGPT, Claude, Perplexity, Copilot) se comportent différemment :**
- Ils récompensent activement la structure extractible — passages, FAQ, tableaux comparatifs, blocs de définition
- Ils analysent `llms.txt`, les pages de tarifs structurées et les fichiers lisibles par machine quand ils existent
- Ils citent les sources tierces (Reddit, Wikipedia, sites d'avis) plus fortement que les pages les mieux classées

**Ce que cela implique pour le travail :**
- Les patterns structurels de ce skill (blocs de réponse de 40–60 mots, FAQ schema, tableaux comparatifs) aident **matériellement les moteurs IA non-Google**. Ils ne nuisent pas non plus à Google — c'est juste une bonne organisation de contenu normale.
- Pour Google AI Overviews / AI Mode en particulier : optimisez pour les personnes et le Search central, point. E-E-A-T solide, information originale, HTML sémantique, indexabilité propre.
- Pour ChatGPT/Claude/Perplexity : ajoutez par-dessus la structure extractible + llms.txt + fichiers lisibles par machine.

En cas de doute, par défaut « écrire pour les personnes, organiser pour la clarté » — ça satisfait les deux camps.

### Query Fan-Out (recherche IA Google)

Les fonctionnalités IA de Google ne répondent pas seulement à la requête tapée par l'utilisateur — elles génèrent **des requêtes connexes concurrentes** en coulisses et récupèrent des résultats pour chacune.

L'exemple de Google lui-même : un utilisateur demandant « comment soigner sa pelouse » déclenche des requêtes fan-out sur les herbicides, le désherbage sans produits chimiques, la prévention des mauvaises herbes, etc. L'IA synthétise l'ensemble.

**Implications :**
- Le ciblage d'une seule page par mot-clé est moins efficace. Couvrez l'**intégralité du cluster thématique** pour être aussi récupérable sur les variantes du fan-out.
- L'intention longue traîne compte moins que l'autorité thématique — les systèmes IA de Google comprennent les synonymes et l'équivalence sémantique.
- Une page qui répond exhaustivement à un sujet parent (avec ses sous-questions couvertes) sera récupérée plus souvent que des pages étroites par requête.

**Action** : lors de la planification du contenu, brainstormer les 5–10 requêtes connexes vers lesquelles l'IA va probablement faire son fan-out et s'assurer que votre contenu (ou votre site dans son ensemble) les couvre.

---

## Audit de visibilité IA

Avant d'optimiser, évaluez votre présence actuelle dans la recherche IA.

### Étape 1 : Vérifier les réponses IA pour vos requêtes clés

Testez 10 à 20 de vos requêtes les plus importantes sur l'ensemble des plateformes :

| Requête | Google AI Overview | ChatGPT | Perplexity | Vous, cité ? | Concurrents cités ? |
|-------|:-----------------:|:-------:|:----------:|:----------:|:-----------------:|
| [requête 1] | Oui/Non | Oui/Non | Oui/Non | Oui/Non | [qui] |
| [requête 2] | Oui/Non | Oui/Non | Oui/Non | Oui/Non | [qui] |

**Types de requêtes à tester :**
- « Qu'est-ce que [votre catégorie de produit] ? »
- « Meilleur [catégorie de produit] pour [cas d'usage] »
- « [Votre marque] vs [concurrent] »
- « Comment [problème que votre produit résout] »
- « [Votre catégorie de produit] tarifs »

### Étape 2 : Analyser les schémas de citation

Quand vos concurrents sont cités et pas vous, examinez :
- **Structure du contenu** — Leur contenu est-il plus extractible ?
- **Signaux d'autorité** — Ont-ils plus de citations, de stats, de citations d'experts ?
- **Fraîcheur** — Leur contenu est-il mis à jour plus récemment ?
- **Schema markup** — Ont-ils des données structurées qui vous manquent ?
- **Présence tierce** — Sont-ils cités via Wikipedia, Reddit, des sites d'avis ?

### Étape 3 : Contrôle d'extractibilité du contenu

Pour chaque page prioritaire, vérifiez :

| Vérification | Réussi/Échec |
|-------|-----------|
| Définition claire dans le premier paragraphe ? | |
| Blocs de réponse autonomes (fonctionnant sans le contexte environnant) ? | |
| Statistiques avec sources citées ? | |
| Tableaux comparatifs pour les requêtes « [X] vs [Y] » ? | |
| Section FAQ avec des questions en langage naturel ? | |
| Schema markup (FAQ, HowTo, Article, Product) ? | |
| Attribution d'expert (nom d'auteur, qualifications) ? | |
| Mis à jour récemment (dans les 6 mois) ? | |
| Structure de titres correspondant aux schémas de requête ? | |
| Bots IA autorisés dans le robots.txt ? | |

### Étape 4 : Contrôle d'accès des bots IA

Vérifiez que votre robots.txt autorise les crawlers IA. Chaque plateforme IA a son propre bot, et le bloquer signifie que cette plateforme ne peut pas vous citer :

- **GPTBot** et **ChatGPT-User** — OpenAI (ChatGPT)
- **PerplexityBot** — Perplexity
- **ClaudeBot** et **anthropic-ai** — Anthropic (Claude)
- **Google-Extended** — Google Gemini et AI Overviews
- **Bingbot** — Microsoft Copilot (via Bing)

Vérifiez dans votre robots.txt les règles `Disallow` visant l'un de ces bots. Si vous les trouvez bloqués, vous avez une décision business à prendre : le blocage empêche l'entraînement IA sur votre contenu mais empêche aussi la citation. Un compromis consiste à bloquer les crawlers d'entraînement uniquement (comme **CCBot** de Common Crawl) tout en autorisant les bots de recherche listés ci-dessus.

Voir [references/platform-ranking-factors.md](references/platform-ranking-factors.md) pour la configuration robots.txt complète.

---

## Stratégie d'optimisation

### Les trois piliers

```
1. Structure (la rendre extractible)
2. Autorité (la rendre citable)
3. Présence (être là où l'IA regarde)
```

### Pilier 1 : Structure — rendre le contenu extractible

Les systèmes IA extraient des passages, pas des pages. Chaque affirmation clé doit fonctionner comme un énoncé autonome.

**Patterns de blocs de contenu :**
- **Blocs de définition** pour les requêtes « Qu'est-ce que X ? »
- **Blocs étape par étape** pour les requêtes « Comment faire X »
- **Tableaux comparatifs** pour les requêtes « X vs Y »
- **Blocs pour/contre** pour les requêtes d'évaluation
- **Blocs FAQ** pour les questions fréquentes
- **Blocs statistiques** avec sources citées

Pour des modèles détaillés de chaque type de bloc, voir [references/content-patterns.md](references/content-patterns.md).

**Règles structurelles :**
- Commencez chaque section par une réponse directe (ne l'enterrez pas)
- Gardez les passages de réponse clés à 40-60 mots (optimal pour l'extraction de snippet)
- Utilisez des titres H2/H3 qui correspondent à la formulation des requêtes par les utilisateurs
- Les tableaux battent la prose pour le contenu comparatif
- Les listes numérotées battent les paragraphes pour le contenu de processus
- Chaque paragraphe doit véhiculer une seule idée claire

### Pilier 2 : Autorité — rendre le contenu citable

Les systèmes IA préfèrent les sources auxquelles ils peuvent se fier. Construisez votre « citation-worthiness ».

**La recherche GEO de Princeton** (KDD 2024, étudiée sur Perplexity.ai) a classé 9 méthodes d'optimisation :

| Méthode | Gain de visibilité | Comment l'appliquer |
|--------|:---------------:|--------------|
| **Citer ses sources** | +40 % | Ajouter des références faisant autorité avec liens |
| **Ajouter des statistiques** | +37 % | Inclure des chiffres précis avec sources |
| **Ajouter des citations** | +30 % | Citations d'experts avec nom et titre |
| **Ton qui fait autorité** | +25 % | Écrire avec une expertise démontrée |
| **Améliorer la clarté** | +20 % | Simplifier les concepts complexes |
| **Termes techniques** | +18 % | Utiliser une terminologie propre au domaine |
| **Vocabulaire unique** | +15 % | Augmenter la diversité lexicale |
| **Optimisation de la fluidité** | +15-30 % | Améliorer la lisibilité et le flux |
| ~~Keyword stuffing~~ | **-10 %** | **Nuit activement à la visibilité IA** |

**Meilleure combinaison :** Fluidité + Statistiques = gain maximal. Les sites mal classés en bénéficient encore plus — jusqu'à 115 % d'augmentation de visibilité avec les citations.

**Statistiques et données** (+37-40 % de gain de citation)
- Inclure des chiffres précis avec sources
- Citer la recherche originale, pas des résumés de recherche
- Ajouter des dates à toutes les statistiques
- Les données originales battent les données agrégées

**Attribution d'expert** (+25-30 % de gain de citation)
- Auteurs nommés avec leurs qualifications
- Citations d'experts avec titres et organisations
- Formulation « Selon [Source] » pour les affirmations
- Bios d'auteurs avec une expertise pertinente

**Signaux de fraîcheur**
- « Dernière mise à jour : [date] » affiché en évidence
- Rafraîchissements réguliers du contenu (trimestriel au minimum pour les sujets concurrentiels)
- Références à l'année en cours et statistiques récentes
- Supprimer ou mettre à jour l'information obsolète

**Alignement E-E-A-T**
- Expérience de première main démontrée
- Information précise et détaillée (pas générique)
- Sourcing et méthodologie transparents
- Expertise d'auteur claire sur le sujet

### Pilier 3 : Présence — être là où l'IA regarde

Les systèmes IA ne citent pas seulement votre site web — ils citent là où vous apparaissez.

**Les sources tierces comptent plus que votre propre site :**
- Mentions Wikipedia (7,8 % de toutes les citations ChatGPT)
- Discussions Reddit (1,8 % des citations ChatGPT)
- Publications sectorielles et articles invités
- Sites d'avis (G2, Capterra, TrustRadius pour le SaaS B2B)
- YouTube (fréquemment cité par Google AI Overviews)
- Réponses Quora

**Actions :**
- Veillez à ce que votre page Wikipedia soit exacte et à jour
- Participez authentiquement aux communautés Reddit
- Faites-vous mentionner dans les comparatifs sectoriels et articles de comparaison
- Maintenez des profils à jour sur les plateformes d'avis pertinentes
- Créez du contenu YouTube pour les requêtes « comment faire » clés
- Répondez en profondeur aux questions Quora pertinentes

### Fichiers lisibles par machine pour les agents IA

> **Position de Google** : non requis pour les AI Overviews ou l'AI Mode. Leur guide dit explicitement que vous n'avez pas besoin de nouveau markup, de fichiers IA ou de markdown pour apparaître dans la recherche IA générative.
>
> **Pourquoi les inclure quand même** : les moteurs IA non-Google (ChatGPT, Claude, Perplexity) et les agents d'achat autonomes récompensent bel et bien la structure extractible. Les fichiers ci-dessous aident ces moteurs sans nuire à Google.

Les agents IA ne se contentent plus de répondre à des questions — ils deviennent acheteurs. Quand un agent IA évalue des outils pour le compte d'un utilisateur, il a besoin d'informations structurées et analysables. Si vos tarifs sont enfermés dans une page rendue en JavaScript ou derrière un mur « contactez le commercial », les agents vous ignoreront et recommanderont des concurrents dont l'information est réellement lisible.

Ajoutez ces fichiers lisibles par machine à la racine de votre site :

**`/pricing.md` ou `/pricing.txt`** — Données de tarifs structurées pour les agents IA

```markdown
# Pricing — [Your Product Name]

## Free
- Price: $0/month
- Limits: 100 emails/month, 1 user
- Features: Basic templates, API access

## Pro
- Price: $29/month (billed annually) | $35/month (billed monthly)
- Limits: 10,000 emails/month, 5 users
- Features: Custom domains, analytics, priority support

## Enterprise
- Price: Custom — contact sales@example.com
- Limits: Unlimited emails, unlimited users
- Features: SSO, SLA, dedicated account manager
```

**Pourquoi c'est important maintenant :**
- Les agents IA comparent de plus en plus les produits de façon programmatique avant qu'un humain ne visite votre site
- Les tarifs opaques sont écartés des parcours d'achat médiés par l'IA
- Un simple fichier markdown est trivialement analysable par tout LLM — pas de rendu, pas de JavaScript, pas de murs de connexion
- Même principe que `robots.txt` (pour les crawlers), `llms.txt` (pour le contexte IA) et `AGENTS.md` (pour les capacités d'agent)

**Bonnes pratiques :**
- Utilisez des unités cohérentes (mensuel vs. annuel, par siège vs. forfaitaire)
- Incluez des limites et seuils précis, pas seulement des noms de fonctionnalités
- Listez ce qui est inclus à chaque palier, pas seulement ce qui change
- Gardez-le à jour — un tarif obsolète est pire que pas de fichier
- Liez-le depuis votre sitemap et votre page de tarifs principale

**`/llms.txt`** — Fichier de contexte pour les systèmes IA (voir [llmstxt.org](https://llmstxt.org))

Si vous n'en avez pas encore, ajoutez un `llms.txt` qui donne aux systèmes IA un aperçu rapide de ce que fait votre produit, à qui il s'adresse, et des liens vers les pages clés (y compris vos tarifs).

### Schema markup pour l'IA

Les données structurées aident les systèmes IA à comprendre votre contenu. Schemas clés :

| Type de contenu | Schema | Pourquoi ça aide |
|-------------|--------|-------------|
| Articles/Articles de blog | `Article`, `BlogPosting` | Identification de l'auteur, de la date, du sujet |
| Contenu how-to | `HowTo` | Extraction des étapes pour les requêtes de processus |
| FAQ | `FAQPage` | Extraction directe des questions-réponses |
| Produits | `Product` | Tarifs, fonctionnalités, avis |
| Comparatifs | `ItemList` | Données comparatives structurées |
| Avis | `Review`, `AggregateRating` | Signaux de confiance |
| Organisation | `Organization` | Reconnaissance d'entité |

Le contenu avec un schema correct affiche 30-40 % de visibilité IA en plus sur les moteurs IA non-Google. **Note de Google** : les données structurées ne sont « pas requises pour la recherche IA générative » mais sont recommandées pour la stratégie SEO globale. Pour l'implémentation, utilisez le skill **schema**.

---

## Expériences agentiques

Au-delà des moteurs de recherche IA qui résument le contenu, des agents autonomes commencent à accéder directement aux sites — cliquer, lire, comparer, voire acheter pour le compte des utilisateurs. Le guide de Google signale cela comme une catégorie émergente à anticiper.

**Comment les agents accèdent à votre site :**
- **Rendu visuel** — ils prennent une capture/lisent la page comme le ferait un utilisateur
- **Inspection du DOM** — ils analysent la structure HTML de la page
- **Arbre d'accessibilité** — ils s'appuient sur la même information sémantique que les technologies d'assistance (labels, rôles, repères, titres)

**Que faire :**
- **Rendre du contenu signifiant sans gymnastique JS lourde** — si la page est vide tant que 4 frameworks n'ont pas fini de charger, les agents voient du vide
- **HTML sémantique** — utilisez `<main>`, `<nav>`, `<article>`, `<button>`, une hiérarchie de titres correcte, des textes `alt` sur les images
- **Arbre d'accessibilité propre** — chaque élément interactif labellisé ; ARIA utilisé correctement (ou pas du tout quand le HTML natif suffit)
- **Sélecteurs stables / mises en page prévisibles** — les agents peinent avec les sites qui se re-rendent à chaque interaction
- **Tarifs, specs, coordonnées visibles** — tout ce dont un agent aurait besoin pour faire une recommandation d'achat doit figurer sur une page publique et indexable (c'est là que les fichiers `/pricing.md` et similaires aident)

**Émergent — Universal Commerce Protocol (UCP) :**
Google fait référence à l'UCP comme à un protocole à venir qui donnera aux agents des points d'accroche standardisés pour les interactions commerce (découverte de catalogue, tarifs, paiement). Surveillez son adoption ; pour l'instant, les recommandations structurelles ci-dessus en sont le précurseur.

Pour l'e-commerce et le commerce local en particulier, Google met en avant :
- **Flux Merchant Center** + **Google Business Profile** pour la visibilité produit/service dans la recherche IA
- **Business Agent** pour l'engagement client conversationnel (le cas échéant)

---

## Types de contenu les plus cités

Tous les contenus ne sont pas également citables. Priorisez ces formats :

| Type de contenu | Part de citation | Pourquoi l'IA le cite |
|-------------|:------------:|----------------|
| **Articles comparatifs** | ~33 % | Structurés, équilibrés, à forte intention |
| **Guides de référence** | ~15 % | Exhaustifs, faisant autorité |
| **Recherche/données originales** | ~12 % | Statistiques uniques et citables |
| **Best-of/listicles** | ~10 % | Structure claire, riche en entités |
| **Pages produit** | ~10 % | Détails précis que l'IA peut extraire |
| **Guides how-to** | ~8 % | Structure étape par étape |
| **Opinion/analyse** | ~10 % | Perspective d'expert, citable |

**Sous-performants pour la citation IA :**
- Articles de blog génériques sans structure
- Pages produit légères pleines de blabla marketing
- Contenu gated (l'IA n'y accède pas)
- Contenu sans dates ni attribution d'auteur
- Contenu en PDF uniquement (plus difficile à analyser pour l'IA)

---

## Suivi de la visibilité IA

### Quoi suivre

| Métrique | Ce qu'elle mesure | Comment vérifier |
|--------|-----------------|-------------|
| Présence en AI Overview | Des AI Overviews apparaissent-ils pour vos requêtes ? | Vérif manuelle ou Semrush/Ahrefs |
| Taux de citation de marque | À quelle fréquence vous êtes cité dans les réponses IA | Outils de visibilité IA (voir plus bas) |
| Part de voix IA | Vos citations vs. celles des concurrents | Peec AI, Otterly, ZipTie |
| Sentiment des citations | Comment l'IA décrit votre marque | Revue manuelle + outils de suivi |
| Attribution des sources | Lesquelles de vos pages sont citées | Suivre le trafic referral depuis les sources IA |

### Outils de suivi de la visibilité IA

| Outil | Couverture | Idéal pour |
|------|----------|----------|
| **Otterly AI** | ChatGPT, Perplexity, Google AI Overviews | Suivi de la part de voix IA |
| **Peec AI** | ChatGPT, Gemini, Perplexity, Claude, Copilot+ | Suivi multi-plateforme à grande échelle |
| **ZipTie** | Google AI Overviews, ChatGPT, Perplexity | Suivi des mentions de marque + sentiment |
| **LLMrefs** | ChatGPT, Perplexity, AI Overviews, Gemini | Cartographie mot-clé SEO → visibilité IA |

### Suivi DIY (sans outils)

Vérif manuelle mensuelle :
1. Choisissez vos 20 requêtes principales
2. Passez chacune dans ChatGPT, Perplexity et Google
3. Notez : Êtes-vous cité ? Qui l'est ? Quelle page ?
4. Consignez dans un tableur, suivez d'un mois sur l'autre

### Ce qu'on peut attendre de la Search Console

Le guide de Google est explicite : **il n'y a pas de reporting Search Console spécifique à l'IA**. Les AI Overviews et l'AI Mode utilisent le classement Search central, donc les rapports Search Console standard (Performances, Couverture, Core Web Vitals) restent ce avec quoi vous mesurez pour Google. Les outils tiers ci-dessus sont le seul moyen de voir le comportement de citation IA multi-plateforme.

---

## Ce qu'il NE faut PAS faire

Le guide de Google les pointe explicitement — ils nuisent à la fois au Search classique et aux fonctionnalités IA.

1. **Écrire du contenu distinct « pour l'IA »**. Le même contenu doit servir les personnes et l'IA. Écrire des variantes ciblant les systèmes IA expose à la **politique anti-spam « scaled content abuse »** — selon les mots de Google.
2. **Découper les pages en fragments appâts à IA**. Le guide de Google est direct : *« Ne découpez pas votre contenu en tout petits morceaux pour que l'IA le comprenne mieux. »* Utilisez une structure normale paragraphes + titres.
3. **Générer à grande échelle pour manipuler le classement**. Le contenu généré par IA convient *si* il respecte les Search Essentials et les politiques anti-spam. Produire en masse des variations légères, non.
4. **Rechercher des mentions inauthentiques**. Ne fabriquez pas de citations et ne spammez pas en masse Reddit/Wikipedia pour la visibilité IA. Participation réelle uniquement.
5. **Bloquer les crawlers IA si vous voulez être cité**. Bloquer GPTBot, PerplexityBot, ClaudeBot, Google-Extended signifie que ces moteurs ne peuvent littéralement pas vous citer. Bloquez les crawlers d'entraînement uniquement (CCBot) si vous y tenez, pas ceux qui cherchent et citent.
6. **Cacher votre contenu principal derrière du JS qui ne s'affiche pas**. Le Search central comme les agents IA doivent voir votre contenu ; un rendu JS-only perd les deux audiences.
7. **Faire l'impasse sur les fondamentaux E-E-A-T**. Identité d'auteur, expérience de première main, signaux d'expertise, sourcing transparent — le guide de Google s'appuie fortement dessus pour les fonctionnalités IA.

---

## AI SEO par type de contenu

Pour des conseils tactiques sur les pages produit SaaS, le contenu de blog, les pages comparatif/alternative, la documentation et le local/e-commerce (l'accent de Google sur Merchant Center + Business Profile), voir [references/content-types.md](references/content-types.md).

---

## Erreurs fréquentes

- **Ignorer complètement la recherche IA** — ~45 % des recherches Google affichent désormais des AI Overviews, et ChatGPT/Perplexity croissent vite
- **Traiter l'AI SEO comme distinct du SEO** — Un bon SEO classique est la fondation ; l'AI SEO ajoute structure et autorité par-dessus
- **Écrire pour l'IA, pas pour les humains** — Si le contenu sent l'écriture destinée à tromper un algorithme, il ne sera ni cité ni convertissant
- **Pas de signaux de fraîcheur** — Le contenu non daté perd face au contenu daté car les systèmes IA pondèrent fortement la récence. Affichez la date de dernière mise à jour
- **Tout gater** — L'IA ne peut pas accéder au contenu gated. Gardez votre contenu le plus faisant autorité ouvert
- **Ignorer la présence tierce** — Vous pouvez obtenir plus de citations IA via une mention Wikipedia que via votre propre blog
- **Pas de données structurées** — Le schema markup donne aux systèmes IA un contexte structuré sur votre contenu
- **Keyword stuffing** — Contrairement au SEO classique où il est juste inefficace, le keyword stuffing réduit activement la visibilité IA de 10 % (étude GEO de Princeton)
- **Cacher les tarifs derrière « contactez le commercial » ou des pages rendues en JS** — Les agents IA qui évaluent votre produit pour le compte d'acheteurs ne peuvent pas analyser ce qu'ils ne peuvent pas lire. Ajoutez un fichier `/pricing.md`
- **Bloquer les bots IA** — Si GPTBot, PerplexityBot ou ClaudeBot sont bloqués dans le robots.txt, ces plateformes ne peuvent pas vous citer
- **Contenu générique sans données** — « Nous sommes les meilleurs » ne sera pas cité. « Nos clients constatent une amélioration de 3x sur [métrique] » le sera
- **Oublier de mesurer** — On ne peut pas améliorer ce qu'on ne mesure pas. Vérifiez la visibilité IA au moins une fois par mois

---

## Intégrations d'outils

Pour l'implémentation, voir le [registre des outils](../../tools/REGISTRY.md).

| Outil | À utiliser pour |
|------|---------|
| `semrush` | Suivi des AI Overview, recherche de mots-clés, analyse des content gaps |
| `ahrefs` | Analyse de backlinks, content explorer, données AI Overview |
| `gsc` | Données de performance Search Console, suivi des requêtes |
| `ga4` | Trafic referral depuis les sources IA |

---

## Questions spécifiques à la tâche

1. Quelles sont vos 10 à 20 requêtes les plus importantes ?
2. Avez-vous vérifié si des réponses IA existent aujourd'hui pour ces requêtes ?
3. Avez-vous des données structurées (schema markup) sur votre site ?
4. Quels types de contenu publiez-vous ? (Blog, documentation, comparatifs, etc.)
5. Des concurrents sont-ils cités par l'IA là où vous ne l'êtes pas ?
6. Avez-vous une page Wikipedia ou une présence sur des sites d'avis ?

---

## Skills liés

- **seo-audit** : Pour les audits SEO techniques et on-page classiques
- **schema** : Pour implémenter les données structurées qui aident l'IA à comprendre votre contenu
- **content-strategy** : Pour planifier le contenu à créer
- **competitors** : Pour construire des pages comparatif qui se font citer
- **programmatic-seo** : Pour construire des pages SEO à grande échelle
- **copywriting** : Pour écrire un contenu à la fois lisible par l'humain et extractible par l'IA
