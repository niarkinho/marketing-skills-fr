---
name: content-strategy
description: À utiliser quand l'utilisateur veut planifier une stratégie de contenu, décider quel contenu créer ou déterminer quels sujets couvrir. Aussi quand il mentionne « stratégie de contenu », « content strategy », « sur quoi écrire », « idées de contenu », « stratégie blog », « topic clusters », « planification de contenu », « calendrier éditorial », « content marketing », « content roadmap », « quel contenu créer », « sujets de blog », « content pillars », « piliers de contenu » ou « je ne sais pas quoi écrire ». À utiliser dès que quelqu'un a besoin d'aide pour décider quel contenu produire, pas seulement pour le rédiger. Pour rédiger des pièces individuelles, voir copywriting. Pour les audits SEO spécifiques, voir seo-audit. Pour le contenu réseaux sociaux spécifiquement, voir social.
metadata:
  version: 2.0.0
---

# Stratégie de contenu

Vous êtes stratège de contenu. Votre objectif : aider à planifier un contenu qui génère du trafic, construit de l'autorité et génère des leads en étant soit recherchable (searchable), soit partageable (shareable), soit les deux.

## Avant de planifier

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur les anciens setups), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (le demander s'il n'est pas fourni) :

### 1. Contexte de l'activité
- Que fait l'entreprise ?
- Qui est le client idéal ?
- Quel est l'objectif principal du contenu ? (trafic, leads, notoriété de marque, thought leadership)
- Quels problèmes votre produit résout-il ?

### 2. Recherche client
- Quelles questions les clients posent-ils avant d'acheter ?
- Quelles objections reviennent dans les calls de vente ?
- Quels sujets apparaissent en boucle dans les tickets de support ?
- Quel langage les clients utilisent-ils pour décrire leurs problèmes ?

### 3. État actuel
- Avez-vous du contenu existant ? Qu'est-ce qui marche ?
- De quelles ressources disposez-vous ? (rédacteurs, budget, temps)
- Quels formats de contenu pouvez-vous produire ? (écrit, vidéo, audio)

### 4. Paysage concurrentiel
- Qui sont vos principaux concurrents ?
- Quels content gaps existent sur votre marché ?

---

## Searchable vs Shareable

Chaque pièce de contenu doit être searchable, shareable, ou les deux. Priorisez dans cet ordre — le trafic de recherche est le socle.

**Le contenu searchable** capte une demande existante. Optimisé pour les gens qui cherchent activement des réponses.

**Le contenu shareable** crée de la demande. Diffuse des idées et fait parler les gens.

### Quand vous rédigez du contenu searchable

- Cibler un mot-clé ou une question spécifique
- Coller exactement à l'intention de recherche — répondre à ce que le chercheur veut
- Utiliser des titres clairs qui correspondent aux requêtes de recherche
- Structurer avec des titres qui reflètent les patterns de recherche
- Placer les mots-clés dans le titre, les titres de section, le premier paragraphe, l'URL
- Fournir une couverture exhaustive (ne pas laisser de questions sans réponse)
- Inclure des données, des exemples et des liens vers des sources faisant autorité
- Optimiser pour la découverte par les IA/LLM : positionnement clair, contenu structuré, cohérence de marque à travers le web

### Quand vous rédigez du contenu shareable

- Mener avec un insight inédit, des données originales ou une prise à contre-courant
- Remettre en cause la sagesse conventionnelle avec des arguments bien construits
- Raconter des histoires qui font ressentir quelque chose
- Créer du contenu que les gens veulent partager pour paraître intelligents ou aider les autres
- Connecter aux tendances actuelles ou aux problèmes émergents
- Partager des expériences honnêtes et vulnérables dont les autres peuvent apprendre

---

## Types de contenu

### Types de contenu searchable

**Contenu par cas d'usage**
Formule : [persona] + [cas d'usage]. Cible les mots-clés de longue traîne.
- « Gestion de projet pour designers »
- « Suivi de tâches pour développeurs »
- « Collaboration client pour freelances »

**Hub and Spoke**
Hub = vue d'ensemble exhaustive. Spokes = sous-sujets liés.
```
/topic (hub)
├── /topic/subtopic-1 (spoke)
├── /topic/subtopic-2 (spoke)
└── /topic/subtopic-3 (spoke)
```
Créer le hub d'abord, puis construire les spokes. Mailler stratégiquement.

**Note :** la plupart du contenu fonctionne très bien sous `/blog`. N'utilisez des structures d'URL hub/spoke dédiées que pour les sujets majeurs avec une profondeur en couches (ex. le guide `/agile` d'Atlassian). Pour les articles de blog typiques, `/blog/post-title` suffit.

**Bibliothèques de templates**
Mots-clés à forte intention + adoption produit.
- Cibler des recherches comme « template plan marketing »
- Fournir une valeur autonome immédiate
- Montrer comment le produit enrichit le template

### Types de contenu shareable

**Thought Leadership**
- Articuler des concepts que tout le monde ressent mais n'a pas nommés
- Remettre en cause la sagesse conventionnelle avec des preuves
- Partager des expériences honnêtes et vulnérables

**Contenu data-driven**
- Analyse de données produit (insights anonymisés)
- Analyse de données publiques (révéler des patterns)
- Recherche originale (mener des expériences, partager les résultats)

**Expert Roundups**
15-30 experts répondant à une question spécifique. Distribution intégrée.

**Études de cas**
Structure : Défi → Solution → Résultats → Enseignements clés

**Meta Content**
Transparence behind-the-scenes. « Comment on a atteint nos premiers 5k€ de MRR », « Pourquoi on a choisi la dette plutôt que le VC ».

Pour du contenu programmatique à l'échelle, voir le skill **programmatic-seo**.

---

## Content pillars et topic clusters

Les content pillars sont les 3-5 sujets centraux que votre marque va posséder. Chaque pilier engendre un cluster de contenu lié.

La plupart du temps, tout le contenu peut vivre sous `/blog` avec un bon maillage interne entre articles liés. Des pages piliers dédiées avec des structures d'URL custom (comme `/guides/topic`) ne sont nécessaires que lorsque vous construisez des ressources exhaustives avec plusieurs couches de profondeur.

### Comment identifier les piliers

1. **Product-led** : quels problèmes votre produit résout-il ?
2. **Audience-led** : qu'est-ce que votre ICP a besoin d'apprendre ?
3. **Search-led** : quels sujets ont du volume dans votre espace ?
4. **Competitor-led** : sur quoi les concurrents se positionnent-ils ?

### Structure d'un pilier

```
Pillar Topic (Hub)
├── Subtopic Cluster 1
│   ├── Article A
│   ├── Article B
│   └── Article C
├── Subtopic Cluster 2
│   ├── Article D
│   ├── Article E
│   └── Article F
└── Subtopic Cluster 3
    ├── Article G
    ├── Article H
    └── Article I
```

### Critères d'un pilier

Un bon pilier doit :
- S'aligner avec votre produit/service
- Correspondre à ce qui compte pour votre audience
- Avoir du volume de recherche et/ou de l'intérêt social
- Être assez large pour de nombreux sous-sujets

---

## Recherche de mots-clés par stade d'achat

Mapper les sujets sur le parcours d'achat avec des modificateurs de mots-clés éprouvés :

### Stade Awareness (notoriété)
Modificateurs : « what is », « how to », « guide to », « introduction to »

Exemple : si les clients posent des questions sur les bases de la gestion de projet :
- « What is Agile Project Management »
- « Guide to Sprint Planning »
- « How to Run a Standup Meeting »

### Stade Consideration (considération)
Modificateurs : « best », « top », « vs », « alternatives », « comparison »

Exemple : si les clients évaluent plusieurs outils :
- « Best Project Management Tools for Remote Teams »
- « Asana vs Trello vs Monday »
- « Basecamp Alternatives »

### Stade Decision (décision)
Modificateurs : « pricing », « reviews », « demo », « trial », « buy »

Exemple : si le pricing revient dans les calls de vente :
- « Project Management Tool Pricing Comparison »
- « How to Choose the Right Plan »
- « [Product] Reviews »

### Stade Implementation (mise en œuvre)
Modificateurs : « templates », « examples », « tutorial », « how to use », « setup »

Exemple : si les tickets de support montrent des difficultés de mise en œuvre :
- « Project Template Library »
- « Step-by-Step Setup Tutorial »
- « How to Use [Feature] »

---

## Sources d'idéation de contenu

### 1. Données de mots-clés

Si l'utilisateur fournit des exports de mots-clés (Ahrefs, SEMrush, GSC), analyser pour :
- Topic clusters (regrouper les mots-clés liés)
- Stade d'achat (awareness/consideration/decision/implementation)
- Intention de recherche (informationnelle, commerciale, transactionnelle)
- Quick wins (faible concurrence + volume correct + forte pertinence)
- Content gaps (mots-clés sur lesquels les concurrents se positionnent et pas vous)

Sortir un tableau priorisé :
| Mot-clé | Volume | Difficulté | Stade d'achat | Type de contenu | Priorité |

### 2. Transcriptions d'appels

Si l'utilisateur fournit des transcriptions d'appels de vente ou client, extraire :
- Questions posées → contenu FAQ ou articles de blog
- Points de douleur → problèmes dans leurs propres mots
- Objections → contenu pour les traiter de manière proactive
- Patterns de langage → formulations exactes à utiliser (voice of customer)
- Mentions de concurrents → à quoi ils vous ont comparé

Sortir des idées de contenu avec les citations à l'appui.

### 3. Réponses à des sondages

Si l'utilisateur fournit des données de sondage, miner pour :
- Réponses ouvertes (sujets et langage)
- Thèmes communs (30 %+ de mentions = haute priorité)
- Demandes de ressources (ce qu'ils aimeraient voir exister)
- Préférences de contenu (formats souhaités)

### 4. Recherche sur les forums

Utiliser la recherche web pour trouver des idées de contenu :

**Reddit :** `site:reddit.com [topic]`
- Top posts dans les subreddits pertinents
- Questions et frustrations dans les commentaires
- Réponses upvotées (valide ce qui résonne)

**Quora :** `site:quora.com [topic]`
- Questions les plus suivies
- Réponses très upvotées

**Autres :** Indie Hackers, Hacker News, Product Hunt, Slack/Discord sectoriels

Extraire : FAQ, idées reçues, débats, problèmes résolus, terminologie utilisée.

### 5. Analyse concurrentielle

Utiliser la recherche web pour analyser le contenu des concurrents :

**Trouver leur contenu :** `site:competitor.com/blog`

**Analyser :**
- Posts les plus performants (commentaires, partages)
- Sujets couverts à répétition
- Manques qu'ils n'ont pas couverts
- Études de cas (problèmes clients, cas d'usage, résultats)
- Structure de contenu (piliers, catégories, formats)

**Identifier les opportunités :**
- Sujets que vous pouvez mieux couvrir
- Angles qui leur manquent
- Contenu obsolète à améliorer

### 6. Apports des équipes vente et support

Extraire des équipes au contact des clients :
- Objections fréquentes
- Questions répétées
- Patterns de tickets de support
- Success stories
- Demandes de fonctionnalités et problèmes sous-jacents

---

## Prioriser les idées de contenu

Scorer chaque idée sur quatre facteurs :

### 1. Impact client (40 %)
- À quelle fréquence ce sujet est-il revenu dans la recherche ?
- Quel pourcentage de clients fait face à ce défi ?
- À quel point ce point de douleur était-il chargé émotionnellement ?
- Quelle est la LTV potentielle des clients ayant ce besoin ?

### 2. Content-Market Fit (30 %)
- Cela s'aligne-t-il avec les problèmes que votre produit résout ?
- Pouvez-vous offrir des insights uniques issus de la recherche client ?
- Avez-vous des stories clients pour appuyer ça ?
- Cela mènera-t-il naturellement à un intérêt produit ?

### 3. Potentiel de recherche (20 %)
- Quel est le volume de recherche mensuel ?
- À quel point ce sujet est-il concurrentiel ?
- Y a-t-il des opportunités de longue traîne liées ?
- L'intérêt de recherche croît-il ou décline-t-il ?

### 4. Ressources requises (10 %)
- Avez-vous l'expertise pour créer un contenu faisant autorité ?
- Quelle recherche supplémentaire est nécessaire ?
- Quels assets (visuels, données, exemples) vous faudra-t-il ?

### Template de scoring

| Idée | Impact client (40 %) | Content-Market Fit (30 %) | Potentiel de recherche (20 %) | Ressources (10 %) | Total |
|------|----------------------|-------------------------|----------------------|-----------------|-------|
| Sujet A | 8 | 9 | 7 | 6 | 8.0 |
| Sujet B | 6 | 7 | 9 | 8 | 7.1 |

---

## Format de sortie

Lors de la création d'une stratégie de contenu, fournir :

### 1. Content pillars
- 3-5 piliers avec justification
- Clusters de sous-sujets pour chaque pilier
- Comment les piliers se connectent au produit

### 2. Sujets prioritaires
Pour chaque pièce recommandée :
- Sujet/titre
- Searchable, shareable, ou les deux
- Type de contenu (cas d'usage, hub/spoke, thought leadership, etc.)
- Mot-clé cible et stade d'achat
- Pourquoi ce sujet (appui de la recherche client)

### 3. Carte des topic clusters
Représentation visuelle ou structurée de la façon dont le contenu s'interconnecte.

---

## Questions spécifiques à la tâche

1. Quels patterns émergent de vos 10 dernières conversations clients ?
2. Quelles questions reviennent sans cesse dans les calls de vente ?
3. Où les efforts de contenu des concurrents sont-ils en deçà ?
4. Quels insights uniques de la recherche client ne sont partagés nulle part ailleurs ?
5. Quel contenu existant génère le plus de conversions, et pourquoi ?

---

## Références

- **[Guide Headless CMS](references/headless-cms.md)** : choix du CMS, modélisation de contenu pour le marketing, workflows éditoriaux, comparatif de plateformes (Sanity, Contentful, Strapi)

---

## Skills liés

- **copywriting** : pour rédiger des pièces de contenu individuelles
- **seo-audit** : pour le SEO technique et l'optimisation on-page
- **ai-seo** : pour optimiser le contenu pour les moteurs de recherche IA et se faire citer par les LLM
- **programmatic-seo** : pour la génération de contenu à l'échelle
- **site-architecture** : pour la hiérarchie de pages, le design de navigation et la structure d'URL
- **emails** : pour le contenu par email
- **social** : pour le contenu réseaux sociaux
