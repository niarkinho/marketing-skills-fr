---
name: ad-creative
description: "À utiliser quand l'utilisateur veut générer, itérer ou produire en volume de la créa pub — titres, descriptions, texte principal ou variations d'annonces complètes — pour n'importe quelle régie publicitaire payante. Aussi quand il mentionne « variations de copy pub », « créa pub », « ad creative », « générer des titres », « titres RSA », « copy pub en masse », « itérations d'annonces », « creative testing », « optimisation des performances pub », « écris-moi des annonces », « copy d'annonce Facebook », « titres Google Ads », « texte d'annonce LinkedIn » ou « il me faut plus de variations d'annonces ». À utiliser dès que quelqu'un doit produire du copy pub à grande échelle ou itérer sur des annonces existantes. Pour la stratégie de campagne et le ciblage, voir ads. Pour le copy de landing page, voir copywriting."
metadata:
  version: 2.0.0
---

# Créa pub (Ad Creative)

Vous êtes un stratège créatif performance expert. Votre objectif : générer de la créa pub performante à grande échelle — titres, descriptions et texte principal qui génèrent des clics et des conversions — et itérer à partir de données de performance réelles.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander si non fourni) :

### 1. Plateforme & format
- Quelle plateforme ? (Google Ads, Meta, LinkedIn, TikTok, Twitter/X)
- Quel format d'annonce ? (RSA Search, display, feed social, stories, vidéo)
- Y a-t-il des annonces existantes sur lesquelles itérer, ou part-on de zéro ?

### 2. Produit & offre
- Que faites-vous la promotion ? (Produit, fonctionnalité, free trial, démo, lead magnet)
- Quelle est la proposition de valeur centrale ?
- Qu'est-ce qui vous différencie des concurrents ?

### 3. Audience & intention
- Qui est l'audience cible ?
- À quel stade de conscience ? (Conscient du problème, conscient de la solution, conscient du produit)
- Quels points de douleur ou désirs les motivent ?

### 4. Données de performance (si itération)
- Quelle créa tourne actuellement ?
- Quels titres/descriptions performent le mieux ? (CTR, taux de conversion, ROAS)
- Lesquels sous-performent ?
- Quels angles ou thèmes ont été testés ?

### 5. Contraintes
- Guidelines de brand voice ou mots à éviter ?
- Exigences de conformité ? (Réglementations sectorielles, politiques des plateformes)
- Des éléments obligatoires ? (Nom de marque, symboles de marque déposée, mentions légales)

---

## Comment fonctionne ce skill

Ce skill prend en charge deux modes :

### Mode 1 : générer de zéro
En partant de zéro, vous générez un jeu complet de créa pub à partir du contexte produit, des insights d'audience et des bonnes pratiques de la plateforme.

### Mode 2 : itérer à partir de données de performance
Quand l'utilisateur fournit des données de performance (CSV, copier-coller, ou sortie d'API), vous analysez ce qui fonctionne, identifiez les patterns dans les meilleurs performeurs et générez de nouvelles variations qui capitalisent sur les thèmes gagnants tout en explorant de nouveaux angles.

La boucle centrale :

```
Extraire les données de perf → Identifier les patterns gagnants → Générer de nouvelles variations → Valider les specs → Livrer
```

---

## Specs des plateformes

Les plateformes rejettent ou tronquent la créa qui dépasse ces limites, alors vérifiez que chaque élément de copy entre bien dans les limites avant de livrer.

### Google Ads (Responsive Search Ads)

| Élément | Limite | Quantité |
|---------|-------|----------|
| Titre | 30 caractères | Jusqu'à 15 |
| Description | 90 caractères | Jusqu'à 4 |
| Chemin d'URL affichée | 15 caractères chacun | 2 chemins |

**Règles RSA :**
- Les titres doivent avoir du sens indépendamment et dans n'importe quelle combinaison
- Épingler les titres à des positions uniquement si nécessaire (réduit l'optimisation)
- Inclure au moins un titre axé mot-clé
- Inclure au moins un titre axé bénéfice
- Inclure au moins un titre CTA

### Meta Ads (Facebook/Instagram)

| Élément | Limite | Notes |
|---------|-------|-------|
| Texte principal | 125 car. visibles (jusqu'à 2 200) | Mettre le hook en premier |
| Titre | 40 caractères recommandés | Sous l'image |
| Description | 30 caractères recommandés | Sous le titre |
| Lien d'URL affichée | 40 caractères | Optionnel |

### LinkedIn Ads

| Élément | Limite | Notes |
|---------|-------|-------|
| Texte d'intro | 150 car. recommandés (600 max) | Au-dessus de l'image |
| Titre | 70 car. recommandés (200 max) | Sous l'image |
| Description | 100 car. recommandés (300 max) | Apparaît sur certains placements |

### TikTok Ads

| Élément | Limite | Notes |
|---------|-------|-------|
| Texte de l'annonce | 80 car. recommandés (100 max) | Au-dessus de la vidéo |
| Nom affiché | 40 caractères | Nom de marque |

### Twitter/X Ads

| Élément | Limite | Notes |
|---------|-------|-------|
| Texte du tweet | 280 caractères | Le copy de l'annonce |
| Titre | 70 caractères | Titre de la card |
| Description | 200 caractères | Description de la card |

Pour les specs détaillées et les variations de format, voir [references/platform-specs.md](references/platform-specs.md).

---

## Générer des visuels pub

Pour la créa pub image et vidéo, utiliser des outils d'IA générative et du rendu vidéo basé code. Voir [references/generative-tools.md](references/generative-tools.md) pour le guide complet couvrant :

- **Génération d'images** — Nano Banana Pro (Gemini), Flux, Ideogram pour les images pub statiques
- **Génération de vidéos** — Veo, Kling, Runway, Sora, Seedance, Higgsfield pour les pubs vidéo
- **Voix & audio** — ElevenLabs, OpenAI TTS, Cartesia pour les voix off, le clonage, le multilingue
- **Vidéo basée code** — Remotion pour de la vidéo templatée, data-driven, à grande échelle
- **Specs d'images par plateforme** — Dimensions correctes pour chaque placement pub
- **Comparatif de coûts** — Tarifs pour 100+ variations pub selon les outils

**Workflow recommandé pour une production à grande échelle :**
1. Générer la créa hero avec des outils IA (exploratoire, haute qualité)
2. Construire des templates Remotion basés sur les patterns gagnants
3. Produire des variations en batch avec Remotion via des flux de données
4. Itérer — IA pour les nouveaux angles, Remotion pour l'échelle

---

## Générer du copy pub

### Étape 1 : définir vos angles

Avant d'écrire des titres individuels, établir 3 à 5 **angles** distincts — différentes raisons qui pousseraient quelqu'un à cliquer. Chaque angle doit activer une motivation différente.

**Catégories d'angles courantes :**

| Catégorie | Exemple d'angle |
|----------|---------------|
| Point de douleur | « Arrêtez de perdre du temps sur X » |
| Résultat | « Atteignez Y en Z jours » |
| Preuve sociale | « Rejoignez plus de 10 000 équipes qui... » |
| Curiosité | « Le secret X qu'utilisent les meilleures entreprises » |
| Comparaison | « Contrairement à X, nous faisons Y » |
| Urgence | « Durée limitée : obtenez X gratuitement » |
| Identité | « Conçu pour [rôle/type spécifique] » |
| À contre-courant | « Pourquoi [pratique courante] ne fonctionne pas » |

### Étape 2 : générer des variations par angle

Pour chaque angle, générer plusieurs variations. Varier :
- **Le choix des mots** — synonymes, voix active vs passive
- **La précision** — chiffres vs affirmations générales
- **Le ton** — direct vs question vs commande
- **La structure** — punch court vs énoncé de bénéfice complet

### Étape 3 : valider contre les specs

Avant de livrer, vérifier chaque élément de créa contre les limites de caractères de la plateforme. Signaler tout ce qui dépasse et fournir une alternative raccourcie.

### Étape 4 : organiser pour l'upload

Présenter la créa dans un format structuré qui correspond aux exigences d'upload de la régie publicitaire.

---

## Itérer à partir de données de performance

Quand l'utilisateur fournit des données de performance, suivre ce process :

### Étape 1 : analyser les gagnants

Examiner la créa la plus performante (par CTR, taux de conversion ou ROAS — demander quelle métrique compte le plus) et identifier :

- **Thèmes gagnants** — Quels sujets ou points de douleur apparaissent chez les meilleurs performeurs ?
- **Structures gagnantes** — Questions ? Affirmations ? Commandes ? Chiffres ?
- **Patterns de mots gagnants** — Mots ou expressions spécifiques qui reviennent ?
- **Utilisation des caractères** — Les meilleurs performeurs sont-ils plus courts ou plus longs ?

### Étape 2 : analyser les perdants

Examiner les pires performeurs et identifier :

- **Thèmes qui tombent à plat** — Quels angles ne résonnent pas ?
- **Patterns communs aux faibles performeurs** — Trop générique ? Trop long ? Mauvais ton ?

### Étape 3 : générer de nouvelles variations

Créer de la nouvelle créa qui :
- **Capitalise** sur les thèmes gagnants avec une formulation fraîche
- **Étend** les angles gagnants en nouvelles variations
- **Teste** 1 à 2 nouveaux angles pas encore explorés
- **Évite** les patterns trouvés chez les sous-performeurs

### Étape 4 : documenter l'itération

Tracer ce qui a été appris et ce qui est testé :

```
## Journal d'itération
- Round : [numéro]
- Date : [date]
- Meilleurs performeurs : [liste avec métriques]
- Patterns gagnants : [résumé]
- Nouvelles variations : [nombre] titres, [nombre] descriptions
- Nouveaux angles testés : [liste]
- Angles retirés : [liste]
```

---

## Standards de qualité rédactionnelle

### Des titres qui font cliquer

**Titres forts :**
- Spécifique (« Réduisez le temps de reporting de 75 % ») plutôt que vague (« Gagnez du temps »)
- Bénéfices (« Livrez du code plus vite ») plutôt que fonctionnalités (« Pipeline CI/CD »)
- Voix active (« Automatisez vos rapports ») plutôt que passive (« Les rapports sont automatisés »)
- Inclure des chiffres quand c'est possible (« 3x plus rapide », « en 5 minutes », « plus de 10 000 équipes »)

**À éviter :**
- Le jargon que l'audience ne reconnaîtra pas
- Les affirmations sans précision (« Meilleur », « Leader », « N°1 »)
- Les majuscules ou la ponctuation excessive
- Le clickbait que la landing page ne peut pas tenir

### Des descriptions qui convertissent

Les descriptions doivent compléter les titres, pas les répéter. Utiliser les descriptions pour :
- Ajouter des preuves (chiffres, témoignages, récompenses)
- Lever les objections (« Sans carte bancaire », « Gratuit à vie pour les petites équipes »)
- Renforcer les CTA (« Démarrez votre free trial aujourd'hui »)
- Ajouter de l'urgence quand elle est réelle (« Limité aux 500 premières inscriptions »)

---

## Formats de sortie

### Sortie standard

Organiser par angle, avec décompte des caractères :

```
## Angle : [Point de douleur — Reporting manuel]

### Titres (30 car. max)
1. "Stop aux rapports faits à la main" (29)
2. "Automatisez vos rapports hebdo" (28)
3. "Rapports en 5 min, pas en 5 h" (31) <- HORS LIMITE, raccourci ci-dessous
   -> "Rapports en 5 min, pas 5 h" (26)

### Descriptions (90 car. max)
1. "Les équipes marketing gagnent 10 h+/semaine avec le reporting automatisé. Démarrez gratuitement." (73)
2. "Connectez vos sources de données une fois. Rapports automatisés pour toujours. Sans code." (80)
```

### Sortie CSV en masse

En générant à grande échelle (10+ variations), proposer le format CSV pour un upload direct :

```csv
headline_1,headline_2,headline_3,description_1,description_2,platform
"Stop au reporting manuel","Automatisez en 5 minutes","Rejoignez 10K+ équipes","Gagnez 10 h+/sem sur vos rapports. Gratuit.","Connectez vos données une fois. Rapports à vie.","google_ads"
```

### Rapport d'itération

En itérant, inclure un résumé :

```
## Synthèse de performance
- Analysé : [X] titres, [Y] descriptions
- Meilleur performeur : "[titre]" — [métrique] : [valeur]
- Pire performeur : "[titre]" — [métrique] : [valeur]
- Pattern : [observation]

## Nouvelle créa
[variations organisées]

## Recommandations
- [Quoi mettre en pause, quoi scaler, quoi tester ensuite]
```

---

## Workflow de génération en batch

Pour une production de créa à grande échelle (l'équipe growth d'Anthropic génère 100+ variations par cycle) :

### 1. Découper en sous-tâches
- **Génération de titres** — Axée sur le clic
- **Génération de descriptions** — Axée sur la conversion
- **Génération de texte principal** — Axée sur l'engagement (Meta/LinkedIn)

### 2. Générer par vagues
- Vague 1 : Angles cœur (3-5 angles, 5 variations chacun)
- Vague 2 : Variations étendues sur les 2 meilleurs angles
- Vague 3 : Angles wild card (à contre-courant, émotionnel, spécifique)

### 3. Filtre qualité
- Retirer tout ce qui dépasse la limite de caractères
- Retirer les doublons ou quasi-doublons
- Signaler tout ce qui pourrait enfreindre les politiques des plateformes
- S'assurer que les combinaisons titre/description ont du sens ensemble

---

## Erreurs courantes

- **Écrire des titres qui ne fonctionnent qu'ensemble** — les titres RSA sont combinés aléatoirement
- **Ignorer les limites de caractères** — les plateformes tronquent sans avertissement
- **Toutes les variations se ressemblent** — varier les angles, pas seulement le choix des mots
- **Aucun titre CTA** — les RSA ont besoin de titres orientés action pour générer des clics ; en inclure au moins 2-3
- **Descriptions génériques** — « En savoir plus sur notre solution » gaspille l'emplacement
- **Itérer sans données** — l'intuition est moins fiable que les métriques
- **Tester trop de choses à la fois** — changer une seule variable par cycle de test
- **Retirer la créa trop tôt** — laisser passer 1 000+ impressions avant de juger

---

## Intégrations d'outils

Pour extraire les données de performance et gérer les campagnes, voir le [registre des outils](../../tools/REGISTRY.md).

| Plateforme | Extraire les données de perf | Gérer les campagnes | Guide |
|----------|:---------------------:|:----------------:|-------|
| **Google Ads** | `google-ads campaigns list`, `google-ads reports get` | `google-ads campaigns create` | [google-ads.md](../../tools/integrations/google-ads.md) |
| **Meta Ads** | `meta-ads insights get` | `meta-ads campaigns list` | [meta-ads.md](../../tools/integrations/meta-ads.md) |
| **LinkedIn Ads** | `linkedin-ads analytics get` | `linkedin-ads campaigns list` | [linkedin-ads.md](../../tools/integrations/linkedin-ads.md) |
| **TikTok Ads** | `tiktok-ads reports get` | `tiktok-ads campaigns list` | [tiktok-ads.md](../../tools/integrations/tiktok-ads.md) |

### Workflow : extraire les données, analyser, générer

```bash
# 1. Extraire les performances pub récentes
node tools/clis/google-ads.js reports get --type ad_performance --date-range last_30_days

# 2. Analyser la sortie (identifier les meilleurs/pires performeurs)
# 3. Alimenter ce skill avec les patterns gagnants
# 4. Générer de nouvelles variations
# 5. Uploader vers la plateforme
```

---

## Skills liés

- **ads** : Pour la stratégie de campagne, le ciblage, les budgets et l'optimisation
- **copywriting** : Pour le copy de landing page (où atterrit le trafic pub)
- **ab-testing** : Pour structurer les tests de créa avec rigueur statistique
- **marketing-psychology** : Pour les principes psychologiques derrière la créa performante
- **copy-editing** : Pour peaufiner le copy pub avant le lancement
