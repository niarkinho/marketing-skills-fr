# Template de plan — La structure en 13 sections

Le template canonique pour chaque plan marketing généré par ce skill. Chaque section a un objectif, une structure et des prompts en ligne sur ce qu'il faut rédiger.

Le plan Quietude (voir `references/example-quietude.md`) est l'implémentation de référence canonique.

---

## Bloc de titre

```markdown
# {Client} — Plan marketing v1

**Préparé par :** {Auteur / nom du fCMO}
**Pour :** {Fondateurs / équipe de direction}
**Date :** AAAA-MM-JJ
**Statut :** Brouillon v1 — pour revue d'équipe
```

---

## Section 1 — Synthèse exécutive

**Objectif :** prête à copier-partager. Un fondateur devrait pouvoir la coller dans un point board ou un email investisseur sans rien éditer.

**Longueur :** 400–700 mots. Serrée.

**Structure :**
1. **Cadre en une phrase.** Qu'optimise ce plan ? Pas « plus de chiffre d'affaires » — quelque chose de spécifique à ce client à ce stade.
2. **Trois gros paris, classés par effet de levier.** Chacun est un paragraphe. Un pari = une thèse à forte conviction sur l'endroit où l'équipe doit concentrer capital et attention.
3. **À quoi ressemblent douze mois, de façon plausible.** Liste à puces. L'état de résultat plausible à la fin de l'horizon du plan. Lisible par un investisseur.
4. **Priorités à 90 jours.** Liste numérotée. Les six (à peu près) mouvements qui sont expédiés au premier trimestre.

**Notes de voix :**
- Coller à la voix du client
- Direct, lisible par un fondateur, sans jargon marketing
- Utiliser des noms et des chiffres (canaux spécifiques, métriques spécifiques) — pas des abstractions
- Arbitrages nommés explicitement quand ils comptent

---

## Section 2 — Cadre stratégique

**Objectif :** distiller positionnement, ICP, logique de business model et brand voice dans une seule page que tout membre de l'équipe ou nouvelle recrue peut lire pour s'orienter.

**Longueur :** 800–1500 mots.

**Structure :**

### Ce qu'est {Entreprise}, en une phrase
Tiré du doc de positionnement / deck seed / langage du fondateur.

### La catégorie que nous revendiquons
L'entreprise crée-t-elle une nouvelle catégorie, en redéfinit-elle une existante, ou concourt-elle dans une catégorie définie ? La nommer. Énoncer le cadre qui définit la catégorie en 2–3 phrases. Référencer la source (mots du fondateur, doc ICP, etc.).

### Pour qui nous sommes (ICP, distillé)
Démographie / firmographie + problème déclaré vs. problème réel + ce qu'ils achètent réellement. Serré, 4–6 puces.

### La logique du business model
Comment l'entreprise gagne-t-elle de l'argent ? Quelle est la théorie de l'unit economics d'acquisition client ? Quelle est la thèse du canal à effet cumulatif (s'il y en a une) ? Tiré du deck seed / modèle financier / narratif du fondateur.

### Brand voice (le non-négociable)
Si le client a des règles de voix documentées, les lister. Vocabulaire OUI / NON. Règles de CTA. Ton. Méthode centrale (initiatique, explicative, narrative, etc.). Toutes les autres sections du plan doivent les respecter.

**Notes de voix :**
- C'est la section la plus « à reprendre des matériaux existants » — ne pas inventer de positionnement. Faire remonter ce qui existe.
- Si le positionnement est flou ou contredit entre les matériaux, le signaler dans les décisions ouvertes de la Section 13.

---

## Section 3 — État des lieux

**Objectif :** ancrer le plan dans la réalité. Quels sont l'équipe, le budget, le travail en cours et le travail bloqué *aujourd'hui* ?

**Longueur :** 1000–2000 mots.

**Structure :**

### Composition de l'équipe (surface marketing)
Tableau de chaque personne ayant une surface marketing :

| Personne | Rôle | Surface marketing |
|---|---|---|

Être honnête sur les trous. S'il n'y a pas encore de recrutement marketing dédié, nommer le moment où il devient nécessaire et quel rôle (voir [team-and-agency-model.md](team-and-agency-model.md) — le premier recrutement devrait être un stratège en π, intitulé Manager ou Lead, pas VP/CMO).

### Budget marketing (actuel)
- Acquisition payante : X €/mois
- Stack d'outils : lister avec coût estimé
- Retainers / fCMO : lister
- Masse salariale : lister
- CAC blended : X € (doit inclure salaires, coûts de contenu, outils, retainers — pas seulement la dépense payante ; voir [budget-planning.md](budget-planning.md) pour le calcul)
- Dépense actuelle en % de l'ARR : X % (comparer à la fourchette 5–40 %)

Énoncer le palier de stade de financement auquel cela correspond (voir [funding-stage-unlocks.md](funding-stage-unlocks.md)). Implication : ce que le plan à 90 jours doit produire *sans* leviers qui exigent un budget futur.

### Phase de croissance SaaS
Nommer la phase actuelle : 0–10 K€ ARR / 10 K–100 K€ / 100 K€–1 M€ / 1 M€–10 M€ / 10 M€+. Chaque phase a sa propre contrainte limitante et son pattern de croissance dominant (voir [growth-patterns.md](growth-patterns.md)). La Section 10 séquence le passage vers la phase suivante.

### Ce qui est déjà fait (reconnaître, puis bâtir dessus)
Tableau :

| Actif | Statut | Effet de levier marketing |
|---|---|---|

C'est là que les lancements passés, moments RP, piliers de contenu, certifications, utilisateurs notables sont reconnus. **Critique** : ne pas écrire un plan qui ignore le travail dont l'équipe est fière.

### Ce qui est en cours (rédigé mais pas expédié)
Tableau :

| Élément | Statut | Blocage |
|---|---|---|

Être honnête sur les blocages. Là où le blocage est « pas de temps » ou « pas de décision », cela va aux décisions ouvertes de la Section 13.

### Ce qui est bloqué (et à débloquer ce trimestre)
Tableau :

| Problème | Coût de l'inaction | Action |
|---|---|---|

Les choses bloquées sont les endroits au plus fort effet de levier où concentrer les premières semaines du plan à 90 jours.

### Snapshot de la grille d'audit
Snapshot noté en 17 sections avec la grille d'état actuel intégrée. Voir `references/current-state-rubric.md` pour la grille complète et les guides de notation.

Si un audit noté antérieur existe, y coller ces scores. Sinon, noter à partir des matériaux disponibles et indiquer « noté à partir des matériaux » sous le titre.

| # | Section | Score | Note |
|---|---|---|---|
| 1 | Positionnement | 0–5 | |
| 2 | Recherche client | 0–5 | |
| ... | ... | ... | ... |
| 17 | Internationalisation | 0–5 | |

**Total : X / 85 (Y %).** Noter la *forme* de la force et de la faiblesse — cette forme est le trou que le reste du plan comble.

**Notes de voix :**
- Honnête > poli. Si les métriques du client sont mauvaises, les nommer. Les fondateurs lisent au-delà de l'enrobage.

---

## Section 4 — Acquisition

**Objectif :** répondre à « comment des inconnus prennent-ils connaissance de nous ? » Mapper chaque canal : état actuel, mouvements planifiés, écartés (avec raison).

**Longueur :** 1000–1800 mots.

**Structure :**

### État actuel
Bref. Ce qui marche aujourd'hui, ce qui ne marche pas, ce que les données montrent sur le mix de canaux.

### Le plan
« Mouvements » numérotés. Chaque mouvement est un paragraphe (3–6 phrases) décrivant le canal, la thèse et le travail spécifique. Mouvements courants :

- **Mouvement 1 — SEO (et contenu)** — Référencer le plan SEO s'il en existe un (`seo/plan.md`). Sinon : recherche de mots-clés, structure pilier/spoke, cadence de contenu.
- **Mouvement 2 — Optimisation App Store / Play Store** (pour les apps grand public) — Réécriture de fiche, tests de captures, ciblage de mots-clés ASO.
- **Mouvement 3 — Canaux pilotés par le fondateur** — LinkedIn pour B2B/SaaS, Twitter/X pour la tech, Instagram pour le grand public. Cadence, sujets, responsables.
- **Mouvement 4 — Amplification RP** — Quel est l'ancrage de crédibilité ? Comment l'amplifier.
- **Mouvement 5 — Événements (si applicable)** — Événements live, conférences, webinaires. Rôle acquisition vs. activation.
- **Mouvement 6 — Surface hardware / commerce (si applicable)** — Boutique Shopify, Amazon, retail.
- **Mouvement 7 — Support des ventes B2B** — Études de cas, pages partenaires, contenu spécifique à la verticale.
- **Mouvement 8 — Couche payante (quand le budget se débloque)** — Apple Search Ads, Meta, LinkedIn, Google. Maintenu jusqu'au stade de financement spécifié.

### Mouvements d'acquisition à 90 jours
Ventilation semaine par semaine des expéditions du premier trimestre.

### Perspective d'acquisition à 12 mois
État de résultat trimestre par trimestre (T1 / T2 / T3 / T4).

### Skills + outils
- **Skills :** lister les skills pertinents du repo marketing-skills (`seo-audit`, `ai-seo`, `ads`, `social`, `competitors`, etc.)
- **MCP / API :** lister les connexions (Ahrefs API, GA4 MCP, Typefully MCP, Stripe MCP pour les calculs de LTV, etc.)

---

## Section 5 — Activation

**Objectif :** répondre à « une fois que quelqu'un nous essaie, vit-il une expérience qui convertit ? »

**Longueur :** 800–1500 mots.

**Structure :** identique à Acquisition (État actuel / Le plan / 90 jours / 12 mois / Skills + outils).

**Mouvements courants :**
- Correctifs fondamentaux (inscription cassée, portes d'onboarding cassées, etc.)
- Tests / refonte d'onboarding (souvent le mouvement au plus fort effet de levier à ce stade)
- Réécriture de la fiche App Store (renvois croisés vers Acquisition)
- Ordre d'expédition des Lifecycle Flows (quand expédier les emails d'onboarding vs. attendre la stabilité produit)
- Revue paywall + pricing (souvent Activation × Revenu)

### Skills + outils
`onboarding`, `signup`, `paywalls`, `copywriting`, `marketing-website-design`, `ab-testing`, etc.

---

## Section 6 — Rétention

**Objectif :** répondre à « une fois que quelqu'un convertit, reste-t-il et approfondit-il ? »

**Longueur :** 800–1500 mots.

**Structure :** identique à ci-dessus.

**Mouvements courants :**
- Flows d'emails de cycle de vie (post-achat, utilisateur en perte de vitesse, win-back)
- Centres d'abonnement / de préférences
- Réconciliation du churn (souvent les définitions de métriques ne correspondent pas entre les surfaces)
- Chemins d'activation hardware → software (pour les activités hybrides)
- Tests de défaut sur le plan annuel (renvois croisés vers Revenu)

### Skills + outils
`emails`, `churn-prevention`, `copywriting`, `paywalls`, etc.

---

## Section 7 — Recommandation (Referral)

**Objectif :** répondre à « les utilisateurs retenus amènent-ils plus d'utilisateurs, et à quel coût ? »

**Longueur :** 500–1200 mots.

**Structure :** identique à ci-dessus.

**Mouvements courants :**
- Lancement d'un programme ambassadeurs / d'affiliation (si un intérêt entrant existe, démarrer par lui)
- Moments « partage-après-valeur » intégrés au produit
- Amplification par le fondateur (le fondateur comme référent-zéro)
- Réseau long terme d'experts / Guides / hôtes certifiés
- Flows de cadeau (pour le grand public / hardware)

### Skills + outils
`referrals`, `social`, `emails` (pour le cycle de vie ambassadeur), `copywriting`, etc.

---

## Section 8 — Revenu

**Objectif :** répondre à « que facturons-nous, qui paie, et comment cela cumule-t-il ? »

**Longueur :** 500–1200 mots.

**Structure :** identique à ci-dessus.

**Mouvements courants :**
- Audit de pricing (ce qui est réellement facturé aujourd'hui vs. ce qui est affiché ?)
- Tests de défaut sur le plan annuel
- Formalisation du bundling hardware → software (pour les activités hybrides)
- Optimisation de la boutique / des pages commerce
- Études de cas B2B + matériel de vente
- Pools de valeur long terme (licence de données, expansion enterprise) — signalés mais non exécutés dans le plan à 12 mois

### Unit economics
Tableau requis :

| Métrique | Valeur | Note |
|---|---|---|
| ARPC (revenu mensuel moyen par client) | X € | Tiré de Stripe / facturation |
| CAC blended | X € | Inclut tous les coûts marketing, pas seulement le payant |
| Taux de rétention annuel | X % | 1 − churn annuel |
| LTV (approximatif) | X € | ARPC × 12 / churn annuel |
| LTV / CAC | X | Benchmark de santé : > 3 |

Ceux-ci alimentent les calculs de budget de la Section 10. Si l'un d'eux est inconnu, le signaler en Section 13 comme décision ouverte n°1.

### Skills + outils
`pricing`, `paywalls`, `sales-enablement`, `revops`, `ab-testing`, etc.

---

## Section 9 — Feuille de route 90 jours

**Objectif :** la couche d'exécution tactique. Chaque mouvement est expédié dans une semaine nommée, avec un responsable.

**Longueur :** des tableaux, pas de la prose. Devrait tenir sur une page imprimée si possible.

**Structure :** quatre sprints de 2–3 semaines :

### Semaines 1–2 — Débloquer
Changements à la plus forte confiance, au plus faible coût. Retirer ce qui est cassé.

| Mouvement | Étape | Responsable |
|---|---|---|

### Semaines 3–4 — Fondation
Travail pilier/fondateur. Consolidation de domaine. Premiers contenus. Premiers flows expédiés. Premiers tests en ligne.

### Semaines 5–8 — Vélocité
Le travail à effet cumulatif commence. Cadence de contenu. Tests répétés. Scaling de canaux.

### Semaines 9–12 — Cumuler
Mouvements de second ordre. Tactiques en couches. Préparation de la revue à 90 jours.

---

## Section 10 — Perspective 12 mois

**Objectif :** jalons trimestriels avec déblocages de capacités par stade de financement nommés explicitement, ancrés contre un pattern de croissance défendable.

**Longueur :** quatre sous-sections, une par trimestre. ~250–400 mots chacune. Plus un court paragraphe de cadrage en tête nommant la méthode de budget et le pattern de croissance.

### Cadrage (haut de la Section 10)

Énoncer explicitement :
- **Méthode de budget utilisée.** Méthode 1 (basée sur le revenu, 5–40 % de l'ARR) ou Méthode 2 (formule basée sur l'objectif). Voir [budget-planning.md](budget-planning.md). Montrer les calculs.
- **Total du budget annuel** + le buffer expérimental (+10–20 %).
- **Objectif d'ARR de fin d'année qui en résulte.** Prévision honnête, pas une garantie — voir le rappel de réalité sur la prévision dans [measurement-framework.md](measurement-framework.md).
- **Pattern de croissance attendu.** Linéaire (X € de MRR ajouté par mois, prévisible), fonction en escalier (plateau entre des sauts délibérés), ou courbes en S superposées. Pour un Série A+ financé par VC, ancrer contre le 3-3-2-2-2 et montrer si le plan y correspond ou choisit explicitement une trajectoire différente. Voir [growth-patterns.md](growth-patterns.md).

### Structure (par trimestre)

#### T{N} — Mois {X}–{Y}

**État de financement :** {palier} selon `funding-stage-unlocks.md`

**Focus :** thème de focus en une phrase pour le trimestre.

**Résultats à la fin du T{N} :**
- Liste à puces de résultats (5–8 éléments)

**Cibles KPI :** 3–5 cibles numériques spécifiques.

**Position des courbes en S Canal/Produit/Marché :** quelles courbes croissent, lesquelles plafonnent, laquelle est la prochaine en préparation pour ce trimestre (voir [growth-patterns.md](growth-patterns.md) — principe de superposition).

---

## Section 11 — Stack des opérations marketing

**Objectif :** le différenciateur fCMO. Montrer comment une petite équipe + un outillage agentique exécute le plan sans recruter à chaque canal.

**Longueur :** tableaux + brève explication.

**Structure :**

### La thèse
1–2 paragraphes expliquant le principe : petite équipe + bibliothèque marketing-skills + intégrations MCP = la production d'une équipe plus grande.

### Skills mappés aux étapes AARRR

| Étape | Skills principaux | Skills de support |
|---|---|---|
| Acquisition | (lister) | (lister) |
| Activation | (lister) | (lister) |
| Rétention | (lister) | (lister) |
| Recommandation (referral) | (lister) | (lister) |
| Revenu | (lister) | (lister) |
| Transversal | (lister) | (lister) |

### MCP / API mappés aux étapes

| Étape | Connexions existantes | Couche d'outillage fCMO |
|---|---|---|

### Un exemple concret
Choisir un moment opérationnel qui prouve que le stack fonctionne (ex : « le MCP Customer.io a permis au fondateur non technique de rédiger un flow en direct lors de l'appel de kickoff »). Ancrer l'affirmation abstraite dans un événement spécifique.

### Déblocages de capacités par stade de financement

| Stade | Effectif | Outillage | Canaux live |
|---|---|---|---|
| (actuel) | (lister) | (lister) | (lister) |
| (prochain tour) | (delta) | (delta) | (delta) |
| ... | ... | ... | ... |

### Modèle d'équipe et d'agence (RACI)

Appliquer le principe de [team-and-agency-model.md](team-and-agency-model.md) : stratégie en interne, exécution souvent externalisée.

| Fonction | Détenue par (rôle stratégique interne) | Exécutée par (IC / contractor / agence) |
|---|---|---|
| Growth marketing (moteur de demande) | | |
| Product marketing (moteur d'histoire) | | |
| Content marketing (moteur de confiance) | | |

Si l'équipe manque d'un détenteur stratégique pour l'une de ces fonctions, le premier mouvement à 90 jours (Section 9) devrait être le recrutement — intitulé Manager ou Lead, en π si possible, pas VP/CMO.

Si le trou est une capacité d'exécution, nommer le contractor ou la petite agence de niche dans la bonne cellule plutôt que l'IC existant de l'équipe.

Tirer de `references/funding-stage-unlocks.md`.

---

## Section 12 — Banque d'idées tactiques

**Objectif :** croiser les 139 idées du skill `marketing-ideas` avec les étapes AARRR, avec un statut spécifique au client.

**Longueur :** longue — les tableaux peuvent facilement totaliser 150+ lignes.

**Structure :**

### Paragraphe d'intro
Expliquer le renvoi croisé : les Sections 4–8 prescrivent ce qui est *en train d'être fait*. Cette section mappe ce qui est *possible*.

### Légende des statuts

- **Maintenant (T1)** — déjà dans le plan à 90 jours
- **T2** — intégration après la fondation
- **T3+** — expansion après closing du seed ou après GA
- **T4+** — long terme
- **Écarter / hors-marque** — incompatible avec la brand voice ou le business model

### 12.1 Idées d'acquisition

Par statut (Maintenant / T2 / T3+ / T4+ / Écarter), tableaux des idées marketing pertinentes par numéro.

| # | Idée | Note client |
|---|---|---|

### 12.2 Idées d'activation
### 12.3 Idées de rétention
### 12.4 Idées de recommandation (referral)
### 12.5 Idées de revenu
### 12.6 Idées transversales / fondation de marque

### Récapitulatif de la banque d'idées
- Comptes par étape AARRR
- Comptes écartés, avec justification
- Ce que le plan couvre en % de la surface tactique disponible
- Ce que cela prouve sur le stade du client

Utiliser `references/idea-cross-reference.md` comme mapping de référence (source de vérité). Appliquer des filtres spécifiques au client pendant la rédaction (les règles de brand voice en excluent certaines ; le stade de financement décale le timing d'autres).

---

## Section 13 — Mesure, RACI, décisions ouvertes, annexe

**Objectif :** clôture opérationnelle. Définir comment le plan se mesure, qui détient quoi, ce qui est encore TBD, et où trouver les docs plus approfondies.

**Structure :**

### Mesure — les métriques qui comptent

**North star (proposée) :** une métrique qui capture la thèse du business model. Pour Quietude c'était le ratio LTV blended sur CAC blended ; pour un SaaS B2B ce pourrait être NRR × NPS ; pour une marketplace, take-rate × utilisateurs actifs mensuels qui transactent. La rendre spécifique à l'entreprise.

**Indicateurs avancés par étape AARRR :** tableau :

| Étape | Indicateurs avancés |
|---|---|
| Acquisition | ... |
| Activation | ... |
| Rétention | ... |
| Recommandation (referral) | ... |
| Revenu | ... |

**Cadence de revue :**
- Hebdomadaire : qui synchronise avec qui, sur quoi
- Mensuelle : qui passe quoi en revue
- Trimestrielle : déclencheur de recalibrage du plan

### RACI

| Domaine | Responsible | Accountable | Consulted | Informed |
|---|---|---|---|---|

Domaines courants : plan stratégique, brand voice, implémentation app/produit, cycle de vie, contenu SEO, App Store, social piloté par le fondateur, événements, ambassadeurs, ventes B2B, pricing, narratif investisseur, futurs recrutements.

### Décisions ouvertes qui bloquent le plan

Classées par impact. Chacune est : nom + impact + ce qui est bloqué.

1. (impact le plus fort) ...
2. ...
8. (impact le plus faible) ...

### Annexe — liens d'approfondissement

**Publié dans ce repo / partagé avec l'équipe :** {chemins relatifs vers les docs du repo partagé}

**Contexte stratégique rédigé par le fondateur** (base de connaissances interne) : {noms des docs auxquels l'équipe a accès en dehors du repo du plan}

**Brouillons de travail du fCMO** (pas encore publiés) : {noms + comment y accéder auprès de l'auteur}

---

## Ligne de clôture

```markdown
*Plan marketing v1 de {Client}. Préparé par {Auteur}, {Date}. Pour revue et discussion d'équipe.*
```

---

## Heuristiques par section pour « cette section est-elle terminée ? »

- **Section 1** — Un lecteur extérieur à Quietude pourrait comprendre la thèse de croissance de l'entreprise à partir de cela seul.
- **Section 2** — Les règles de brand voice sont assez explicites pour que n'importe quel nouveau copywriter puisse les suivre.
- **Section 3** — Tous les éléments « en cours » ont un responsable et un blocage nommés.
- **Sections 4–8** — Chaque mouvement nomme un skill (`un-skill`) et un outil (Customer.io MCP / Stripe MCP / Ahrefs / etc.).
- **Section 9** — Chaque ligne a un responsable.
- **Section 10** — Chaque trimestre nomme le stade de financement explicitement.
- **Section 11** — Au moins un exemple opérationnel concret prouve la thèse du stack.
- **Section 12** — La liste des idées écartées a une justification, pas juste une absence.
- **Section 13** — La north star est spécifique à cette entreprise (pas un générique « croissance de l'ARR »).
