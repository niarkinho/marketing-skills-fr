# Méthodologie — Comment se construit un plan marketing

Le workflow en trois phases qui produit un plan marketing complet. SKILL.md est la couche d'orchestration ; ce document en est le détail opérationnel.

## Phase 1 — INIT (recherche + intake)

**Objectif :** entrer en Phase 2 avec assez de contexte pour rédiger chaque section sans deviner.

### Étape 1.1 — Mettre en place le dossier du plan

Arborescence canonique pour chaque plan :

```
~/marketing-plans/{client-slug}/
├── materials/         # Fichiers fournis par le client (decks, sortie d'audit, doc brand voice, etc.)
├── research.md        # Rédigé en Phase 1 (INIT)
├── progress.md        # Machine à états — voir Étape 1.1.1 pour le schéma
├── sections/
│   ├── 01.md          # Synthèse exécutive (rédigée en dernier, placée en premier)
│   ├── 02.md          # Cadre stratégique
│   ├── ...
│   └── 13.md          # Mesure, RACI, décisions ouvertes, annexe
└── final_plan.md      # Livrable compilé (sortie de la Phase 3)
```

### Étape 1.1.1 — Schéma d'état de `progress.md`

Chaque plan suit un unique fichier `progress.md` à la racine du plan. C'est la source de vérité pour la reprise. Schéma :

```markdown
# {Client} — Avancement du plan marketing

phase: init | review | finalize | finalized
current_section: <numéro, significatif uniquement pendant la phase review>
plan_version: v1
last_updated: AAAA-MM-JJ HH:MM

## Sections terminées
- [ ] 2. Cadre stratégique
- [ ] 3. État des lieux
- [ ] 4. Acquisition
- [ ] 5. Activation
- [ ] 6. Rétention
- [ ] 7. Recommandation (Referral)
- [ ] 8. Revenu
- [ ] 9. Feuille de route 90 jours
- [ ] 10. Perspective 12 mois
- [ ] 11. Stack des opérations marketing
- [ ] 12. Banque d'idées tactiques
- [ ] 13. Mesure, RACI, décisions ouvertes, annexe
- [ ] 1. Synthèse exécutive (synthétisée en dernier)

## Artefacts approuvés
sections/02.md, sections/03.md, ... (lister au fur et à mesure qu'ils sont rédigés)

## Notes
<toute décision ouverte, blocage ou contexte hors-bande qui ne figure pas dans research.md>
```

### Étape 1.1.2 — Arbre de décision de reprise

À chaque invocation, vérifier l'état dans cet ordre :

1. **Aucun dossier `{client-slug}/`** → nouveau plan. Créer le dossier + `materials/` + `sections/` vide. Démarrer INIT (Étape 1.2).
2. **Le dossier existe, pas de `research.md`** → INIT a été interrompu. Reprendre à l'Étape 1.2.
3. **`research.md` existe, pas de `progress.md`** → INIT terminé, REVIEW non démarré. Créer `progress.md`, démarrer REVIEW à la Section 2.
4. **`progress.md` existe, `phase: review`** → REVIEW en cours. Reprendre à `current_section` (ou à la première case non cochée).
5. **`progress.md` existe, `phase: finalize`** → FINALIZE a été interrompu. Relancer la Phase 3.
6. **`progress.md` existe, `phase: finalized`** → le plan est terminé. **Ne pas écraser silencieusement.** Demander à l'utilisateur : *« Ce plan est finalisé (v{N}). Voulez-vous (a) le réviser en v{N+1}, (b) démarrer un nouveau plan dans un nouveau dossier, ou (c) rouvrir une section spécifique ? »*

Mettre à jour `phase` et `last_updated` à chaque changement d'état.

### Étape 1.2 — Lire les matériaux existants

Si `materials/` contient des fichiers, tous les lire. Dépôts courants :
- Pitch deck / deck investisseur
- Doc de positionnement / doc brand voice
- Recherche client / doc ICP
- Métriques App Store / snapshot analytics
- Inventaire des emails de cycle de vie
- Sortie d'audit antérieure (toute évaluation notée de l'état actuel réalisée par l'équipe)
- Recherche SEO (`seo/plan.md`, `seo/keyword-shortlist.md`)
- Transcript de l'appel de kickoff
- Notes Slack / asynchrones du fondateur

Tout lire. Capturer les faits clés dans `research.md` au fil de l'eau.

### Étape 1.3 — Tirer les données live là où c'est branché

Si des MCP/API sont branchés pour ce client, tirer :

- **Ahrefs** → domain rating, mots-clés organic, backlinks, top pages, domaines référents (selon le skill `/seo-audit`)
- **GA4 MCP** → trafic par canal, événements de conversion, courbes de rétention
- **Stripe MCP** → MRR, ARR, churn, mix de plans, LTV blended par cohorte
- **App Store Connect** (manuel ou `dev-browser`) → funnel install → trial → payant ; rétention par cohorte
- **Customer.io MCP** → inventaire des flows, taux d'envoi / ouverture / clic / désinscription
- **Shopify** → conversion des pages produit, AOV, taux de réachat
- **GitHub MCP** → inventaire des repos, dates des derniers commits, ce qui est obsolète
- **Notion** → annuaire de connaissances internes s'il est exposé

Ne pas demander à l'utilisateur de copier/coller des données qui peuvent être tirées directement.

### Étape 1.4 — Mener un intake structuré

Pour chaque trou dans les matériaux, interroger l'utilisateur. L'intake minimal couvre dix sujets :

#### Intake 1 — Vue d'ensemble du client
- Que fait l'entreprise, en une phrase (mots du fondateur) ?
- Quel est le produit principal ?
- Quels autres produits / SKU / paliers existent ?
- Le produit est-il live, en bêta ou en pré-lancement ?
- Si bêta : throttling ? Calendrier de GA (disponibilité générale) ?

#### Intake 2 — ICP
- Pour qui êtes-vous, en une phrase ?
- Que disent-ils vouloir ?
- Que veulent-ils réellement ?
- Quel est leur problème déclaré ? Leur vrai problème ?
- Démographie / firmographie : qui correspond exactement à l'ICP ?

#### Intake 3 — État du funnel aujourd'hui
- Quels sont les chiffres actuels du funnel ? (inscriptions, activations, payants, rétention)
- Quelle est la *forme* du funnel — le goulot d'étranglement est-il en haut, au milieu ou en bas ?
- Où est la plus grosse fuite ?

#### Intake 4 — État du financement
- Tour actuel (pre-seed / seed / Série A / etc.) ?
- Total levé à ce jour ?
- Burn / runway actuels ?
- Levée active ? Closing prévu quand ?
- Investisseurs notables ?
- Permission de mentionner la mission fCMO dans les pitchs ?

#### Intake 5 — Équipe
- Fondateurs et ce que chacun pilote (produit, marketing, ventes, etc.) ?
- Autres rôles dans l'équipe et leur surface marketing ?
- Conseillers qui touchent au marketing ?
- Agences / contractors / fractionals ?
- Où sont les trous évidents ?
- Pour l'actuel responsable marketing de l'équipe (s'il y en a un) : sa forme est-elle en π (deux jeux de compétences profonds), en T (un profond, large) ou purement tactique ? Voir [team-and-agency-model.md](team-and-agency-model.md) pour le cadre qui alimente le RACI de la Section 11 et la recommandation de premier recrutement de la Section 9.

#### Intake 6 — Budget
- Dépense marketing mensuelle actuelle, ventilée : acquisition payante, outils, retainers, masse salariale ?
- Palier de budget auquel cela correspond (voir [funding-stage-unlocks.md](funding-stage-unlocks.md)) ?
- Quel budget se débloque quand le prochain tour clôture ?
- CAC blended si connu (incluant salaires, coûts de contenu, outils, retainers — pas seulement la dépense pub payante). Si inconnu, le signaler comme la décision ouverte n°1 de la Section 13 — chaque projection de revenu en dépend.
- ARPC, taux de rétention annuel (ou taux de churn), pour que les calculs de budget de [budget-planning.md](budget-planning.md) puissent être appliqués à la Section 8 (Revenu) et à la Section 10 (perspective 12 mois).

#### Intake 7 — Canaux actuellement actifs
- Acquisition : SEO organic, paid search, paid social, contenu, social, partenariats, événements, RP, ambassadeurs, etc. — pour chacun, statut (live / en pause / jamais testé)
- Activation : état de l'onboarding, flow d'inscription, paywall, expérience de première session, fiche app store
- Rétention : état des emails de cycle de vie, upsells in-app, cohorte de churn
- Recommandation (referral) : existence d'un programme, attribution, intérêt entrant
- Revenu : structure de prix, mix de plans, expériences récentes

#### Intake 8 — Déjà fait
Quel travail passé ce plan doit-il reconnaître ?
- Lancements majeurs et dates
- Moments RP et qui a couvert
- Piliers de contenu / hubs / pièces fondatrices
- Partenariats
- Récompenses / certifications
- Clients / utilisateurs notables (si utilisateurs nommables en grand public)
- Conseillers / fractionals passés

#### Intake 9 — En cours et bloqué
- Qu'est-ce qui est rédigé mais pas expédié ? Pourquoi ?
- Qu'est-ce qui est « presque prêt » depuis des mois ?
- Qu'est-ce qui bloque chaque élément ?
- Qu'est-ce qui est cassé ou activement nuisible ?

#### Intake 10 — Posture stratégique
- La chose la plus importante à corriger ce trimestre (lecture du fondateur)
- La chose la plus importante à ignorer ce trimestre (lecture du fondateur)
- Ce sur quoi les investisseurs / le board posent le plus de questions
- Toute contrainte non visible ailleurs (juridique, liée à un partenariat, liée à la marque)

### Étape 1.5 — Noter l'état actuel selon la grille

Utiliser la grille en 17 sections de `references/current-state-rubric.md` comme lentille de notation. Deux modes :

- **À partir de matériaux riches.** Quand l'équipe a partagé des decks, des audits de contenu antérieurs, un doc brand voice existant, un travail de positionnement récent ou un transcript de kickoff — noter à partir de là. Marquer « noté à partir des matériaux » dans le titre de section.
- **À partir d'un audit déjà noté séparément.** Si l'équipe a déjà une évaluation notée de l'état actuel (quel que soit le format), ingérer ces chiffres directement. Ne pas refaire le travail.

Dans les deux cas, la sortie est le tableau noté de 17 lignes qui devient la Section 3 du plan, suivi d'une « interprétation de forme » de 2 à 4 phrases qui pointe où se regroupent les forces et les trous.

### Étape 1.6 — Rédiger research.md

Compiler tout dans `research.md` avec cette structure :

```markdown
# {Client} — Dossier de recherche du plan marketing

**Date :** AAAA-MM-JJ
**Auteur :** (nom du fCMO / planificateur)

## Snapshot de l'entreprise
- Description en une phrase
- Stade (pre-seed / seed / Série A / etc.)
- Statut produit (bêta / GA)

## ICP
- ICP principal
- Problème déclaré vs. réel
- Démographie / firmographie

## État du funnel aujourd'hui
- Chiffres actuels
- Forme du funnel
- Plus grosse fuite

## Financement
- Total levé
- Statut du tour actuel
- Runway

## Équipe
- Fondateurs et périmètres
- Surface marketing par personne
- Trous

## Budget marketing actuel
- €/mois total
- Ventilation
- Mapping de palier

## Canaux actuellement actifs
[Par étape AARRR]

## Déjà fait (à reconnaître dans le plan)
[Liste]

## En cours et bloqué
[Liste avec blocages]

## Posture stratégique
- Priorité n°1 du fondateur
- Dépriorisation n°1 du fondateur
- Points de pression des investisseurs
- Contraintes

## Scores de la grille d'état actuel
[17 scores de section avec `references/current-state-rubric.md`. Si un audit noté antérieur existe, coller ces scores. Sinon marquer « noté à partir des matériaux ».]

## Matériaux lus
[Liste des fichiers de materials/ + date de lecture]
```

Enregistrer. Passer à la Phase 2.

---

## Phase 2 — REVIEW (rédaction section par section)

**Objectif :** parcourir les 13 sections du template de plan ([plan-template.md](plan-template.md)), rédiger chacune, obtenir la confirmation de l'utilisateur, enregistrer au fil de l'eau.

### Étape 2.1 — Initialiser progress.md

Utiliser le schéma défini à l'Étape 1.1.1 ci-dessus. Fixer `phase: review`, `current_section: 2`, `plan_version: v1`, et horodater `last_updated`.

### Étape 2.2 — Parcourir chaque section dans cet ordre : 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, puis 1

La Section 1 (synthèse exécutive) est rédigée **en dernier** car elle dépend des conclusions de toutes les autres sections. Parcourir les Sections 2 → 13 dans l'ordre numérique, puis synthétiser la Section 1 à partir des autres. Le `final_plan.md` compilé est toujours présenté dans l'ordre canonique 1 → 13.

Pour chaque section, utiliser le template de [plan-template.md](plan-template.md) pour rédiger. Puis en chat :

1. Présenter le brouillon (ou les puces clés — sections courtes en ligne, sections longues sous forme de plan à puces d'abord)
2. Demander : *« Approuver, ajuster ou développer ? »*
3. Itérer jusqu'à confirmation de l'utilisateur
4. Enregistrer le texte confirmé dans `sections/01.md` ... `sections/13.md` (un fichier par section, numéro complété par un zéro pour l'ordre de tri). C'est l'artefact persisté canonique — la récupération en dépend.
5. Cocher la case dans `progress.md`
6. Passer à la section suivante

### Étape 2.3 — Conseils spécifiques par section

**Section 1 (synthèse exécutive)** est synthétisée à partir des Sections 2–13 une fois toutes approuvées. La rédiger en dernier ; la présenter en premier dans le document de sortie.

**Section 3 (état des lieux)** utilise la grille en 17 sections intégrée à `references/current-state-rubric.md`. Si un audit noté antérieur existe, y coller ces scores. Sinon, noter à partir des matériaux disponibles.

**Sections 4–8 (AARRR)** suivent chacune la même structure interne : état actuel, le plan (mouvements numérotés), mouvements à 90 jours, perspective 12 mois, skills + outils. Ne pas sauter la sous-section skills + outils — c'est ce qui rend le plan opérationnellement honnête.

**Section 11 (stack des opérations marketing)** est auto-générable à partir de [ops-stack-mapping.md](ops-stack-mapping.md) plus les mouvements spécifiques nommés dans les Sections 4–8.

**Section 12 (banque d'idées)** est auto-générable à partir de `references/idea-cross-reference.md` plus des filtres spécifiques au client (sauter les idées qui entrent en conflit avec la brand voice ; déplacer les statuts selon le timing du stade de financement).

**Section 13** se trouve à la fin. Les décisions ouvertes doivent être classées par impact. L'annexe ne doit référencer que des fichiers accessibles à l'équipe (avertir au sujet des chemins locaux à la machine).

### Étape 2.4 — Cohérence de brand voice

Si le client a des règles de brand voice documentées (capturées dans research.md / Section 2), chaque section doit les respecter. Contraintes de voix courantes :
- Règles de vocabulaire (listes OUI / NON)
- Règles de CTA (ex : « ne jamais mettre la pression »)
- Cadrage initiatique vs. explicatif
- Ton (ex : faisant autorité mais accessible, intime mais professionnel)

Si le brouillon d'une section viole la brand voice, le refaire avant de le montrer à l'utilisateur.

---

## Phase 3 — FINALIZE (compiler + vérifier + publier)

**Objectif :** produire `final_plan.md` et, optionnellement, publier dans un repo partagé.

### Étape 3.1 — Compiler

Fixer `phase: finalize` dans `progress.md` avant de commencer. Concaténer `sections/01.md` à `sections/13.md` dans `final_plan.md` (ordre canonique 1 → 13, quel que soit l'ordre de rédaction). Ajouter :
- En-tête de titre avec date et marqueur de version « v1 »
- Frontmatter « Préparé par / Pour / Date / Statut »
- Ancres de section qui fonctionnent au collage dans Notion

### Étape 3.2 — Passe de vérification

Avant impression :

- **Vérification des renvois croisés** — chaque numéro d'idée marketing (ex : « idée #17 ») correspond à l'idée réelle dans `references/idea-cross-reference.md`. Chaque mention de skill apparenté existe soit dans le repo `marketingskills`, soit est documentée comme dépendance externe (voir la note de ops-stack-mapping sur les skills inter-marketplaces).
- **Vérification MCP/API** — chaque outil mentionné en Section 11 existe réellement dans le stack de l'utilisateur (selon l'intake de research.md) OU est signalé comme « futur / pas encore branché ».
- **Vérification des chemins** — aucun chemin spécifique à une machine (`/Users/...`, `/home/...`) dans la sortie. Remplacer par des références descriptives.
- **Vérification de voix** — relecture finale contre les règles de brand voice. Signaler et corriger les violations.
- **Vérification des décisions ouvertes** — chaque « TBD » ou question sans réponse de l'intake est listé dans les décisions ouvertes de la Section 13, pas caché dans le corps.
- **Vérification des reconnaissances** — chaque élément « déjà fait » de research.md est reconnu quelque part dans le plan.

### Étape 3.3 — Imprimer

Sortir `final_plan.md` dans le dossier du plan. Imprimer un résumé en chat :

> *« Plan marketing v1 enregistré dans `~/marketing-plans/{client-slug}/final_plan.md`. ~X XXX mots répartis sur 13 sections. Prêt à coller dans Notion ou à partager avec l'équipe. »*

### Étape 3.4 — Publier (optionnel)

Demander à l'utilisateur :
> *« Voulez-vous que je publie ceci dans un repo GitHub partagé pour que l'équipe puisse y accéder ? Si oui, quel est le repo et le chemin cibles (ex : `{client-org}/{client-context}/marketing/plan.md`) ? »*

Si oui :
- Cloner (ou supposer cloné) le repo cible
- Sortir une branche de feature ou pousser directement sur main selon la préférence de l'utilisateur
- Copier `final_plan.md` vers le chemin cible
- Ajuster l'annexe pour utiliser des chemins relatifs au repo (pas des chemins machine)
- Commit + push
- Confirmer avec l'URL du commit

Si non : laisser en local. Terminé.

### Étape 3.5 — Marquer finalisé

Fixer `phase: finalized` dans `progress.md` et horodater `last_updated`. C'est l'état terminal et il empêche les futures invocations de `/marketing-plan` d'écraser silencieusement le plan (voir Étape 1.1.2 cas 6).

---

## Reprendre un plan

La reprise est entièrement gouvernée par l'arbre de décision de l'Étape 1.1.2 ci-dessus — toujours vérifier l'état dans cet ordre à chaque invocation.

Si l'utilisateur dit *« recommencer »* → demander s'il veut supprimer le dossier existant ou d'abord le déplacer vers `archive/` ; ne pas écraser silencieusement.
Si l'utilisateur dit *« refaire la Section X »* → décocher cette case dans `progress.md`, supprimer `sections/0X.md`, et re-rédiger.

## Modes d'échec à surveiller

- **Sauter l'intake.** Un plan rédigé sans intake correct est générique et ne survivra pas au contact du fondateur. Toujours faire l'intake complet sur les dix sujets, sauf si l'utilisateur y renonce explicitement.
- **Prétendre que des données existent.** Si vous ne pouvez pas confirmer un chiffre (MRR actuel, taux de rétention, etc.), ne pas deviner. Le marquer `[TBD — à confirmer avec l'équipe]` dans le plan et l'ajouter aux décisions ouvertes.
- **Ignorer la brand voice.** Si le client a une voix forte (la plupart en ont une), chaque section doit la respecter. Lire les règles de voix avant de rédiger tout texte proche du copy.
- **Gonfler la banque d'idées.** La Section 12 n'est exhaustive que si elle inclut la liste des idées écartées avec leurs raisons. Ne pas la gonfler avec des idées qui clairement ne collent pas juste pour atteindre les 139.
- **Édulcorer les métriques inconfortables.** Si le churn est élevé ou l'activation faible, le nommer dans l'État des lieux. Les fondateurs lisent au-delà de l'enrobage.
- **Oublier la logique de stade de financement.** Si le client est en pleine levée, le plan doit expliquer ce qui change quand le tour clôture. Sauter cela transforme un plan en liste de souhaits.
