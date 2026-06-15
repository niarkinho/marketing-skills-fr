---
name: aso
description: "À utiliser quand l'utilisateur veut auditer ou optimiser une fiche App Store ou Google Play. Aussi quand il mentionne « audit ASO », « app store optimization », « optimiser ma fiche app », « améliorer la visibilité de mon app », « classement app store », « auditer ma fiche », « pourquoi personne ne télécharge mon app », « améliorer la conversion de mon app », « optimisation de mots-clés pour app », « optimiser ma fiche store » ou « comparer mon app aux concurrents ». À utiliser quand l'utilisateur partage une URL App Store ou Google Play et veut l'améliorer."
metadata:
  version: 2.0.0
---

# Audit ASO

Analyser les fiches App Store et Google Play à l'aune des bonnes pratiques ASO.
Récupère les données live de la fiche, score les métadonnées, les visuels et les
notes, puis produit un plan d'action priorisé.

## Quand l'utiliser

- L'utilisateur partage une URL App Store ou Google Play
- L'utilisateur demande d'auditer ou d'optimiser une fiche app
- L'utilisateur veut comparer son app à celles de concurrents
- L'utilisateur pose une question sur le classement, la visibilité ou la conversion en téléchargements

## Avant l'audit

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

## Phase 1 — Identifier le store et récupérer

### Détecter le type de store depuis l'URL

```
Apple:  apps.apple.com/{country}/app/{name}/id{digits}
Google: play.google.com/store/apps/details?id={package}
```

Si l'utilisateur donne un nom d'app plutôt qu'une URL, chercher sur le web :
`site:apps.apple.com "{nom de l'app}"` ou `site:play.google.com "{nom de l'app}"`

### Récupérer la fiche

Utiliser WebFetch pour récupérer la page de la fiche. Extraire tous les champs disponibles :

**Champs Apple App Store :**

- Nom de l'app (titre) — limite 30 car.
- Sous-titre — limite 30 car.
- Description (longue) — non indexée pour la recherche, mais compte pour la conversion
- Texte promotionnel — 170 car., modifiable sans nouvelle version
- Catégorie (principale + secondaire)
- Captures d'écran (nombre, ordre, texte des légendes)
- Vidéo de présentation (présence, durée)
- Note (moyenne + nombre)
- Avis récents (ceux visibles)
- Prix / achats intégrés
- Nom du développeur
- Date de dernière mise à jour
- Notes de l'historique des versions
- Classification d'âge
- Taille
- Langues / localisations listées
- In-app events (si visibles)

**Champs Google Play :**

- Nom de l'app (titre) — limite 30 car.
- Description courte — limite 80 car.
- Description complète — limite 4 000 car., EST indexée pour la recherche
- Catégorie + tags
- Image de présentation (feature graphic) (présence)
- Captures d'écran (nombre, ordre)
- Vidéo de présentation (présence)
- Note (moyenne + nombre)
- Avis récents (ceux visibles)
- Prix / achats intégrés
- Nom du développeur
- Date de dernière mise à jour
- Texte « Nouveautés »
- Tranche de téléchargements
- Classification du contenu
- Section sécurité des données
- Langues listées

Si WebFetch renvoie des données incomplètes (les stores font du rendu côté client), noter les
lacunes et travailler avec ce qui est disponible. Demander à l'utilisateur de coller les champs
manquants s'ils sont critiques.

### Évaluation des visuels

WebFetch ne peut pas extraire les images des captures d'écran ni le texte des légendes. **Prendre
une capture d'écran de la page de la fiche** pour obtenir les données visuelles :

1. Naviguer vers l'URL de la fiche et capturer une capture pleine page
2. Évaluer la capture pour : qualité de l'icône, nombre de captures, texte des légendes,
   qualité du message, présence de vidéo de présentation, feature graphic (Google Play)
3. Si les outils navigateur ne sont pas disponibles, demander à l'utilisateur de partager une capture de la
   page de la fiche

**Texte promotionnel (Apple) :** ce champ de 170 car. apparaît au-dessus de la description
mais est souvent indistinct de celle-ci dans le HTML scrapé. Si vous ne pouvez pas confirmer
sa présence, le noter et recommander à l'utilisateur de vérifier dans App Store Connect.

---

## Phase 1.5 — Évaluer la maturité de la marque

Avant de scorer, classer l'app dans l'un des trois paliers. Cela détermine comment
interpréter les écarts à « l'ASO du manuel » — un choix de marque délibéré par un
nom connu n'est pas la même chose qu'une opportunité ratée par une app inconnue.

### Définitions des paliers

| Palier          | Signaux                                                                                                                              | Exemples                                    |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------- |
| **Dominant**    | Nom connu du grand public, 1M+ notes, top-10 de sa catégorie, reconnaissance de marque quasi universelle. Les utilisateurs cherchent par nom de marque, pas par mots-clés génériques. | Instagram, Uber, Spotify, WhatsApp, Netflix |
| **Établi**      | Bien connu dans sa catégorie, 100K+ notes, fort volume d'installs organiques, marque reconnue mais pas universellement.              | Strava, Notion, Duolingo, Cash App, Calm    |
| **Challenger**  | En construction de notoriété, <100K notes, a besoin d'être découvert via les mots-clés et les tactiques ASO. La plupart des apps sont ici. | Votre app, la plupart des apps indé/startup |

### Comment le palier affecte le scoring

**Les apps Dominantes** bénéficient d'un scoring ajusté dans ces domaines :

- **Titre :** les titres marque-seule ou marque-d'abord sont valides (score 8+ si la marque est le mot-clé). Ces apps n'ont pas besoin de la découverte par mots-clés génériques.
- **Description :** scorer uniquement sur la qualité de conversion, pas la présence de mots-clés. Si l'app est un nom connu, une description de marque bien rédigée bat une description bourrée de mots-clés.
- **Visuels :** la photographie lifestyle/de marque au lieu de démos d'UI est une stratégie de conversion légitime. L'absence de vidéo est acceptable si le produit est difficile à démontrer en 30 s ou si la notoriété de marque est quasi universelle.
- **Nouveautés :** des notes de version génériques à une cadence hebdomadaire+ sont acceptables (score 8+). À grande échelle, des changelogs détaillés ont un ROI minime et risquent un retour de bâton.
- **In-app events :** l'absence d'events pour des apps utilitaires à très large base installée (Uber, WhatsApp) n'est pas une pénalité. Ces apps n'ont pas besoin d'aide à la découverte.
- **Localisation :** scorer relativement au marché réel, pas au nombre absolu. Une fintech US-only avec 2 langues (anglais + espagnol) est correctement localisée.

**Les apps Établies** bénéficient d'un ajustement partiel :

- Les titres marque-d'abord conviennent mais doivent quand même inclure 1-2 mots-clés
- Les choix stratégiques de description bénéficient du doute
- Les autres dimensions sont scorées normalement

**Les apps Challenger** sont scorées strictement à l'aune des bonnes pratiques ASO du manuel — chaque caractère, chaque capture et chaque mot-clé compte.

**Principe clé :** avant de retirer des points, se demander : « Est-ce une erreur ou un choix
délibéré d'une équipe qui a des données que je n'ai pas ? » Si l'app a 1M+ notes et une
équipe ASO dédiée, supposer que leurs choix sont guidés par les données sauf erreur manifeste.

---

## Phase 2 — Scorer chaque dimension

Scorer chaque dimension de 0 à 10 en utilisant les critères de `references/scoring-criteria.md`.
Appliquer les ajustements de palier de maturité de marque de la Phase 1.5.

Fichiers de référence pour les specs plateformes et les benchmarks :

- `references/apple-specs.md` — Limites de caractères officielles Apple, specs captures/vidéo, règles CPP/PPO, déclencheurs de rejet
- `references/google-play-specs.md` — Limites officielles Google Play, specs captures, seuils Android Vitals, règles
- `references/benchmarks.md` — Données de conversion, impact des notes, lift vidéo, comportement captures, benchmarks CPP/events

### Dimensions et pondérations

| #   | Dimension            | Pondération | Ce que ça couvre                                                          |
| --- | -------------------- | ----------- | ------------------------------------------------------------------------- |
| 1   | Titre et sous-titre  | 20%         | Usage des caractères, présence de mots-clés, clarté, équilibre marque + mots-clés |
| 2   | Description          | 15%         | 3 premières lignes, densité de mots-clés (Google), CTA, structure, texte promotionnel |
| 3   | Visuels              | 25%         | Nombre/qualité/message des captures, vidéo, icône, feature graphic        |
| 4   | Notes et avis        | 20%         | Note moyenne, volume, récence, réponses du développeur                    |
| 5   | Métadonnées et fraîcheur | 10%     | Choix de catégorie, récence des mises à jour, nombre de localisations, sécurité des données |
| 6   | Signaux de conversion | 10%        | Positionnement prix, transparence des achats intégrés, preuve sociale, tranche de téléchargements |

**Score final** = somme pondérée, sur 100.

### Interprétation du score

| Score  | Note  | Signification                                                  |
| ------ | ----- | --------------------------------------------------------------- |
| 85-100 | A     | Bien optimisé ; se concentrer sur l'A/B testing et l'itération |
| 70-84  | B     | Bonne fondation ; opportunités d'amélioration claires          |
| 50-69  | C     | Lacunes significatives ; les corrections priorisées auront un fort impact |
| 30-49  | D     | Optimisation majeure nécessaire sur plusieurs dimensions       |
| 0-29   | F     | La fiche nécessite une refonte complète                        |

---

## Phase 3 — Comparaison concurrentielle (optionnel)

Si l'utilisateur fournit des URL de concurrents ou demande une comparaison :

1. Récupérer 2-3 concurrents leaders dans la même catégorie
2. Appliquer le même scoring à chacun
3. Construire un tableau comparatif mettant en évidence où l'app de l'utilisateur est plus faible/forte
4. Identifier les écarts de mots-clés — termes sur lesquels les concurrents se positionnent mais que l'app de l'utilisateur ne cible pas

Si aucun concurrent n'est précisé, suggérer à l'utilisateur d'en fournir 2-3 ou proposer de chercher
les apps leaders de sa catégorie.

---

## Phase 4 — Générer le rapport

Utiliser le modèle de `references/report-template.md` pour structurer la sortie.

Le rapport doit inclure :

1. **Carte de score** — tableau avec les 6 dimensions, scores et note
2. **Top 3 des quick wins** — changements qui prennent <1 heure et ont le plus fort impact
3. **Constats détaillés** — analyse par dimension avec problèmes spécifiques et correctifs
4. **Suggestions de mots-clés** — basées sur l'analyse titre/description et les écarts concurrentiels
5. **Recommandations de visuels** — améliorations spécifiques captures/vidéo
6. **Plan d'action priorisé** — liste ordonnée des changements par impact vs effort

### Règles du rapport

- Chaque recommandation doit être **spécifique et actionnable** (« Changer le sous-titre de X à Y » et non « Améliorer le sous-titre »)
- Inclure le nombre de caractères pour toutes les recommandations de texte
- Signaler les différences spécifiques aux plateformes (Apple vs Google) quand c'est pertinent
- Noter ce qui NE PEUT PAS être évalué sans outils payants (volume de recherche, classements exacts)
- Quand on suggère des changements de mots-clés, expliquer POURQUOI chaque mot-clé compte

---

## Règles spécifiques aux plateformes

### Apple App Store — Faits clés

- Titre (30 car.) + Sous-titre (30 car.) + Champ mots-clés (100 **octets**, caché) = texte indexé
- Le champ mots-clés est en octets, pas en caractères — l'arabe/CJK utilise 2-3 octets par caractère
- La description longue n'est PAS indexée pour la recherche — l'optimiser pour la conversion uniquement
- Le texte promotionnel (170 car.) n'affecte PAS la recherche (confirmé par Apple)
- Ne jamais répéter de mots entre titre/sous-titre/champ mots-clés (Apple indexe chaque mot une fois)
- Champ mots-clés : virgules, sans espaces (« photo,editor,filter » et non « photo, editor, filter »)
- Captures : jusqu'à 10 par appareil. Les 3 premières visibles en recherche — 90% ne scrollent jamais au-delà de la 3e
- Légendes des captures indexées depuis juin 2025 (extraction IA)
- In-app events : max 10 publiés à la fois, max 31 jours chacun. Indexés et apparaissent en recherche
- Custom Product Pages (jusqu'à 70) en recherche organique depuis juillet 2025. +5,9% de lift de conversion moyen
- Vidéo de présentation : jusqu'à 3, 15-30 s chacune. Lecture auto en muet — +20-40% de lift de conversion
- SKStoreReviewController : max 3 invites par 365 jours
- Apple a une curation éditoriale humaine — la qualité et le design comptent davantage
- Voir `references/apple-specs.md` pour les specs complètes, dimensions et déclencheurs de rejet

### Google Play — Faits clés

- Titre (30 car.) + Description courte (80 car.) + Description complète (4 000 car.) = texte indexé
- La description complète EST indexée — viser 2-3% de densité de mots-clés naturellement
- Pas de champ mots-clés caché — tous les mots-clés doivent être dans le texte visible
- Compréhension NLP/sémantique de Google — le bourrage de mots-clés est détecté et pénalisé
- Interdit dans le titre : emojis, MAJUSCULES, « best »/« #1 »/« free », CTA (appliqué depuis 2021)
- Captures : min 2, **max 8** par appareil (pas 10 comme Apple)
- Feature graphic (1024x500, exact) requise pour les placements en avant
- La vidéo NE se lance PAS automatiquement — seulement ~6% des utilisateurs lancent la lecture (faible ROI vs iOS)
- Android Vitals affectent directement le classement : crash >1,09% ou ANR >0,47% = visibilité réduite
- Contenu promotionnel : soumettre 14 jours en avance pour la mise en avant. Les apps voient 2x plus d'acquisitions explore
- Custom Store Listings : jusqu'à 50 (peuvent cibler les utilisateurs churned, des pays spécifiques, des campagnes pub)
- Store Listing Experiments : tester jusqu'à 3 variantes, sur 7+ jours, 1 expérience à la fois
- Voir `references/google-play-specs.md` pour les specs complètes et les détails de règles

### Ce qu'Apple indexe vs ce que Google indexe

| Champ                  | Apple indexe ?   | Google indexe ?        |
| ---------------------- | ---------------- | ---------------------- |
| Titre                  | Oui              | Oui (signal le plus fort) |
| Sous-titre / Desc. courte | Oui           | Oui                    |
| Champ mots-clés        | Oui (caché)      | N'existe pas           |
| Description longue     | Non              | Oui (fortement)        |
| Légendes des captures  | Oui (depuis 2025) | Non                   |
| In-app events          | Oui              | N/A (LiveOps à la place) |
| Nom du développeur     | Non              | Partiel                |
| Noms des achats intégrés | Oui            | Oui                    |

---

## Checklist des problèmes courants

Signaler ceux-ci si trouvés. Les items marqués _(dépendant du palier)_ doivent être évalués à l'aune
du palier de maturité de marque de l'app — ils peuvent être des choix délibérés pour les apps Dominantes.

**Toujours signaler (tous paliers) :**

- [ ] Note sous 4,0
- [ ] Dernière mise à jour > 3 mois
- [ ] La description Google Play n'a pas de stratégie de mots-clés (sous 1% de densité)
- [ ] Feature graphic manquante sur Google Play
- [ ] Le champ mots-clés Apple a probablement des mots répétés (déduit du titre+sous-titre)
- [ ] Mauvaise catégorie — l'app affronterait moins de concurrence dans une autre catégorie
- [ ] Moins de 5 captures d'écran

**Signaler pour Challenger/Établi uniquement** _(pas des erreurs pour les apps Dominantes) :_

- [ ] Le titre gaspille des caractères sur le seul nom de marque (pas de mots-clés) _(Dominant : la marque EST le mot-clé)_
- [ ] Le sous-titre/description courte duplique les mots-clés du titre
- [ ] Les 3 premières lignes de la description sont génériques _(Dominant : peut être un choix de voix de marque)_
- [ ] Pas de vidéo de présentation _(Dominant : peut être rationnel si le produit est difficile à démontrer)_
- [ ] Les captures sont de simples dumps d'UI sans message/légende _(Dominant : les visuels lifestyle/marque peuvent mieux convertir)_
- [ ] Seulement 1-2 localisations _(scorer relativement au marché réel, pas au nombre absolu)_
- [ ] Pas d'in-app events ni de contenu promotionnel _(les apps utilitaires Dominantes peuvent ne pas avoir besoin d'aide à la découverte)_

**Signaler pour tous les paliers mais noter le contexte :**

- [ ] Pas de réponses du développeur aux avis négatifs _(noter le volume — répondre à 10M+ avis est un défi différent qu'à 1K)_
- [ ] Texte « Nouveautés » générique _(acceptable à une cadence de release hebdomadaire+ pour Établi/Dominant)_

---

## Questions spécifiques à la tâche

1. Quelle est l'URL App Store ou Google Play ?
2. Est-ce votre app ou celle d'un concurrent ?
3. Dans quelle catégorie l'app est-elle en concurrence ?
4. Avez-vous des URL de concurrents pour comparer ?
5. Êtes-vous concentré sur la visibilité en recherche, le taux de conversion, ou les deux ?
6. Avez-vous accès aux données d'App Store Connect ou de Google Play Console ?

---

## Skills liés

- **cro** : pour optimiser la conversion des landing pages web qui génèrent des installs d'app
- **ad-creative** : pour créer des créas pub App Store et Google Play
- **analytics** : pour mettre en place l'attribution d'installs et le tracking d'in-app events
- **customer-research** : pour comprendre les besoins et le langage des utilisateurs afin d'orienter le copy de la fiche
