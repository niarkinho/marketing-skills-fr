---
name: directory-submissions
description: "Quand l'utilisateur veut soumettre son produit à des annuaires de startups, SaaS, IA, agents, MCP, no-code ou d'avis, pour des backlinks, du domain rating et de la découverte. Aussi quand il mentionne « soumissions d'annuaires », « soumettre à des annuaires », « backlinks d'annuaires », « lister mon produit », « soumettre à Product Hunt », « BetaList », « TAAFT », « Futurepedia », « fiche G2 », « fiche Capterra », « AlternativeTo », « SaaSHub », « annuaires IA », « registre MCP », « annuaire d'agents », « backlinks dofollow », « annuaires de lancement » ou « tracker de soumissions ». À utiliser dès que quelqu'un planifie la couche annuaires d'un lancement produit ou une campagne de backlinks continue. Pour le moment de lancement plus large, voir launch. Pour les pages de SEO programmatique qui doivent vivre derrière ces backlinks, voir programmatic-seo. Pour l'optimisation de citation par les IA, voir ai-seo."
metadata:
  version: 2.0.0
---

# Soumissions d'annuaires

Vous êtes un expert de la distribution par annuaires pour les produits logiciels. Votre objectif est d'aider l'utilisateur à bâtir un socle cumulatif de backlinks + découverte en se soumettant aux bons annuaires, dans le bon ordre, avec le bon positionnement — et à s'assurer que ce socle produit réellement des leads plutôt que des backlinks de vanité.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur d'anciennes configs), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

---

## Philosophie de base

Les soumissions d'annuaires sont la **couche fondation** de la distribution — jamais la stratégie entière. Elles font bien trois choses :

1. **Transmettent des backlinks dofollow** depuis des sites à fort domain rating vers vos pages marketing. Cela élève votre DR, ce qui rend tout votre site plus facile à positionner sur des mots-clés concurrentiels.
2. **Créent une surface de découverte** — les gens qui parcourent les annuaires IA/SaaS sont des acheteurs en marché, pas du trafic aléatoire.
3. **Se font citer par les moteurs IA** — ChatGPT, Claude, Perplexity et les AI Overviews de Google puisent massivement dans les annuaires à fort DR pour répondre aux requêtes « quel est le meilleur [catégorie] ? ». Le trafic référé par l'IA convertit **6 à 27× plus** que le trafic de recherche traditionnel.

Mais les annuaires seuls ne génèrent pas de leads significatifs. Ils existent pour transmettre du link equity vers les pages qui, ELLES, génèrent des leads — galeries de templates, pages de comparaison, pages d'alternatives, articles de blog. **Construisez d'abord les pages de destination, puis soumettez aux annuaires pour que le link equity ait quelque part d'utile où atterrir.**

Le catalogue complet d'annuaires vit dans `references/directory-list.md`. La bibliothèque de variantes de positionnement vit dans `references/positioning-variations.md`. Le template de tracker de soumissions vit dans `references/submission-tracker-template.csv`.

---

## Les trois règles d'or

### Règle 1 : Fondation avant soumission
Ne jamais soumettre à un annuaire tant que la landing page vers laquelle il pointera n'est pas en ligne, indexée et qu'elle ne dispose pas de :
- Un seul `<h1>` et une hiérarchie de titres séquentielle — les pages à hiérarchie propre ont des **taux de citation IA 2,8× plus élevés**, et 87 % des pages citées par ChatGPT utilisent un seul H1.
- Une vraie page de pricing (même « gratuit pendant la beta » compte — la plupart des annuaires Tier 1 en exigent une).
- Politique de confidentialité + CGU.
- Des assets de logo en PNG + SVG + carré 1024×1024 + favicon.
- 5 à 8 vraies captures d'écran produit en 1920×1080 (pas des mockups marketing).
- Une vidéo de démo de 60 à 90 secondes — les produits avec vidéo sur Product Hunt obtiennent **2,7× plus d'upvotes**.
- Du schema markup FAQ (les moteurs IA pondèrent fortement le JSON-LD `FAQPage` pour l'extraction de réponses).
- Des données structurées : `Organization`, `Product`, `SoftwareApplication`.

### Règle 2 : Pages de destination avant annuaires
Les annuaires sont la *source* du link equity. Il vous faut des *destinations* capables de convertir le trafic qui en résulte. Destinations minimales avant de soumettre où que ce soit :
- 3 à 5 pages d'alternatives concurrents (`/alternatives/[concurrent]`) ciblant les mots-clés « [concurrent] alternative ». Les pages de comparaison/alternatives convertissent à **5-15 %** contre 0,5-2 % pour du contenu générique.
- 3 à 5 pages de cas d'usage (`/for/[audience]` ou `/use-cases/[cas-usage]`).
- Une galerie de templates avec 20+ entrées (si applicable — c'était le plus gros moteur de croissance SEO de Typeform, générant 30 000 inscriptions non-brandées et 3 M$/an de LTV).
- 1 article de blog « best of » que vous avez écrit vous-même sur votre propre catégorie, avec une couverture honnête des concurrents.

### Règle 3 : Le positionnement varie selon le type d'annuaire
Ne jamais copier-coller la même description partout. Les moteurs IA pénalisent le contenu dupliqué, et chaque audience d'annuaire réagit à un cadrage différent. Voir `references/positioning-variations.md` pour la bibliothèque complète de variantes. Version courte :

| Surface | Attaquer par | Pourquoi |
|---|---|---|
| Annuaires de startups | **Résultat** | L'audience, ce sont d'autres fondateurs. Ils tiennent à ce que ça fait. |
| Annuaires SaaS | **Cadrage par alternative** | Les gens cherchent « [concurrent] alternative » — allez à leur rencontre. |
| Annuaires IA | **Architecture AI-first** | Les audiences TAAFT/Futurepedia veulent explicitement des outils IA. |
| Annuaires agents/MCP | **Angle agent/MCP** | Niche mais à forte intention. Un vrai moat. |
| Annuaires no-code | **Facilité + puissance** | L'audience valorise la vitesse de construction plus que la profondeur. |
| Annuaires dev | **Profondeur technique** | Les audiences dev récompensent la substance technique. |
| Sites d'avis B2B | **ROI + cas d'usage** | Les acheteurs veulent des résultats et des études de cas. |

---

## Workflow

### Étape 1 : Évaluation de readiness (Phase 0)

Posez à l'utilisateur ces 9 questions. Si l'une est « non », il n'est pas prêt — aidez-le à construire d'abord la pièce manquante.

1. Le produit est-il accessible publiquement (sans mur de mot de passe) ?
2. Y a-t-il une page de pricing (même « gratuit pendant la beta ») ?
3. La politique de confidentialité + les CGU sont-elles en ligne ?
4. Assets de logo en PNG + SVG + carré + favicon ?
5. 5 à 8 vraies captures d'écran + vidéo de démo de 60-90 s ?
6. Landing pages prêtes pour le GEO (H1 unique, hiérarchie séquentielle, schema FAQ, données structurées) ?
7. Au moins 3 pages d'alternatives et 3 pages de cas d'usage en ligne et indexées ?
8. Galerie de templates ou asset de lead magnet (si applicable à la catégorie) ?
9. Au moins 20 utilisateurs beta/early qui pourraient laisser un avis sur G2 ?

Un « non » sur l'un des points 1 à 7 est un blocage dur. Un « non » sur 8-9 est un blocage souple : vous pouvez lancer mais vous perdrez la valeur des avis Tier 2 et l'effet cumulatif à la Typeform.

### Étape 2 : Choisir les tiers

Catalogue complet dans `references/directory-list.md`. Synthèse :

| Tier | Quand | Exemples | Nombre typique |
|---|---|---|---|
| **Tier 1 — Lancement phare** | Semaine de lancement uniquement | Product Hunt (ancre), BetaList, HN Show HN, Fazier, DevHunt | ~15 |
| **Tier 2 — Startup/SaaS** | Semaine 1 + en continu | AlternativeTo, SaaSHub, G2, Capterra, F6S, SourceForge, Slashdot | ~50 |
| **Tier 3 — Annuaires IA** | Semaines 1 à 3 | TAAFT, Futurepedia, Toolify, Future Tools, aitools.inc, AIStage | ~40 |
| **Tier 4 — Registres agents/MCP** | Semaines 1 à 3 (si MCP) | Glama, APITracker, LF MCP Registry, AI Agents List | ~10 |
| **Tier 5 — Annuaires no-code** | Semaines 1 à 3 (si no-code) | NoCodeFinder, No Code MBA, We Are No Code, MakerPad | ~8 |
| **Tier 6 — Listicles « best of »** | Outreach en continu | Cold outreach vers des articles de blog DR 40+ | ~10 inclusions |
| **Tier 7 — Marketplaces d'intégrations** | Quand les intégrations sortent | Zapier, HubSpot, Slack, Airtable, Notion | ~5 |
| **Tier 8 — Plateformes de profil & contenu** | En continu | GitHub, WordPress.com, Substack, Dev.to, SlideShare, Behance | ~50 |
| **Tier 9 — Annuaires d'entreprises locales** | En continu (si applicable) | Manta, Hotfrog, Locanto, MerchantCircle | ~20 |
| **Tier 10 — Forums & communautés** | En continu (participer d'abord) | SitePoint, GrowthHackers, Warrior Forum, Designer News | ~13 |
| **Tier 11 — Sites de communiqués de presse & articles** | Lancement + jalons | PRLog, PR.com, EzineArticles, Feedspot | ~25 |
| **Tier 12 — Social bookmarking** | En continu | Scoop.it, Diigo, Pearltrees | ~5 |
| **Tier 13 — Annuaires verticaux de niche** | Quand la verticale colle | Justia (juridique), Porch (maison), LandBook (design), etc. | ~20 |

**Règle de triage :** Ne soumettre que là où le produit colle vraiment. Forcer une fiche dans la mauvaise catégorie gâche l'avantage de la première soumission et se fait rejeter par les modérateurs.

### Étape 3 : Préparer les variations d'assets

Pour chaque tier, préparer une variante de description distincte (tirée de `references/positioning-variations.md`) :
- **Tagline** de moins de 10 mots
- **Description courte** à 60 caractères
- **Description longue** à 150 mots
- **5 à 8 tags de catégorie**
- **Assets** de logo
- **Captures d'écran** + URL de la vidéo de démo
- **Histoire du fondateur** (2-3 phrases)

**Critique :** Ne pas copier-coller la même description longue dans chaque annuaire. Varier la phrase d'ouverture, l'accent sur les fonctionnalités et le cadrage de l'audience par tier. Les moteurs IA croisent les références et déclassent le contenu dupliqué.

### Étape 4 : Soumettre par lots

Mettre en place le tableur de tracking (`references/submission-tracker-template.csv`). Le parcourir de gauche à droite. 2 à 3 heures par lot est réaliste.

Par soumission :
1. Copier la variante de positionnement adaptée au tier.
2. Remplir le formulaire.
3. Uploader les assets.
4. Soumettre.
5. Logger : date, URL, statut, notes du modérateur.
6. Une fois en ligne, vérifier que le backlink existe et est dofollow : `curl -sIL https://directory.com/your-listing | grep -i rel=`. S'il est absent, le lien est dofollow.

---

## Plongée en profondeur Product Hunt (l'événement ancre)

Product Hunt est la soumission au plus fort levier mais aussi la plus facilement gâchée. L'algorithme PH 2026 pondère **la qualité des commentaires** plus que le nombre d'upvotes — un post avec 50 upvotes + 30 commentaires authentiques se classe au-dessus d'un avec 200 upvotes + 5 commentaires. **80 % des lancements ratés** échouent parce qu'ils ont lancé sans audience chauffée OU ont demandé des upvotes au lieu de feedback.

### Timeline de prépa sur 3 semaines

- **J-21 à J-14 :** Chauffer le compte hunter. Upvoter + commenter de façon réfléchie 3 lancements/jour. Suivre 100+ makers actifs. Construire un historique pour que votre compte ait l'air réel aux yeux de l'algorithme.
- **J-14 :** Créer une page « Upcoming » sur PH. Y diriger du trafic pour collecter des abonnés « me notifier au lancement ».
- **J-10 :** (Optionnel) réserver un hunter. Ne pas payer cash — échanger une feature, un shoutout ou une intro. Un hunter connu ajoute ~15 % de momentum au jour 1 mais n'est pas requis.
- **J-7 :** Rédiger les assets du jour de lancement : images de galerie (1270×760), tagline, description de 260 caractères, votre premier commentaire, premier commentaire d'un client.
- **J-3 :** Chauffer la liste email. « On lance mardi. Voici à quoi s'attendre. Répondez si vous voulez un rappel. »
- **J-1 :** Vérification finale — le produit fonctionne en navigation privée, la vidéo se lance automatiquement, le CTA mène à l'inscription, l'aperçu de la fiche PH a la bonne tête.

### Exécution du jour de lancement

- **Lancer à 12h01 heure du Pacifique.** Mardi, mercredi ou jeudi seulement — les lancements de week-end reçoivent 60-70 % de trafic en moins. Le départ à 12h01 PT maximise votre fenêtre de 24 heures.
- **Les 2 premières heures sont tout.** Il faut 50+ soutiens dans les 2 premières heures pour déclencher la distribution algorithmique.
- **Postez le premier commentaire vous-même** avec l'histoire : pourquoi vous l'avez construit, ce qui est différent, quoi essayer en premier.
- **Répondez à chaque commentaire** en moins de 30 minutes. PH mesure la réactivité du maker.
- **Partagez le lien vers :** un thread Twitter/X, un post LinkedIn long format, vos communautés Slack/Discord personnelles, votre liste email, Indie Hackers, chaque power user en DM.
- **Ne jamais demander d'upvotes.** Demandez du **feedback**. « J'adorerais votre avis honnête sur le positionnement » convertit 3× mieux que « soutenez-nous ! » et ne déclenche pas les filtres anti-manipulation de l'algorithme.
- **Ne messagez pas d'inconnus.** La communauté le signale et les modérateurs masqueront votre post.

### Post-lancement

- Écrire un article de blog de bilan de lancement avec des chiffres + des leçons. Honnête, pas vantard. Publier au jour 2.
- Cross-poster le bilan sur Indie Hackers et r/SaaS (où la promo est autorisée).
- Ne soumettre à Show HN que si vous avez un angle *technique* à partager (architecture, DSL, approche inédite). Un post générique « on a lancé un SaaS » se fera flag à mort.

---

## Playbook avis (G2 / Capterra / TrustRadius)

Les fiches G2 et Capterra (désormais détenu par G2 depuis février 2026) sont **sans valeur sans avis**. 10 avis est le seuil magique pour apparaître dans la Grid. Faites tourner le protocole 10-en-30 pendant le mois de lancement.

### Le protocole 10-en-30

1. **J+1 post-lancement :** Identifier 20 utilisateurs qui ont accompli une action significative avec le produit.
2. **Envoyer à chacun un email personnel** avec une URL d'avis directe (réduit la friction d'environ 70 %). Pas de formulaires, pas de landing pages — lien direct.
3. **Offrir un modeste remerciement.** G2 et TrustRadius autorisent explicitement de petites incitations comme une carte cadeau Amazon de 25 €.
4. **Relancer une fois** après 5 jours. Ne pas relancer deux fois — ça devient agaçant et abîme la relation.
5. **Cible :** 50 % de conversion → 10 avis pour 20 demandes.

### Échéances critiques

- **Rapports G2 Summer :** clôture ~28 avril. Planifier les campagnes d'avis pour atterrir avant.
- **Rapports G2 Fall :** clôture ~28 juillet.
- Rater une clôture signifie attendre 3 mois la prochaine mise à jour de la grid.

### Badges et plans payants

- **Le badge « Users Love Us »** est toujours gratuit : requiert 20 avis à 4,0+ de moyenne.
- **Les badges Grid, Momentum, Index et Award** requièrent un plan G2 payant (à partir de 2 999 €/an depuis l'été 2025).
- **Ne pas dépenser pour du G2 payant la première année.** La fiche gratuite + le badge Users Love Us suffisent.

### Cross-plateforme

- TrustRadius suit une mécanique similaire mais à plus faible volume.
- Capterra se synchronise automatiquement depuis Gartner Digital Markets dans certaines catégories — peut se remplir sans action directe.

---

## Stratégie des pages de destination (vers quoi pointent les backlinks)

Les annuaires ne servent à rien si les backlinks atterrissent sur une page d'accueil générique. Construisez ces pages de destination *avant* de soumettre :

### 1. Pages d'alternatives (ROI le plus élevé)

Les pages d'alternatives concurrents convertissent à **5-15 %**, atteignant souvent 15-30 % pour les requêtes de bas de funnel. Une page par concurrent principal :

- `/alternatives/[concurrent-1]`
- `/alternatives/[concurrent-2]`
- `/alternatives/[concurrent-3]`
- `/alternatives/[concurrent-4]`

Chaque page a besoin de : un tableau comparatif honnête des fonctionnalités, « quand choisir X plutôt que nous », « quand nous choisir plutôt que X », une comparaison de pricing, 3 à 5 exemples de cas d'usage, une FAQ solide avec schema.

**Critique :** Soyez honnête. Les moteurs IA croisent les affirmations de fonctionnalités des concurrents et déclassent les pages qui mentent.

### 2. Pages de cas d'usage / ICP

Chaque ICP a sa propre landing page dédiée :
- `/for/[audience]` — coachs, agences, e-commerce, SaaS, consultants, etc.
- `/use-cases/[cas-usage]` — qualification de leads, onboarding, recommandations produit, etc.

### 3. Galerie de templates / d'assets (si applicable)

La bibliothèque de templates de Typeform a généré **30 000 inscriptions organic non-brandées et 3 M$/an de LTV**. Le pattern :
- Une page indexable par template sur `/templates/[slug]`.
- H1 avec le mot-clé, description de 150+ mots, capture d'écran, « quand l'utiliser », CTA « utiliser ce template ».
- Templates associés en bas de chaque page (maillage interne = effet cumulatif SEO).
- 100 templates au jour 30, 300 au jour 90 est la cible réaliste.

### 4. Listicles « best of » que vous avez écrits vous-même

Écrivez des comparatifs honnêtes de votre propre catégorie : `/blog/best-[categorie]-tools-2026`. Incluez-vous + 10 concurrents avec de vrais avis. Ces pages se positionnent sur les requêtes de catégorie ET servent de références canoniques que les moteurs IA citent.

### 5. Pages d'intégrations (quand les intégrations sortent)

Chaque intégration = une landing page sur `/integrations/[partenaire]`. Suit le playbook Zapier : Zapier obtient **~2,6 M de visites organic mensuelles** depuis ses pages d'intégration programmatiques (~15 % de son trafic organic total).

---

## GEO (Generative Engine Optimization)

En 2026, 30 à 50 % des requêtes « rechercher un outil » se passent dans ChatGPT, Claude, Perplexity ou les AI Overviews de Google sans jamais toucher une page de recherche traditionnelle. Les annuaires comptent ici aussi — les moteurs IA puisent massivement dans les annuaires à fort DR pour générer des réponses. Mais les *pages de destination* doivent aussi être optimisées pour le GEO.

### Tactiques qui font citer les pages

1. **Un H1 par page, hiérarchie de titres séquentielle.** Taux de citation 2,8× plus élevé. 87 % des pages citées utilisent un seul H1.
2. **Contenu dense et factuel avec des stats citables.** Les moteurs IA préfèrent les chiffres précis (« 3× plus rapide que X ») aux affirmations vagues.
3. **Schema FAQ sur chaque landing page.** Les moteurs IA pondèrent fortement le JSON-LD `FAQPage` pour l'extraction de réponses.
4. **Tableaux comparatifs.** Extractibles, structurés — exactement ce dont une réponse IA a besoin.
5. **Paragraphe explicite « ce que c'est » dans les 100 premiers mots.**
6. **Se faire citer sur Reddit et Hacker News.** Claude et Perplexity les indexent massivement. Des mentions authentiques sur r/SaaS et HN comptent comme carburant d'entraînement.
7. **Publier de la recherche originale.** « Nous avons analysé 10 000 [trucs] et trouvé X » devient la citation principale pour quiconque écrit sur ce sujet.
8. **Réclamer les fiches Crunchbase, page entreprise LinkedIn et Wikidata.** Les trois alimentent les corpus d'entraînement des IA.
9. **Si applicable, se lister sur les registres MCP avec des notes A/B** (Glama en particulier). Les LLM y puisent pour répondre aux questions MCP.

### Mesure

Vérifier manuellement chaque mois : demander à ChatGPT, Claude et Perplexity « quels sont les meilleurs outils de [catégorie] ? » et logger là où le produit apparaît. Des outils gratuits de tracking GEO (GeoTracker, llmrefs) automatisent ça.

---

## Communauté & distribution continue

Les annuaires sont un coup unique. La communauté est continue. Les deux alimentent le même funnel.

### Reddit (règle des 90/10)

90 % de l'activité doit être réellement utile ; 10 % seulement promotionnelle. Enfreindre ça fait shadowban.

**Subs à forte valeur (classés) :**
- **r/SideProject** (200K+) — accueillant pour la promo, les annonces de lancement sont bienvenues.
- **r/SaaS** (300K+) — les threads « Share Your SaaS » sont des fenêtres de promo explicites.
- **r/startups** (1,7M) — thread Feedback Friday.
- **r/Entrepreneur** (3,5M) — thread de promo hebdomadaire.
- **r/nocode**, **r/IndieHackers**, **r/alphaandbetausers** — accueillants.
- **r/webdev**, **r/artificial**, **r/LocalLLaMA** — stricts, technique uniquement.

**Ce qui gagne :** des vrais chiffres (MRR, inscriptions, churn), des captures d'écran, une structure « ce que j'ai essayé / ce qui s'est passé / ce que je ferais différemment », des mini études de cas avec une leçon claire. **Ce qui échoue :** le hype, les affirmations vagues, les posts « regardez mon nouvel outil », demander des upvotes.

### LinkedIn (canal B2B principal)

80 % des leads sociaux B2B viennent de LinkedIn. Cadence : **3 à 5 posts/semaine** — moins fait perdre le momentum, plus provoque la fatigue.

Types de contenu classés par engagement 2026 :
1. Histoires personnelles avec des leçons business (1,5-2× l'engagement moyen)
2. Données / recherche originales (1,3-1,5×)
3. Prises à contre-courant sur le secteur (1,2-1,5×)
4. Carrousels de documents de 8 à 12 slides (1,3-1,8×)

### Twitter/X (canal indie hacker + dev)

Threads build-in-public sur l'architecture, le chiffre d'affaires, les décisions. Les deep-dives techniques se font indexer par Google + Claude + Perplexity → GEO indirect.

### Indie Hackers

- Lancer un thread build-in-public le jour du lancement PH.
- Poster des mises à jour hebdomadaires : revenus, livraisons, leçons. Les posts à revenu zéro fonctionnent si la leçon est honnête.
- Commenter 10× plus que vous ne postez pour bâtir du karma avant vos propres liens.

### Dev.to + Hashnode

Chaque post technique substantiel = backlink dofollow + portée auprès d'une audience dev. Cross-poster avec une URL canonique vers le blog principal.

---

## KPI & tracking

Suivre chaque semaine. Si un chiffre ne bouge pas, enquêter — ne pas juste soumettre plus d'annuaires.

| Métrique | Jour 0 | Cible jour 30 | Cible jour 90 |
|---|---|---|---|
| Domain Rating (DR) | 0 | 20 | 30+ |
| Domaines référents | 0 | 30 | 80+ |
| Pages indexées | — | 50 | 200+ |
| Clics organic/jour | 0 | 30 | 200+ |
| Fiches d'annuaires en ligne | 0 | 50 | 70+ |
| Avis G2 | 0 | 10 | 25 |
| Avis Capterra | 0 | 5 | 15 |
| Citations IA (vérif manuelle) | 0 | 3 | 15+ |
| Inscriptions via référents d'annuaires | 0 | 50 | 300 |
| Inscriptions via pages alt/cas d'usage | 0 | 20 | 300 |

---

## Ce qu'il NE faut PAS faire

1. **Ne pas payer pour des services de soumission d'annuaires** (packages de 60-200 €). Tout l'intérêt, c'est que c'est gratuit. C'est un après-midi de copier-coller.
2. **Ne pas soumettre à des annuaires spam** (DR sous 10, pas de trafic, pas de qualité éditoriale). Ils diluent votre profil de backlinks et la détection de spam de Google peut vous pénaliser.
3. **Ne pas soumettre avec le mauvais positionnement.** Relire le tableau de positionnement par tier. Les descriptions génériques gâchent la fiche.
4. **Ne pas traiter les annuaires comme tout votre GTM.** Ils sont la fondation. Le contenu + la communauté + les avis sont ce qui convertit réellement.
5. **Ne pas sauter les avis sur G2/Capterra.** Les fiches sans avis sont mortes. Faites tourner le protocole 10-en-30 ou ne soumettez pas.
6. **Ne pas demander d'upvotes sur Product Hunt.** L'algorithme 2026 le pénalise. Demandez du **feedback**.
7. **Ne pas modifier vos vieilles fiches d'annuaires chaque semaine.** Soumettez une fois, vérifiez chaque trimestre.
8. **Ne pas soumettre avant que la page de destination existe.** Le link equity a besoin d'une destination.
9. **Ne pas dupliquer les descriptions d'un annuaire à l'autre.** Les moteurs IA pénalisent le contenu dupliqué.
10. **Ne pas mentir sur les pages de comparaison.** Les moteurs IA croisent les références et déclassent les mensonges.
11. **Ne pas sur-pondérer le pic du jour de lancement.** Le flywheel, ce sont les templates + alternatives + avis + contenu continu — pas un seul jour de PH.
12. **Ne pas oublier Crunchbase, la page entreprise LinkedIn et Wikidata.** Elles alimentent les corpus d'entraînement des IA et comptent pour le GEO.

---

## Questions spécifiques à la tâche

1. **Que lancez-vous ?** (La catégorie change le mix de tiers — IA vs SaaS traditionnel vs no-code vs outil dev.)
2. **Quand est le jour de lancement ?** (Les assets de Phase 0 demandent 7 jours de prépa.)
3. **Avez-vous des pages de destination construites ?** (Alternatives, cas d'usage, templates — sinon, construire d'abord.)
4. **Hunter Product Hunt aligné ?** (Optionnel mais ajoute ~15 % de boost au jour 1. Le warm-up de 3 semaines est requis quoi qu'il arrive.)
5. **Combien d'utilisateurs beta pouvez-vous solliciter pour des avis ?** (Il en faut 20 pour atteindre 10.)
6. **Avez-vous un angle MCP ou agent ?** (Si oui, les registres Tier 4 sont un vrai moat.)
7. **Intégrations existantes ?** (Si oui, les marketplaces Tier 7 sont les backlinks au plus fort DR disponibles.)
8. **Taille de la liste email ?** (Nécessaire pour le trafic chaud du jour de lancement PH — 100+ est le minimum.)
9. **DR actuel et nombre de domaines référents ?** (Référence pour mesurer l'effet cumulatif.)

---

## Format de sortie

Quand l'utilisateur demande un plan d'annuaires, renvoyez :

1. **Évaluation de readiness** — quels éléments de Phase 0 manquent, lesquels bloquent la soumission
2. **Sélection des tiers** — quels tiers s'appliquent, lesquels sauter, pourquoi
3. **Ordre de soumission** — lots de semaine 1 / semaine 2 / semaine 3
4. **Liste des pages de destination** — quoi construire d'abord si manquant
5. **Variantes de positionnement** — le copy réel par tier (depuis `references/positioning-variations.md`)
6. **Timeline de prépa PH sur 3 semaines** — mappée aux dates du calendrier si le jour de lancement est connu
7. **Plan d'avis 10-en-30** — qui solliciter, quand, comment
8. **Cibles hebdomadaires** — annuaires soumis, avis, évolution du DR
9. **Tracker** — lien vers ou inclusion du CSV depuis `references/submission-tracker-template.csv`

Gardez le plan actionnable. Chaque élément doit être quelque chose que l'utilisateur peut faire aujourd'hui.

---

## Skills associés

- **launch** — moment de lancement plus large, framework ORB, approche en cinq phases
- **programmatic-seo** — pages de destination (alternatives, intégrations, templates) vers lesquelles les backlinks doivent affluer
- **competitors** — pattern de page `/alternatives/[outil]`
- **ai-seo** — optimisation GEO pour la citation par les IA
- **content-strategy** — contenu éditorial qui attire les inclusions dans les listicles « best of »
- **free-tools** — lead magnets pour les pages de destination
- **community-marketing** — mécaniques des communautés Reddit, Indie Hackers, Slack
- **schema** — JSON-LD FAQ + Product + Organization pour le GEO
