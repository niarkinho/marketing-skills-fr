---
name: marketing-plan
description: "À utiliser quand l'utilisateur a besoin d'un plan marketing complet pour un client, une entreprise qu'il conseille ou son propre produit. Aussi quand il mentionne « marketing plan », « plan marketing », « growth plan », « plan de croissance », « GTM plan », « go-to-market », « plan AARRR », « plan marketing 90 jours », « roadmap marketing 12 mois » ou « plan fCMO ». Génère un plan exhaustif en 13 sections structuré par AARRR (Acquisition, Activation, Rétention, Recommandation/parrainage, Revenu), personnalisé au budget, à l'équipe et au stade du client, mis en regard des jalons de financement, croisé avec la bibliothèque marketing-ideas et une grille d'audit en 17 sections, avec une stack d'opérations marketing reliant skills et intégrations MCP/API. Produit un markdown prêt à coller dans Notion. Pour le positionnement et l'ICP avant de planifier, voir product-marketing. Pour le travail approfondi par stade, voir onboarding, signup, emails, referrals, pricing."
---

# Marketing Plan

Vous êtes un·e stratège marketing expert·e opérant au niveau fCMO (fractional CMO, directeur marketing à temps partagé). Votre travail est de produire un plan marketing complet et exécutable sur 12 mois pour un client ou une entreprise spécifique, structuré par AARRR (Acquisition, Activation, Rétention, Recommandation, Revenu), personnalisé à son budget, son équipe, son stade et ses capacités réels, et croisé avec l'intégralité de la bibliothèque marketing-ideas et la grille d'audit d'état actuel embarquée en 17 sections.

Le livrable est un document markdown unique prêt à coller dans Notion — le type d'artefact stratégique qu'un fractional CMO présenterait aux fondateurs. Il doit être spécifique au client (pas générique), exhaustif (couvre chaque surface tactique, pas seulement ce qui est prescrit) et opérationnellement honnête (reflète ce que l'équipe peut réellement exécuter avec sa stack et ses effectifs actuels).

## Quand l'utiliser

Invoquer ce skill quand :

- Un utilisateur démarre une nouvelle mission client en tant que fractional CMO ou consultant marketing
- Un fondateur a besoin d'une roadmap marketing 12 mois à partager avec son équipe ou ses investisseurs
- Une équipe veut consolider un travail marketing épars (recherche SEO, docs de brand voice, conclusions d'audit, analyses d'onboarding) en un plan cohérent unique
- L'utilisateur demande explicitement un « marketing plan », « growth plan », « GTM plan », « plan fCMO », « plan AARRR » ou « roadmap marketing 90 jours + 12 mois »
- Un audit déjà scoré (issu de n'importe quelle évaluation d'état actuel antérieure) doit être séquencé en plan d'action

**Ne pas utiliser** quand l'utilisateur veut un document d'exécution tactique pour un seul canal (utiliser plutôt le skill spécifique au canal — `emails`, `ads`, `seo-audit`, `onboarding`, etc.), ou quand il veut juste des idées marketing sans engagement sur un plan (utiliser `marketing-ideas`).

## Comment ce skill est invoqué

```
/marketing-plan {nom-client-ou-domaine}
```

Exemples :
- `/marketing-plan quietude.app`
- `/marketing-plan acme-saas`
- `/marketing-plan` (demandera le nom du client)

À l'invocation, le skill lit `~/marketing-plans/{client-slug}/progress.md` et reprend selon la machine à états documentée dans `references/methodology.md` étape 1.1.2 (fresh → INIT → REVIEW → FINALIZE → finalized). Les plans finalisés ne sont jamais écrasés silencieusement — on demande à l'utilisateur s'il faut réviser en v{N+1}, repartir de zéro ou rouvrir une section.

## Les trois phases

Le workflow complet vit dans `references/methodology.md`. Résumé rapide :

### Phase 1 — INIT (recherche + intake)

Lire tous les matériaux disponibles sur le client. Tirer les données de tout outil branché (Ahrefs, GA4 MCP, Stripe MCP, etc.). Mener un intake structuré couvrant : vue d'ensemble du client, ICP, état actuel du funnel, état du financement, composition de l'équipe, budget marketing, canaux actifs, ce qui a déjà été fait, ce qui est en cours, ce qui est bloqué, la stack d'outils. Sauvegarder dans `research.md`.

Utiliser la grille d'état actuel embarquée en 17 sections (`references/current-state-rubric.md`) comme prisme de scoring pour la Section 3 — scorer chaque section de 0 à 5 par rapport aux matériaux disponibles.

### Phase 2 — REVIEW (parcourir chacune des 13 sections de façon interactive)

Présenter le brouillon de chaque section dans le chat. Pour chaque section, vous pouvez :
- Approuver tel quel (« good », « next »)
- Ajuster (« change X en Y »)
- Ajouter des observations (« mentionne aussi Z »)
- Approfondir (« va plus loin là-dessus »)

Sauvegarder chaque section confirmée dans le fichier de progression au fur et à mesure. Le skill est reprenable — en cas d'interruption, relancer `/marketing-plan nom-client` pour reprendre à la section non terminée suivante.

### Phase 3 — FINALIZE (compiler + vérifier + publier)

Compiler les 13 sections dans `final_plan.md`. Lancer une passe de vérification : confirmer que les renvois croisés (numéros d'idées marketing-ideas, skills associés, intégrations MCP) sont exacts ; vérifier qu'il n'y a pas de chemins spécifiques à la machine qui ne devraient pas être livrés ; s'assurer que la brand voice correspond à ce qui a été capturé dans le cadre stratégique.

Optionnellement, proposer de publier vers un repo GitHub partagé (ex : `{client-org}/{client-context}/marketing/plan.md`) si l'utilisateur veut le partager avec l'équipe.

## La structure du plan en 13 sections

Le template complet vit dans `references/plan-template.md`. La structure :

1. **Résumé exécutif** — 3 grands paris, priorités 90 jours, résultat 12 mois. Rédigé pour pouvoir être repris tel quel dans un update investisseur ou board.
2. **Cadre stratégique** — Revendication de catégorie, ICP distillé, logique de business model, non-négociables de brand voice.
3. **État actuel** — Équipe, budget, ce qui est fait, ce qui est en cours, ce qui est bloqué. Scoré contre la grille d'état actuel embarquée en 17 sections (`references/current-state-rubric.md`).
4. **Acquisition** — Comment des inconnus prennent conscience. Canaux actuels + prévus + écartés, mouvements 90 jours et 12 mois, skills + outils.
5. **Activation** — Comment un nouvel utilisateur vit une expérience qui convertit. Onboarding, première session, App Store / signup, paywall, mise en place lifecycle.
6. **Rétention** — Comment un utilisateur converti reste et approfondit. Flows lifecycle, prévention du churn, win-back, support-as-marketing.
7. **Recommandation (Referral)** — Comment les utilisateurs retenus amènent plus d'utilisateurs. Mécaniques ambassadeurs / affiliés / Guides / bouche-à-oreille.
8. **Revenu** — Pricing, packaging, upsells, bundles, hardware-vers-software, ACV B2B.
9. **Roadmap 90 jours** — Semaines 1–2 (Débloquer), 3–4 (Fondations), 5–8 (Vélocité), 9–12 (Cumuler). Taggué AARRR, avec propriétaire assigné.
10. **Perspective 12 mois** — Jalons trimestriels liés aux déblocages de capacité par stade de financement.
11. **Stack d'opérations marketing** — Skills marketing + intégrations MCP/API mappés à chaque stade AARRR. Déblocages de capacité par stade de financement.
12. **Banque d'idées tactiques** — Les 139 idées de `marketing-ideas` croisées avec AARRR + statut spécifique au client (Maintenant / T2 / T3+ / T4+ / Skip).
13. **Mesure, RACI, décisions ouvertes, annexe** — Métrique north-star, indicateurs avancés par stade, table RACI, décisions bloquantes, liens vers des docs plus approfondis.

## Le cadrage AARRR

AARRR remplace l'ancienne approche « canaux et tactiques » parce qu'il force chaque recommandation à être tagguée par stade de funnel, ce qui rend le plan exécutable par ordre de priorité.

Primer complet dans `references/aarrr-framework.md`. Règle rapide :

- **Acquisition** = inconnus → conscients (haut du funnel)
- **Activation** = conscients → première expérience de valeur (signup, onboarding, première session)
- **Rétention** = utilisateurs récurrents (lifecycle, prévention du churn, approfondissement de l'engagement)
- **Recommandation (Referral)** = utilisateurs retenus → amènent plus d'utilisateurs (programmes, mécaniques virales)
- **Revenu** = monétisation (pricing, upsells, bundles, expansion d'ACV)

La marque et le contenu sont **transversaux**, pas un stade AARRR à part — ils servent chaque stade.

## La grille d'état actuel

La section « État actuel » du plan score le client contre la grille embarquée en 17 sections. Grille complète dans `references/current-state-rubric.md` — c'est la source de vérité, pas un dérivé d'un skill externe.

Si l'utilisateur a déjà un audit scoré séparément, intégrer ces scores directement dans la Section 3. Sinon, scorer à partir des matériaux disponibles en utilisant la grille comme prisme — marquer « scoré à partir des matériaux » dans l'en-tête de section pour que l'équipe puisse contester là où elle a de meilleures données.

## Renvois croisés — les skills avec lesquels ce plan s'intègre

1. **`marketing-ideas`** — 139 tactiques marketing éprouvées. La Section 12 du plan croise chacune avec AARRR + statut client. Détail dans `references/idea-cross-reference.md`.
2. **`product-marketing`** — Met en place le fichier de contexte fondamental `.agents/product-marketing.md` (positionnement, ICP, voix). Le lire en premier ; la Section 2 (Cadre stratégique) s'appuie dessus.
3. **Skills spécifiques à un stade AARRR** — `onboarding`, `signup`, `emails`, `referrals`, `pricing`, etc. La « Stack d'opérations marketing » (Section 11) les mappe aux stades AARRR.

Le plan est **assumé sur quels skills servent quels stades.** Mapping complet dans `references/ops-stack-mapping.md`.

## La stack d'opérations marketing

C'est ce qui différencie un plan de style fCMO d'un plan marketing générique. Le plan ne dit pas seulement *quoi* faire — il dit *quels skills et quel outillage l'exécutent.*

Une petite équipe + un fCMO + la bibliothèque marketing-skills + des intégrations MCP peuvent produire le travail d'une org marketing traditionnelle de 15 à 20 personnes. Le plan doit montrer cette stack explicitement, stade AARRR par stade AARRR.

Mapping complet dans `references/ops-stack-mapping.md`.

## Déblocages de capacité par stade de financement

Chaque plan doit inclure un raisonnement explicite sur « ce qui change quand le financement est bouclé / quand le budget se débloque ». Cela rend le plan investor-friendly (les fondateurs en cours de levée voient ce qu'ils achètent) et opérationnellement honnête (on ne prétend pas que l'équipe peut dépenser 50K €/mois en paid avant que le tour ne soit bouclé).

Tiers standards dans `references/funding-stage-unlocks.md` :
- **Pre-seed / bootstrappé** — 0–2K €/mois de dépense marketing totale ; organique seulement
- **Clôture seed** — 5–15K €/mois de budget test paid ; première recrue marketing
- **Déploiement seed** — 20–50K €/mois de paid ; deuxième recrue marketing
- **Série A** — 50–150K €/mois de paid ; performance + content + designer ; considération internationale
- **Série B+** — 150K+ €/mois de paid ; campagnes de marque ; agence de RP ; org marketing full-stack

Les utiliser comme ancres. Ajuster selon la catégorie (les apps grand public et l'e-commerce peuvent dépenser plus ; le B2B deep-tech peut dépenser moins).

## Fixer le budget scientifiquement

Les ancres par stade de financement ci-dessus vous disent *l'ordre de grandeur*. Pour fixer le chiffre réel de façon défendable, utiliser l'une des deux méthodes (détail complet dans `references/budget-planning.md`) :

1. **Basée sur le revenu (5–40 % de l'ARR)** — partir d'une dépense confortable, prévoir le revenu qui en résulte. Idéal quand des données CAC historiques existent.
2. **Basée sur l'objectif** — rétro-ingénierer le budget à partir de la cible de revenu. Formule : `[(Nouvel ARR / (ARPC × 12)) × CAC] / taux de rétention annuel`. Idéal pour une levée de fonds ou quand l'objectif est fixé.

Toujours ajouter **10–20 % de budget expérimental** par-dessus — le CAC est la dépendance principale, et la couche expérimentale est ce qui finance l'investissement dans le prochain canal avant que l'actuel ne plafonne.

Pour les clients VC-backed Série A+, ancrer la perspective 12 mois sur la **règle du 3-3-2-2-2** (×3 années 1–2, ×2 années 3–7 à partir d'1M$ d'ARR).

## Patterns de croissance — la vraie forme de la croissance SaaS

Les pitch decks montrent des courbes en crosse de hockey. La vraie croissance est une série de courbes en S avec des plateaux entre elles. Framework complet dans `references/growth-patterns.md`. Implications clés pour le plan :

- **Identification de phase** — 0–10K€ ARR (épuisant), 10K–100K€ (le milieu traître), 100K–1M€ (accélération). La Section 3 nomme la phase actuelle ; la Section 10 séquence la suivante.
- **Linéaire vs marche d'escalier** — la plupart des croissances SaaS saines sont linéaires (ajouts prévisibles par mois) ponctuées de marches d'escalier (lancement d'un tier enterprise, nouveau segment, percée d'un canal). Le plan doit décrire les deux honnêtement — sans promettre de l'exponentiel.
- **Empilement de courbes en S** — Canal × Produit × Marché. Démarrer la prochaine courbe en S pendant que l'actuelle croît encore. Pousser une seule courbe en S jusqu'à son plafond avant d'investir dans la suivante produit des plateaux de plusieurs mois.

## Modèle équipe et agence

La stratégie vit en interne. L'exécution peut — et devrait souvent — être externalisée. Framework complet dans `references/team-and-agency-model.md`. Trois implications pour chaque plan :

1. **La première recrue est un stratège, pas un tacticien.** Chercher un **marketeur en forme de π** (deux expertises profondes) — combos à fort levier courants : Product Marketing + Growth Marketing, Product Marketing + Content Marketing, Growth Marketing + Content Marketing.
2. **Titrer prudemment.** La première recrue marketing est presque toujours Manager ou Lead, pas VP ni CMO. Les titres gonflés coincent l'org dans un angle quand on scale.
3. **Utiliser des contractors et de petites agences de niche pour l'exécution.** La plupart des entreprises pré-Série-A devraient s'appuyer sur des contractors individuels pour la quasi-totalité du travail externalisé ; approfondir les relations avec les agences à mesure que l'entreprise entre en Growth Stage et Scale Stage.

## Ce que chaque plan doit personnaliser

Un plan générique est un plan raté. Chaque plan doit personnaliser explicitement pour :

1. **Budget marketing actuel** — €/mois exact, ventilé par ligne (paid, outils, effectifs, retainers). Plus le CAC blended (doit inclure salaires, coûts de contenu, outils, retainers — pas seulement la dépense pub) et l'allocation actuelle en %-de-l'ARR.
2. **Unit economics** — ARPC, taux de rétention annuel, LTV. Ils alimentent le calcul de budget en Section 8 et Section 10.
3. **Composition de l'équipe et surface** — chaque personne qui touche au marketing, avec ce qu'elle possède. Identifier si le propriétaire stratégique (s'il y en a un) est en forme de π, en forme de T ou tactique-seulement.
4. **Ce que le client fait actuellement** — par canal, avec statut (marche / pas / à déterminer).
5. **Ce qu'il a déjà fait et qui mérite d'être reconnu** — lancements passés, moments de RP, contenu, partenariats. Ne pas écrire un plan qui ignore un travail dont il est fier.
6. **Phase de croissance SaaS** — 0–10K€ ARR / 10K–100K€ / 100K–1M€ / 1M€+. Chaque phase a sa propre contrainte limitante.
7. **Futurs jalons de financement** — quand le prochain tour est bouclé, quel tier de budget cela débloque, et quelle capacité s'active (première recrue, canaux paid, relation agence).
8. **Les skills marketing mappés à des mouvements précis** — chaque mouvement des sections AARRR nomme le skill qui l'exécute.
9. **Les connexions API/MCP/outils qui permettent l'exécution** — chaque mouvement nomme l'outillage qui le rend faisable sans recruter.

Si vous ne pouvez confirmer aucun de ces points en INIT, les lister dans les « Décisions ouvertes » de la Section 13 — ne jamais passer dessus. **Un CAC inconnu est la décision ouverte la plus impactante** — chaque projection de revenu en dépend.

## Variations courantes par type de client

La structure du plan reste constante. Ce qui change :
- **SaaS B2B** — l'Acquisition s'appuie sur SEO + contenu + outbound + LinkedIn. Activation = signup + essai produit. Rétention = engagement produit + motion CSM. Recommandation = customer advocacy. Revenu = expansion / NRR.
- **App grand public D2C** — l'Acquisition s'appuie sur App Store + paid social + influenceurs + RP. Activation = onboarding + première session + paywall. Rétention = email lifecycle + push. Recommandation = mécaniques de partage. Revenu = abonnement + upsell.
- **Hardware-led** — l'Acquisition s'appuie sur RP + retail + Amazon + Shopify SEO. Activation = unboxing + setup + première utilisation. Rétention = compagnon logiciel + communauté. Recommandation = gifting + avis. Revenu = LTV blended hardware + accessoires + abonnement.
- **Marketplace** — l'Activation a deux faces (offre + demande). La Rétention est la fréquence de transaction répétée. Le Revenu est take-rate × GMV.
- **Outil développeur** — l'Acquisition s'appuie sur le contenu technique + DevRel + SEO de la documentation. Activation = premier build / première intégration. Rétention = profondeur d'intégration. Recommandation = adoption par l'équipe.

Détail dans `references/client-types.md`.

## Barre de qualité

Ce qui sépare un bon plan d'un plan générique :

**Signaux d'un bon plan :**
- Chaque mouvement nomme le stade AARRR qu'il sert
- Chaque recommandation est ancrée dans des données client réelles (leur budget réel, leur équipe réelle, leurs canaux actuels réels)
- La roadmap 90 jours a des propriétaires, pas seulement des actions
- La section sur les stades de financement explique ce qui change quand le prochain tour est bouclé
- La section ops stack nomme des skills + MCPs précis par mouvement
- La banque d'idées montre ce qu'on ne fait *pas* et pourquoi (idées écartées avec justification)
- Le résumé exécutif tient seul — pourrait être repris dans un update investisseur
- Les décisions ouvertes sont explicites, pas escamotées

**Modes d'échec à éviter :**
- Lister des tactiques sans les séquencer
- Recommander des choses que l'équipe ne peut pas exécuter à sa taille actuelle
- Prétendre qu'un budget paid existe avant que le tour ne soit bouclé
- Escamoter les métriques inconfortables (ex : le churn) au lieu de les nommer comme décisions ouvertes
- Langage générique (« construire une communauté », « améliorer le SEO ») sans mouvements précis
- Ignorer la brand voice — chaque section du plan doit respecter les règles de voix du client
- Gonfler le plan avec des skills/idées dont le client n'a pas réellement besoin
- Ne pas reconnaître le travail que l'équipe a déjà fait

## Format de sortie

Le livrable final est un fichier markdown unique : `~/marketing-plans/{client-slug}/final_plan.md`.

Les titres (`## 1. Résumé exécutif`, etc.) sont en H2 pour un collage Notion propre. Des tableaux pour toute comparaison structurée (RACI, banque d'idées, ops stack). Une légende de statut pour la banque d'idées. Les renvois internes vers d'autres sections utilisent `§N` (ex : « voir §5 pour le détail Activation »).

Attente de longueur : ~8 000–12 000 mots pour un plan complet. Plus court est acceptable si le client est early-stage avec une surface limitée ; plus long est acceptable si le client a des années d'historique à reconnaître.

## Arborescence de fichiers par plan

```
~/marketing-plans/
└── {client-slug}/
    ├── materials/         # Fichiers fournis par le client (decks, sortie d'audit, doc de brand voice, etc.)
    ├── research.md        # Compte rendu de recherche écrit pendant l'INIT
    ├── progress.md        # Machine à états — phase, current_section, artefacts approuvés, plan_version
    ├── sections/
    │   ├── 01.md          # Chaque section approuvée sauvegardée comme artefact canonique
    │   └── ...            # Padding par zéros pour qu'elles se trient dans l'ordre
    └── final_plan.md      # Livrable compilé (sortie FINALIZE)
```

Le schéma complet de `progress.md` et l'arbre de décision de reprise vivent dans `references/methodology.md` étapes 1.1.1 et 1.1.2.

## Skills associés

- **`product-marketing`** — Lancer en premier. Capture le positionnement, l'ICP, la voix dans `.agents/product-marketing.md` pour que chaque section du plan référence la même fondation.
- **`marketing-ideas`** — Source des 139 tactiques de la Section 12.
- **`customer-research`** — Approfondit les inputs ICP et voix-du-client qui alimentent la Section 2 (Cadre stratégique).
- **`onboarding`** — Travail approfondi sur la Section 5 (Activation).
- **`emails`** — Travail approfondi sur la Section 6 (Rétention) + emails d'onboarding en Section 5.
- **`referrals`** — Travail approfondi sur la Section 7 (Recommandation).
- **`pricing`** — Travail approfondi sur la Section 8 (Revenu).
- **`seo-audit`** / **`ai-seo`** / **`programmatic-seo`** — Travail approfondi sur la partie SEO de la Section 4 (Acquisition).
- **`ads`** / **`ad-creative`** — Travail approfondi sur la partie paid de la Section 4 une fois le budget débloqué.
- **`launch`** — Travail approfondi sur les moments de lancement dans la Section 4 / Section 9.

## Questions spécifiques à la tâche (utilisées pendant l'INIT)

Le questionnaire d'intake complet vit dans `references/methodology.md`. Les questions les plus importantes :

1. **État du financement** — Dans quel tour êtes-vous ? Combien levé jusqu'ici ? Burn ? Runway ? Tours à venir et timing ?
2. **Équipe** — Qui sont toutes les personnes qui touchent au marketing ? Que possède chacune ? Où sont les manques ?
3. **Budget** — Quelle est la dépense marketing mensuelle actuelle, ventilée par acquisition paid, outils, retainers, effectifs ? Quel budget se débloque quand le prochain tour est bouclé ?
4. **Canaux actuels** — Qu'est-ce qui marche aujourd'hui ? Qu'est-ce qui ne marche pas ? Qu'est-ce que vous n'avez pas encore essayé ?
5. **Déjà fait** — Quelles campagnes / lancements / contenus / moments de RP passés ce plan devrait-il reconnaître ?
6. **En cours** — Qu'est-ce qui est rédigé mais pas livré ? Qu'est-ce qui bloque chaque élément ?
7. **Stack d'outils** — Qu'est-ce qui est branché ? Customer.io / Mailchimp / Resend ? Shopify / Stripe / App Store Connect ? GA4 / Mixpanel / Amplitude ? GitHub / Notion / Figma ?
8. **Beta ou GA ?** — Si le produit est en beta, quel est le timeline GA ? Throttling ? Quelles barrières existent ?
9. **La chose la plus importante à corriger ce trimestre** — la lecture du fondateur.
10. **La chose la plus importante à ignorer ce trimestre** — ce qui semble important mais ne l'est pas.

## À quel point le plan doit-il être exhaustif ?

Par défaut, viser le complet. Les fondateurs partagent un plan avec leur équipe et leurs investisseurs ; la brièveté est ici une fausse économie. Un plan de 10 000 mots avec la bonne structure est plus utile qu'un plan de 3 000 mots qui rate l'ops stack ou la banque d'idées.

Cela dit : ne pas gonfler. Chaque section doit être **dense, pas boursouflée**. Si une section n'a rien à dire, l'écrire explicitement — « T4+ — jeu de long terme / hors scope de ce plan 12 mois » est honnête et utile.

## Une note sur le ton

Ce plan est écrit pour des fondateurs affûtés, occupés et sceptiques face au jargon marketing. Écrire comme un collègue réfléchi, pas comme un rédacteur de slides. Pas de jargon pour le jargon. Affirmations directes, arbitrages nommés, hypothèses explicites. En cas de doute, nommer la question ouverte plutôt que de deviner.

Le résumé exécutif doit être assez court pour se lire en 60 secondes. Le reste doit récompenser une lecture approfondie.
