# Exemple — Plan marketing Quietude v1

**Ceci est l'exemple de référence canonique pour le skill `/marketing-plan`.** Il s'appuie sur une vraie mission de fCMO pour une plateforme de bien-être hybride hardware-et-software. **Les noms, domaines et détails identifiants ont été modifiés** — le client s'appelle ici « Quietude », et les membres de l'équipe ont été renommés (Alex / Sam / Casey / Devon). Les chiffres du funnel, le budget et les enseignements structurels conservent la forme de la mission d'origine, afin que l'exemple garde sa valeur pédagogique.

Utilisez-le comme référence « à quoi ressemble un bon plan » au moment de rédiger un nouveau plan. La structure, le ton, la profondeur et la précision opérationnelle sont la barre à atteindre.

**L'archétype de Quietude :** hardware + software hybride, avec une couche de crédibilité deep-tech / clinique. Voir `references/client-types.md` pour les patterns d'archétypes.

**Contexte du stade de financement :** pré-clôture du seed (en plein milieu d'une levée de seed de 3 M€). Tier 1 selon `references/funding-stage-unlocks.md`. Budget paid de 0 € ; organic + lifecycle + ambassadeurs uniquement.

**Ce qui était solide dans ce plan :**
- Le cadre stratégique (Section 2) s'appuyait sur le propre framing méditation-vs-régulation du fondateur comme pilier de contenu
- L'état actuel (Section 3) intégrait la grille d'audit en 17 sections scorée contre les supports existants (sans audit formel mené)
- La roadmap 90 jours (Section 9) avait des moves assignés à un owner, pas juste des actions
- La stack ops (Section 11) intégrait une preuve opérationnelle concrète (Customer.io MCP utilisé en live par un fondateur non technique lors du call de kickoff)
- La banque d'idées tactiques (Section 12) croisait les 139 marketing-ideas avec l'AARRR + un statut spécifique à Quietude, dont 23 skips explicites avec justification

---

# Quietude — Plan marketing v1

**Préparé par :** Casey Reed (fCMO)
**Pour :** Alex, Sam et l'équipe Quietude
**Date :** 2026-05-27
**Statut :** Draft v1 — pour relecture de l'équipe

## 1. Résumé exécutif

Quietude a construit quelque chose de rare : un produit cliniquement validé, cohérent en marque, porté par son fondateur, dans une catégorie qui n'a pas encore de nom. L'opportunité des douze prochains mois n'est pas d'inventer une machine marketing à partir de zéro — c'est de **convertir la gravité organique existante en un funnel mesurable et répétable**, puis d'empiler de l'acquisition paid par-dessus ce funnel une fois la levée de seed bouclée.

**Trois grands paris, classés par levier :**

1. **Colmater la fuite avant de verser de l'eau.** La forme du funnel Jour 1 → Jour 35 (1,34 % → 5,46 %) nous dit que le produit convertit dès qu'on lui donne du temps et du contact. Ce qui lui manque, c'est un premier moment de session qui marche (le gate des écouteurs tue la conversion) et une couche lifecycle pour délivrer ce contact. Ces deux pièces — refonte de l'onboarding et flows Customer.io shippés — sont le déblocage de tout le reste.
2. **Capitaliser sur les moats que Quietude possède déjà.** Étude clinique peer-reviewed, PR via un influenceur de la longévité, 15 000 participants en événements live, la voix fondateur d'Alex — ce sont des générateurs de liens, des piliers de contenu et des ancres de crédibilité que la plupart des marques de bien-être tueraient pour avoir. Ils sont sous-exploités. SEO, contenu et App Store optimization les traduisent en surface de recherche et de découverte.
3. **Construire le système d'exploitation fondateur-et-fCMO qui permet à une équipe de 4 personnes de faire le marketing d'une équipe de 20.** C'est ce qui rend le plan réellement exécutable à la taille d'équipe et au burn rate de Quietude — un outillage agentique par-dessus Customer.io, Shopify, App Store, Stripe, GitHub et la bibliothèque de skills marketing signifie qu'on ship sans recruter.

**À quoi ressemblent douze mois, de façon plausible :**

- L'app passe de la beta à la GA. L'onboarding convertit avec un lift significatif par rapport à la baseline d'aujourd'hui.
- 4 piliers de contenu SEO plantés, avec le Pilier 1 (Régulation du système nerveux) et le Pilier 2 (Sommeil + Masque) qui rankent sur des mots-clés Tier-1.
- Lifecycle complet en live dans Customer.io : onboarding, réengagement des inactifs, post-achat hardware, opt-ins du subscription center.
- Programme d'ambassadeurs en live avec 15 à 25 hôtes actifs. Premier pilote de certification des Quietude Guides lancé.
- Le wedge du masque vendu à l'échelle via Shopify avec un chemin propre hardware → activation app. CAC blended mesuré et suivi.
- Acquisition paid qui démarre post-clôture-seed sur un budget test initial de 5 à 10 K€/mois, scalant à 20–50 K€/mois si l'unit economics valide.
- La narrative de Series A s'écrit toute seule : preuve clinique + lift d'activation + effet de cumul lifecycle + premiers cas de référence d'installs B2B.

**Les priorités à 90 jours** (que le reste de ce document opérationnalise) :

1. Tuer le gate des écouteurs. Shipper le fix de fond cette semaine.
2. Lancer le test d'onboarding à trois variantes. Trouver le vainqueur d'activation.
3. Shipper les Flows Customer.io 6 (post-achat masque) et 4 (utilisateur inactif) — garder le Flow 2 (onboarding) en attente tant que l'UI de l'app n'est pas stabilisée.
4. Réécrire la fiche App Store dans la voix de marque de Quietude. L'asset hors-site au plus fort levier en ce moment.
5. Planter les fondations SEO : consolider sur `quietude.app`, publier le hub du Pilier 1 + 3 spokes, publier la landing page de l'étude de psychophysiologie peer-reviewed.
6. Lancer le programme d'ambassadeurs avec les ~5 inbounds en attente.

Tout le reste se cumule par-dessus ces six.

---

## 2. Cadre stratégique

Cette section distille le positionnement, l'ICP et la voix de marque en ce que l'équipe doit garder en tête pendant l'exécution. Le détail complet vit dans `marketing-os.md`, `icp.md` et `sound-philosophy.md`.

### Ce qu'est Quietude, en une phrase

Une plateforme d'intelligence du système nerveux — audio spatial cliniquement validé + compagnon de réflexion IA (Mira) + hardware + installations de lieux + réseau de praticiens. *« On commence par le son. On s'étend à chaque sens. On finit par les villes. »*

### La catégorie qu'on revendique (et qu'on défend)

Quietude ne rentre pas dans la catégorie des apps de méditation, ni dans celle de l'audio de concentration, ni dans celle de la tech du sommeil. La marque fait une revendication plus forte : **la régulation bottom-up du système nerveux via l'audio spatial**, avec la preuve clinique comme preuve et la crédibilité somatique comme défense.

Le cadre qui définit la catégorie, selon Alex (2026-05-19) : **La méditation est top-down. Quietude est bottom-up.** La méditation utilise l'esprit pour commander le corps — un kung-fu mental qui échoue précisément auprès des gens qui en ont le plus besoin, parce que le cortex préfrontal est hors-ligne sous stress. Quietude entre par le tronc cérébral, avant l'esprit pensant. Le corps répond avant d'avoir à essayer. (Traitement complet en pilier de contenu dans `meditation-vs-regulation.md`.)

C'est le message stratégique le plus important. Il a sa place dans la copy de l'App Store, l'onboarding, l'email lifecycle, le contenu SEO, les talking points des ambassadeurs et le deck de seed.

### Pour qui on est (ICP D2C, distillé)

Professionnels surstimulés et hauts performeurs, 25–45 ans, urbains (Bay Area, NYC, Londres, Berlin, Austin). Travailleurs de la tech, fondateurs, créateurs, universitaires, designers, consultants. Souvent neuro-atypiques (TDAH, HSP, surdoués). Acheteurs de bien-être sophistiqués — déjà fortement investis dans leur vie intérieure.

**Leur problème déclaré :** *« Je n'arrive pas à éteindre mon cerveau. J'ai essayé les apps de méditation. Elles ne marchent pas. »*

**Leur vrai problème :** la surstimulation, pas le manque de motivation. Leur don (la pensée rapide) est devenu une malédiction. Ils ont besoin de la permission d'arrêter d'optimiser — y compris leur repos.

**Ce qu'ils achètent vraiment :** le *sentiment* de stabilité, l'indulgence sensorielle, de beaux rituels, une efficacité sans effort, un raccourci luxueux vers le génie qu'ils ne peuvent pas atteindre dans le chaos.

### La logique du business model (selon le deck de seed)

**Le B2B ensemence le marché. Le D2C récolte.** Un install de lieu met Quietude devant ~20 K personnes/an pour un coût de ~17 K€ → 5 % convertissent en abonnés → ~430 K€/an par lieu. Six canaux à effet de cumul (referral, Guides, contenu, home hosting, PR, communauté) font tendre le CAC vers zéro d'ici l'An 3. An 5 : 75 % des nouveaux abonnés viennent de canaux à coût quasi-nul.

**Périmètre fCMO selon le kickoff : piloté par le D2C.** Alex possède les ventes B2B via les événements/le réseau/la crédibilité fondateur. Le levier fCMO est sur le côté D2C app/hardware. Ce plan reflète ce partage — le B2B est reconnu comme moteur de récolte mais pas traité comme surface de travail primaire.

### Voix de marque (le non-négociable)

Selon le Marketing OS :
- **Ton.** Autoritaire mais accessible. Intime mais professionnel. Révolutionnaire mais ancré. L'autorité vient de l'expérience vécue, pas de l'explication.
- **Parler depuis le corps, pas depuis l'esprit.** Chaque phrase restaure la sécurité somatique et l'orientation. Le langage ouvre l'espace plutôt qu'il ne ferme le sens.
- **Vocabulaire OUI :** vivacité, vie intérieure, système nerveux, son spatial, résonance, sécurité somatique, clarté incarnée, rythme naturel, orientation, initiation, parler-vrai.
- **Vocabulaire NON :** zen, chill, vibes, « high-vibe », bypass spirituel, clichés de méditation, langage didactique/explicatif, « laissez-moi vous expliquer pourquoi ça marche ».
- **Méthode cœur : la Réflexion Initiatique.** Le but de l'écriture n'est pas d'expliquer ni de convaincre — c'est de déplacer l'état intérieur du lecteur. Le résultat doit être *« quelque chose en moi a bougé »*, pas *« je comprends ce concept »*.
- **Règle CTA :** ne jamais mettre la pression. « On ne rappelle pas. On invite. »

Cette règle contraint chaque pièce de copy à travers chaque stage AARRR. Dans le doute : réécrire depuis le corps.

---

## 3. État actuel

Voici notre point de départ — équipe, budget, ce qui est déjà en mouvement, ce qui est bloqué, scoré contre la grille d'audit marketing CF en 17 sections.

### Composition de l'équipe (surface de travail marketing)

| Personne | Rôle | Surface de travail marketing |
|---|---|---|
| **Alex** | Co-fondateur, CEO | Possède : LinkedIn perso, événements live, ventes B2B, narrative fondateur, relations investisseurs, écriture de la voix de marque |
| **Sam** | Co-fondateur, CXO | Possède : crédibilité clinique/somatique, gardiennage de la voix de marque, angle somatique sur la relecture de copy, réseau de praticiens |
| **Devon** | Lead Dev | Possède : build produit/UI, instrumentation, câblage des events Customer.io, déploiement App Store |
| **Ed Dorsey** | Design Advisor | Cadence advisory (ex-Apple/Airbnb/Strava) |
| **Emily Babich** | Creative Strategy | Cadence advisory |
| **Matt Mikkelsen** | Field Recording | Bibliothèque audio, pas du marketing |
| **Casey Reed** | fCMO | Stratégie, lifecycle, SEO, tests d'onboarding, contenu, programme d'ambassadeurs, stack ops |

**Pas encore de recrutement marketing dédié.** Premier recrutement probablement post-clôture-seed (candidat Q3 2026) : un lifecycle + content marketing manager qui possède Customer.io, la production de contenu SEO et les opérations ambassadeurs au quotidien.

### Budget marketing (actuel)

- **Acquisition paid :** 0 €. Confirmé par Alex, 2026-05-20 : *« UA D2C jusqu'ici : mes posts LinkedIn perso, les événements Quietude live, le bouche-à-oreille organique et la découverte organique sur l'app store. »* Aucune couche paid.
- **Stack d'outils :** abonnement Customer.io, Shopify (boutique masque), App Store Connect, GA4 (ou en attente), Stripe, Notion, Dub.co (attribution ambassadeurs). Estimation ~500–1 500 €/mois cumulés.
- **Retainer fCMO :** mission Casey Reed.
- **PR :** pas de PR payée. Tailwind organique de l'influenceur longévité, réseau d'angels consumer-tech + labo de foundation models.

**Implication :** le plan 90 jours doit produire des gains sans aucun levier paid actionné. Tout dans les 12 prochaines semaines est organic, lifecycle, ou au niveau produit. Le paid est un déblocage Q2–Q3.

### Ce qui est déjà fait (reconnaître, puis capitaliser dessus)

| Asset | Statut | Levier marketing |
|---|---|---|
| Étude de psychophysiologie peer-reviewed (2025) | Publiée | Ancre de l'autorité clinique. L'asset le plus sous-marketé que Quietude possède. |
| Endorsement masque par un influenceur longévité | Live, génère des ventes Shopify | Hook presse. Sous-utilisé pour la preuve sociale en landing page. |
| Investissement d'angels consumer-tech + labo de foundation models | Clôturé | Opportunité de PR investisseur. Pièces « Pourquoi j'ai investi » sur Substack/Medium. |
| 15 K+ participants en événements live sur une décennie | Réel | Potentiel de liste email, pool d'ambassadeurs, banque de témoignages, référence B2B. |
| Masque Quietude (5 K en stock) | En vente | Le produit wedge. Chemin hardware → activation app. |
| 38 % de rétention à 12 mois (vs moyenne catégorie 20 %) | Réel | Métrique phare. A sa place partout. |
| Intégration Customer.io + Shopify | Câblée | L'infrastructure lifecycle existe. Les flows n'ont qu'à être shippés. |
| 4 repos GitHub pour le contexte + le produit | Mis en place | `quietude-context` (cerveau partagé), `quietude-promo`, `quietude-app` (app), `mira` (IA), `quietude-api` |
| Doc Sound Philosophy d'Alex | Doc de travail | Position paper linkable une fois poli et publié. |
| ~5 ambassadeurs inbound en attente | Inbound | Programme de referral prêt à lancer — pas de demand-gen nécessaire pour la v1. |
| Install B2B Aurora (~250 K€, deadline juillet) | En cours | Premier lieu flagship. Cas de référence une fois installé. |
| Notion Knowledge Directory | Live | Contexte interne. |
| Customer.io MCP (intégration Claude) | Validé au kickoff | L'équipe non technique peut shipper des flows en autonomie. |

### Ce qui est en cours (drafté mais pas shippé)

| Item | Statut | Bloqueur |
|---|---|---|
| Flow 2 — Onboarding app (8 emails / 14 jours) | Draft | UI de l'app en mouvement ; la copy référence des écrans qui peuvent changer |
| Flow 4 — Réengagement utilisateur inactif (5 emails / 38 jours) | Draft | Aucun — prêt à shipper |
| Flow 6 — Post-achat masque | Draft | Aucun — prêt à shipper |
| Refonte de l'onboarding (plan de test à 3 variantes) | Doc de stratégie fait | Cadrage eng + retrait du gate des écouteurs |
| Plan SEO 90 jours + keyword research | Fait | En attente de la décision de consolidation de domaine + démarrage de la production de contenu |

### Ce qui est bloqué (et qu'il faut débloquer ce trimestre)

| Problème | Coût de l'inaction | Action |
|---|---|---|
| Hard-gate des écouteurs dans l'onboarding | Chute de conversion confirmée post-lancement | Tuer cette semaine (fix de fond) |
| 4 domaines non consolidés (quietude.app, quietude.space, quietude.audio, quietude.center) | Autorité SEO fragmentée, confusion sur l'email transactionnel | Consolider sur `quietude.app` selon les données SEO |
| Copy de la fiche App Store pas dans la voix de marque | La surface Quietude au plus fort trafic ; expérience hors-marque pour les nouveaux arrivants | Réécrire dans la voix (Pilier 1) |
| La consolidation de domaine nécessite un plan de 301 + migration de l'expéditeur email | Risque de perte de trafic si mal géré | Planifier en semaines 1–2, exécuter en semaines 3–4 |
| Le repo `quietude-promo` n'a rien shippé depuis mars 2026 | Le site marketing est périmé | Confirmer s'il est en ligne ; réécrire ou remplacer |
| 29 % de churn mensuel App Store vs claim de 38 % de rétention à 12 mois | Décalage de définition de métrique qui embrouille l'équipe | Réconcilier avec Devon + les données Customer.io |
| Périmètre de la réflexion post-session de Mira inconnu | Bloque les tests d'onboarding Variante B et Variante C | Résoudre avec Devon |

### Snapshot de la grille d'audit (17 sections)

Scoré de 0 à 5 à partir des supports, en utilisant la grille embarquée dans `references/current-state-rubric.md`. Marqué « scoré à partir des supports » plutôt que « audit formel » — Alex peut contester tout score où il dispose de meilleures données.

| # | Section | Score | Note |
|---|---|---|---|
| 1 | Positionnement | **4** | Revendication de catégorie claire et originale. Le cadre bottom-up est la pièce la plus forte. Nécessite une articulation externe plus large. |
| 2 | Recherche client | **4** | Recherche profonde menée par le fondateur, une décennie de participants live. Pourrait être captée plus systématiquement. |
| 3 | Page d'accueil | **2** | `quietude-promo` n'a rien shippé depuis mars. Voix hors-marque par endroits. |
| 4 | Pages ventes / produit | **2** | La page masque existe sur Shopify mais n'est pas optimisée pour le SEO ni pour la narrative de vente. Pas de landing page app-produit dans la voix de marque. |
| 5 | Pages de conversion | **2** | `/partner` existe sur `quietude.app`. Aucune page `/science`, `/eye-mask`, `/ambassadors`, `/guides` en ligne. |
| 6 | Comparatif concurrents | **1** | Rien n'existe. Grosse opportunité SEO + ventes (s'approprier les SERP « Quietude vs Calm/Headspace/Brain.fm/Endel »). |
| 7 | Ressources / contenu | **1** | Sound Philosophy pas encore public. Étude de psychophysiologie peer-reviewed pas encore sur une page dédiée. Pas de blog. |
| 8 | Onboarding | **2** | Le gate des écouteurs tue la conversion. Projet « stop-and-fix » ce trimestre. |
| 9 | Lifecycle email | **1** | Les trois flows draftés, aucun en live. Ordre de ship établi. |
| 10 | Support de vente | **3** | Le deck de seed est fort (orienté investisseur). Support de vente B2B plus porté par le fondateur que par les assets. |
| 11 | Messaging | **5** | Alex + Sam ont écrit la voix de marque la plus distinctive de la catégorie bien-être. C'est un moat. |
| 12 | Pricing | **3** | 30 €/mois l'app, 45 € le masque, 7 500 € les enceintes, 50–200 K€ le B2B. N'a pas été pressure-testé pour le lift de conversion D2C. |
| 13 | CRO | **2** | Taux de conversion App Store traçable mais aucun historique d'A/B. Le gate des écouteurs est le test de retrait évident en premier. |
| 14 | GTM / lancements | **2** | App en beta throttlée. Les lancements majeurs (masque, Mira public) n'ont pas eu de GTM structuré. |
| 15 | Ads | **0** | Aucune couche paid. Reflète la stratégie organique actuelle — pas une faiblesse, mais le déblocage budget signifie que ça va bouger. |
| 16 | SEO | **1** | État actuel : 7 visites organiques/mois. Le plan existe ; l'exécution n'a pas encore démarré. |
| 17 | Internationalisation | **1** | Siège en Finlande + ICP global, mais copy EN-only et US-centrée. À reporter jusqu'au Q4+. |

**Total : 36 / 85 (42 %).** La forme compte plus que le score : haut en Positionnement + Messaging + Recherche client, bas en Pages de conversion + Lifecycle email + SEO + Ressources + Ads. C'est l'écart que ce plan referme.

---

## 4. Acquisition

> *« Comment les inconnus prennent-ils conscience de Quietude ? »*

### État actuel

100 % organique. Quatre canaux réels : le LinkedIn perso d'Alex, les événements Quietude live, le bouche-à-oreille organique, la découverte organique sur l'App Store. Plus le drag passif de PR de l'endorsement de l'influenceur longévité + l'étude clinique.

C'est une bonne nouvelle, pas une mauvaise. Chaque euro de chiffre d'affaires gagné à ce jour l'a été sans acquisition paid. La barre à dépasser n'est pas haute ; l'upside par-dessus une base organique est significatif.

### Le plan

**Canal 1 — SEO (investissement primaire des 90 jours).**
Le plan complet à 90 jours vit dans `seo/plan.md`. Résumé : consolider sur `quietude.app`, cibler trois clusters asymétriques (régulation du système nerveux KD 14–32, masque de sommeil lesté/occultant KD 6–30, WELL + B2B social-wellness-club KD 5–34), publier 4 piliers de contenu. Cible 90 jours : 500–1 500 visites organiques/mois, 80+ mots-clés rankés. Cible 12 mois : 10 000/mois, 1 000+ mots-clés.

**Canal 2 — App Store optimization (l'asset hors-site au plus fort levier).**
La fiche App Store est actuellement l'URL Quietude la plus visitée par l'algorithme d'Apple. Corriger la copy a plus de levier ce trimestre que corriger le site marketing. Réécrire dans la voix de marque. Ajouter le framing méditation-vs-régulation. Mener avec l'ancre clinique. Tester des variations de screenshots.

**Canal 3 — Le LinkedIn d'Alex (productiser le canal).**
Aujourd'hui c'est du posting fondateur ad-hoc. Le prochain move est structuré : une cadence de 2–3x/semaine, des catégories de posts qui mappent les piliers de contenu (système nerveux, science du son, parcours fondateur, preuve clinique, behind-the-scenes), des liens traçables via Dub, un funnel follower → abonné email → install app mesuré. C'est la voix d'Alex — le canal ne marche que si c'est lui qui écrit. fCMO + scheduling Typefully rendent la cadence soutenable.

**Canal 4 — Amplification PR.**
Le tailwind de l'influenceur longévité est réel mais sous-utilisé sur les surfaces owned. Ajouter une page `/notable-users` ou `/in-the-press`. Pitcher l'étude de psychophysiologie peer-reviewed à 5 médias (presse bien-être : Well+Good, MindBodyGreen ; tech-adjacent : Wired avec le hook influenceur longévité ; mainstream : Outside, Forbes Wellness). Réponses HARO/Help-A-B2B-Writer citant les données de Quietude. Moments de PR investisseur (pièces « Pourquoi j'ai investi dans Quietude » sur Substack des angels consumer-tech — pousser pour les obtenir avec des backlinks).

**Canal 5 — Instrumentation événement-vers-app.**
Les événements live sont l'exposition ICP la plus convertissante que Quietude possède (15 K+ participants, une décennie de confiance). Ils ne sont pas instrumentés. Ajouter : QR code par événement → install app + capture email, lifecycle post-événement (Customer.io Flow 7 ?), tracking du ROI événement. Objectif : transformer un événement d'un moment de conversion d'un soir en un funnel de 30 jours.

**Canal 6 — Wedge du masque (produit d'entrée consumer).**
5 K masques en stock. La boutique Shopify existe mais n'est pas optimisée. Améliorations : optimiser la page produit pour le SEO (cibler « masque de sommeil lesté », « masque de sommeil occultant », « masque de sommeil en soie »), ajouter des avis via Judge.me (décision de kickoff), politique de retour à 30 jours (attente du marché US, selon kickoff), construire le listicle (« Quietude vs Manta vs Nodpod vs Lumon »). Envisager un listing Amazon comme play de distribution v2.

**Canal 7 — Installs B2B de lieux (gardé lean selon le kickoff).**
Alex possède ça. Le marketing soutient avec : des études de cas après chaque install, la réécriture de la page `/partner` dans la voix (existe déjà sur quietude.app), du contenu Pilier 4 (« La feature son qui manque dans WELL »), des liens réciproques des lieux partenaires inscrits dans les contrats.

**Canal 8 — Couche paid (débloquée post-clôture-seed).**
En attente jusqu'à l'atterrissage du financement seed. Budget test initial : 5–10 K€/mois répartis entre Apple Search Ads (intention la plus forte pour l'App Store), Meta (Instagram + Facebook pour le masque), LinkedIn (acheteurs B2B de lieux). Ne pas déclencher tant que : (a) le fix de fond de l'onboarding n'est pas shippé, (b) le Flow 6 n'est pas en live, (c) au moins une landing page de Pilier n'est pas dans la voix. Le paid amplifie ce qui marche déjà — un paid prématuré amplifie ce qui est cassé.

### Moves d'acquisition à 90 jours

- Semaines 1–2 : décision de consolidation de domaine + plan de 301. Première passe de réécriture de la fiche App Store.
- Semaines 3–4 : 301 de domaine exécutées. Migration GSC. Hub du Pilier 1 SEO drafté.
- Semaines 5–8 : hub du Pilier 1 + 3 spokes publiés. Hub Pilier 2 (Masque) + listicle publiés. Cadence LinkedIn d'Alex opérationnalisée via Typefully. L'étude de psychophysiologie peer-reviewed atterrit sur une page `/science` dédiée.
- Semaines 9–12 : pierre angulaire du Pilier 4 (WELL/B2B) publiée. Sound Philosophy devient public sur `/research/sound-philosophy`. Premier push PR : pitcher l'étude + le hook influenceur longévité à 5 médias.

### Perspective acquisition à 12 mois

- Q1 (Mois 1–3) : fondations. Piliers SEO plantés. Réécriture App Store shippée. Cadence LinkedIn stable. Push PR lancé.
- Q2 (Mois 4–6, post-clôture-seed) : pilote d'acquisition paid à 5–10 K€/mois. SEO qui se cumule — Pilier 1 qui ranke. Premier cas de référence d'install B2B en live.
- Q3 (Mois 7–9) : le paid scale à 20–30 K€/mois si l'unit economics tient. Les quatre piliers produisent. App GA — nouveau moment GTM.
- Q4 (Mois 10–12) : canaux à effet de cumul en live. 50+ pièces de contenu pilier. Premier pilote du programme Quietude Guides créant du SEO local + de l'earned media.

### Skills + outils

- **Skills :** `seo-audit`, `ai-seo`, `programmatic-seo`, `schema`, `content-strategy`, `competitors`, `launch`, `ads`, `ad-creative`, `social`, `typefully`, `analytics`, `copywriting`, `marketing-website-design`, `free-tools`
- **MCPs / APIs :** Ahrefs API, DataForSEO API, Typefully MCP (scheduling LinkedIn), GA4 MCP (une fois câblé), GitHub MCP (travail sur le repo `quietude-promo`), Notion (knowledge directory), Stripe MCP (calcul LTV / CAC-paid), `agent-browser` (rédaction + test LinkedIn), `defuddle` (recherche)

---

## 5. Activation

> *« Une fois que quelqu'un essaie Quietude, vit-il une expérience qui convertit ? »*

### État actuel

Jour 1 → payant : **1,34 %**. Jour 7 → payant : **3,73 %**. Jour 35 → payant : **5,46 %**. *La forme du funnel est le signal.* Le lift de ~4× sur 35 jours signifie que le produit convertit dès qu'on lui donne du temps et du contact — deux choses que l'onboarding actuel sape et que la couche lifecycle ne fournit pas encore.

Précautions : l'app est en beta throttlée. Les métriques sont bruitées. Ne pas optimiser contre des absolus ; optimiser contre la *forme* du funnel et la *comparaison de cohortes*.

### Le plan

**Move 1 — Tuer le hard-gate des écouteurs (fix de fond, cette semaine).**
Chute de conversion confirmée après le ship du gate. Le fix n'est pas une meilleure copy sur le gate — c'est de retirer le gate. Remplacer par une détection passive des écouteurs + un nudge doux en une ligne. Changement sans regret. Raisonnement complet dans `onboarding-recommendation.md`.

**Move 2 — Lancer le test d'onboarding à trois variantes.**
Trois variantes, chacune une expression pure d'une croyance sur ce qui pilote l'activation dans cet ICP :
- **Variante 1 — Confiance d'abord.** Promesse forte + ancre clinique + mur de témoignages + mécanisme en 1 ligne. Teste si l'ICP saturé a besoin de framing avant de s'investir.
- **Variante 2 — Vu d'abord.** Diagnostic multi-étapes → résumé « on vous voit » généré par IA → session personnalisée. Teste si être nommé avec précision est l'événement de conversion.
- **Variante 3 — Ressenti d'abord.** L'audio démarre à l'ouverture de l'app. ~15 mots à l'écran. La session EST l'onboarding. Teste si le produit peut le porter à froid.

Séquence de test (séquentielle, ~7 semaines jusqu'à un vainqueur) : baseline de fond → V3 vs baseline → vainqueur vs V1 → vainqueur vs V2. Système complet dans `onboarding-recommendation.md`.

**Move 3 — Réécriture de la fiche App Store.**
L'asset hors-site au plus fort levier. Réécrire dans la voix de marque. Mener avec méditation-vs-régulation. Variations de screenshots à tester. C'est aussi un move d'Acquisition (découverte organique) mais il vit ici parce que c'est le seuil vers l'essai.

**Move 4 — Customer.io Flow 2 (en attente jusqu'à UI stable).**
La séquence d'onboarding de 8 emails / 14 jours est draftée et on-brand. On retient le ship parce que les emails référencent des écrans in-app qui vont changer pendant la refonte de l'onboarding. Une fois qu'une variante d'onboarding gagnante est shippée, le Flow 2 reçoit un rafraîchissement de copy contre l'UI finale et passe en live.

**Move 5 — Revue paywall + pricing (transversal vers Revenue).**
Quelle est la structure d'essai actuelle ? Durée, trigger du paywall, intro pricing ? Quand la forme du funnel est « lift sur 35 jours », allonger l'essai peut mieux convertir qu'un gating agressif plus tôt. À auditer en Q1.

### Moves d'activation à 90 jours

- Semaine 1 : gate des écouteurs retiré. Baseline établie.
- Semaines 2–3 : Variante 3 (Ressenti d'abord) prototypée, instrumentée, shippée à une cohorte de test.
- Semaines 4–5 : lecture Variante 3 vs baseline. Décider ship/itérer. Démarrer le build de la Variante 1.
- Semaines 6–7 : Variante 1 (Confiance d'abord) en live.
- Semaines 8–9 : lecture V1 vs vainqueur. Démarrer le build de la Variante 2.
- Semaines 10–11 : Variante 2 (Vu d'abord) en live.
- Semaine 12 : lecture finale. Variante gagnante programmée pour ship permanent. Flow 2 débloqué.

### Perspective activation à 12 mois

- Q1 : variante gagnante identifiée et shippée.
- Q2 : le Flow 2 ship. Les A/B tests de paywall démarrent.
- Q3 : lancement GA — onboarding re-validé à plus fort trafic. La segmentation de cohortes par source d'acquisition (Shopify/masque vs direct vs ambassadeur vs paid) commence à piloter des forks de variantes.
- Q4 : l'onboarding n'est plus le goulot d'étranglement. Le focus se déplace vers la transition Activation → Rétention (sessions 2–7).

### Skills + outils

- **Skills :** `onboarding`, `signup`, `cro`, `cro`, `paywalls`, `popups`, `copywriting`, `copy-editing`, `copycraft`, `marketing-website-design`, `ab-testing`, `marketing-psychology`
- **MCPs / APIs :** App Store Connect (manuel + `dev-browser` pour l'automatisation des screenshots), GitHub MCP (repo app `quietude-app` pour le code d'onboarding), Figma / Pencil MCP (pour le design des écrans d'onboarding), Customer.io MCP (pour toute coordination in-app/email), GA4 MCP (events d'activation)

---

## 6. Rétention

> *« Une fois que quelqu'un convertit, reste-t-il — et s'approfondit-il ? »*

### État actuel

**Métrique phare (selon le deck de seed) : 38 % de rétention à 12 mois** — quasi le double de la moyenne de catégorie (~20 %). C'est le plus fort signal de rétention unique du deck et l'un des claims les plus sous-marketés que Quietude possède.

**Snapshot App Store, 2026-05-16 :** 145 payants, 42 churnés (~29 % de churn mensuel). Décalage de définition avec le claim des 38 % — à réconcilier. Possiblement : 38 % est de la rétention de cohorte annuelle (les gens qui ont payé au mois 1 et paient encore au mois 12), 29 % est du churn mensuel brut (les gens qui ont payé ce mois-ci et n'ont pas payé le suivant). Les deux peuvent être vrais. Il faut clarifier quelle métrique est reportée en externe et laquelle est le vrai signal de santé produit.

### Le plan

**Move 1 — Shipper le Flow 6 en premier (post-achat masque).**
Selon la décision de kickoff et le doc onboarding-recommendation : c'est le flow prêt à shipper. Ancré sur le hardware, ne référence pas d'écrans in-app, peut shipper aujourd'hui. Câble le chemin hardware → activation app (les acheteurs de masque devraient obtenir un essai Premium gratuit de 6 mois — formaliser ça comme partie du flow).

**Move 2 — Shipper le Flow 4 en second (réengagement utilisateur inactif).**
Cinq emails sur 38 jours. Le langage est universel — ne dépend pas de l'état de l'UI de l'app. Shipper après que le Flow 6 soit en live.

**Move 3 — Garder le Flow 2 en attente (onboarding).**
Huit emails sur 14 jours. En attente jusqu'à la stabilisation de l'UI de l'app post-refonte-onboarding. Ne pas shipper de copy qui devra être réécrite dans 8 semaines.

**Move 4 — Subscription center Customer.io avec topics opt-in.**
Selon la décision de kickoff. Topics : événements, mises à jour de l'app, somatique & système nerveux, promos masque. Les utilisateurs s'auto-segmentent. Améliore la délivrabilité (taux de plainte plus bas) et donne au lifecycle une surface de segmentation plus riche.

**Move 5 — Réflexion post-session de Mira (une fois cadrée).**
Le move de rétention le plus puissant à moyen terme. Après une session, Mira demande *« Qu'avez-vous remarqué ? »* Chips préréglés optionnels + texte libre. Deux gains : (a) donne à Mira des priors pour la personnalisation à la session 2+, (b) les réponses de réflexion deviennent une mine d'or de contenu + segmentation pour l'équipe. Question de cadrage pour Devon — est-ce que Mira supporte ça actuellement, ou c'est du nouveau build ?

**Move 6 — Flow d'activation hardware → app.**
Le chemin acheteur-de-masque-devient-abonné-Premium est suggéré dans le deck de seed (CAC blended via le hardware) mais n'est pas visible dans le dashboard App Store. Auditer le flow existant : est-ce qu'un achat masque sur Shopify délivre réellement un code Premium gratuit ? Comment est-il redeemé ? Quel est le taux de conversion ? C'est fondamental pour la thèse du « wedge B2C ».

**Move 7 — Réconcilier la métrique de rétention.**
Quelle est la vraie définition de « 38 % de rétention à 12 mois » ? Cohorte ? Type de plan (mensuel vs annuel) ? Survivre à ça même si la réponse est inconfortable — l'équipe et les investisseurs doivent parler de la même métrique.

**Move 8 — Plan annuel par défaut (transversal vers Revenue).**
Pattern de l'industrie : mettre l'annuel par défaut réduit l'anxiété de churn et améliore la LTV. À tester en Q2.

### Moves de rétention à 90 jours

- Semaines 1–2 : le Flow 6 (post-achat masque) ship. Traiter les fixes de la revue de kickoff (saut de ligne du lien d'étude, footer CAN-SPAM, signature avec bulle-visage fondateur, avis Judge.me).
- Semaines 3–4 : le Flow 4 (réengagement utilisateur inactif) ship.
- Semaines 5–6 : subscription center Customer.io construit et en live.
- Semaines 7–8 : flow d'activation hardware → app audité et documenté. Colmater les fuites.
- Semaines 9–10 : réconciliation de la métrique de rétention (avec Devon).
- Semaines 11–12 : campagne de win-back pour la cohorte churnée — tester de la copy de réactivation.

### Perspective rétention à 12 mois

- Q1 : Flows 6 + 4 qui tournent. Subscription center en live.
- Q2 : le Flow 2 ship (post-refonte-onboarding). Réflexion post-session de Mira en production. Plan annuel par défaut testé.
- Q3 : lancement GA — métriques de rétention re-baselinées à plus fort volume. Flows lifecycle par cohorte (masque vs install app direct).
- Q4 : lifecycle complet à effet de cumul. La rétention n'est plus une préoccupation top-trois — le focus se déplace vers Referral et Revenue.

### Skills + outils

- **Skills :** `emails`, `churn-prevention`, `copywriting`, `copy-editing`, `paywalls`, `ab-testing`
- **MCPs / APIs :** **Customer.io MCP** (validé au kickoff — l'équipe non technique peut shipper des flows), Shopify (acheteurs de masque comme source d'events), Stripe MCP (état d'abonnement, pulls de cohortes de churn), GA4 MCP (events de session, courbes de rétention)

---

## 7. Referral

> *« Les utilisateurs retenus amènent-ils plus d'utilisateurs — et à quel coût ? »*

### État actuel

~5 ambassadeurs inbound en attente (selon le kickoff). Dub.co mis en place. Pas encore de programme formel. Le bouche-à-oreille se produit naturellement selon le breakdown UA d'Alex.

C'est l'un des plus forts indicateurs avancés du business : 5 personnes non affiliées ont levé la main pour demander à amener Quietude à leur réseau *avant qu'aucun programme n'existe*. Ce signal n'apparaît pas dans les apps à product-market fit plus faible.

### Le plan

**Move 1 — Lancer le programme d'ambassadeurs avec les 5 inbounds.**
Tier 1 du programme. Landing pages par ambassadeur (ex. `quietude.app/with/sarah`). Dub.co track l'attribution. Structure de commission à déterminer (selon le kickoff, €/abonné ou rev-share à définir). Soft-launch avec les 5 — traiter comme cohorte pilote, recueillir du feedback, affiner avant d'ouvrir les candidatures.

**Move 2 — Construire le moment share-after-shift.**
La réflexion post-session de Mira (voir Rétention) est le moment naturel pour faire surface un prompt de partage. Après qu'un utilisateur rapporte un shift ressenti, proposer : *« Envie de partager Quietude avec quelqu'un qui en a besoin ? »* En une ligne, jamais insistant. Mécanisme de bouche-à-oreille le plus puissant : flow gift-a-month où le destinataire obtient une intro réduite ou gratuite.

**Move 3 — Amplification fondateur (Alex + Sam comme ambassadeurs-zéro).**
Alex mentionnant la mission fCMO dans les pitchs de levée (permission accordée). Mentions réciproques dans le contenu côté fCMO. Le réseau clinique de Sam → pool d'ambassadeurs praticiens.

**Move 4 — Pilote de certification Quietude Guides (long terme, Q3+).**
Le programme Guides est l'effet de cumul referral de Phase 2 (selon le deck de seed). 500–1 000 Guides à travers 50+ villes d'ici A3–5. Premier pilote de certif : 3–5 hôtes qui animent des sessions live, obtiennent un rev-share + co-marketing. Construit du SEO local + earned media + un flywheel ambassadeur-d'ambassadeurs. En attente jusqu'à ce que paid + lifecycle tournent — Guides est un build sur plusieurs trimestres.

**Move 5 — Flow de cadeau de masque.**
Le referral hardware est rare et puissant. *« Envoyez un masque Quietude à un ami. Il reçoit le masque + 3 mois de Premium gratuits. Vous obtenez un crédit pour votre prochaine commande. »* Les fenêtres de pic fêtes/cadeaux sont le test.

### Moves de referral à 90 jours

- Semaines 1–4 : programme d'ambassadeurs cadré, structure de commission décidée, template de landing page par ambassadeur construit, 5 inbounds onboardés.
- Semaines 5–8 : premières ventes pilotées par ambassadeurs trackées via Dub. Attribution et flow de paiement validés.
- Semaines 9–12 : ouvrir les candidatures pour les 10–15 prochains ambassadeurs. Démarrer le cadrage de Quietude Guides.

### Perspective referral à 12 mois

- Q1 : programme d'ambassadeurs en live avec 5–10 actifs.
- Q2 : 15–25 ambassadeurs actifs. Moment share-after-shift en production (post-réflexion Mira).
- Q3 : pilote de certif Guides lancé (3–5 hôtes). Flow de cadeau de masque en live pour le pic des fêtes.
- Q4 : 50+ ambassadeurs + 5–10 Guides. Le referral pilote 15–25 % des nouveaux abonnés D2C.

### Skills + outils

- **Skills :** `referrals`, `social`, `copywriting`, `marketing-website-design` (landing pages par ambassadeur)
- **MCPs / APIs :** Dub.co (attribution — déjà dans la stack), Stripe MCP (comptabilité des commissions + paiements), GitHub MCP (déploiement de landing pages dans `quietude-promo` ou nouveau repo `quietude-ambassadors`), Customer.io MCP (lifecycle ambassadeur : onboarding, digest de performance mensuel, notification de paiement)

---

## 8. Revenue

> *« Que facture-t-on, qui paie, et comment ça se cumule ? »*

### État actuel

| Produit | Prix | Signal de volume |
|---|---|---|
| App Quietude + Mira | ~30 €/mois | 145 abonnés payants (snapshot App Store 2026-05-16) |
| Masque Quietude | ~45 € | 5 K en stock, ventes pilotées par la PR de l'influenceur longévité |
| Quietude Audio (enceintes) | ~7 500 € | Niche, porté par le fondateur |
| Quietude Spaces (install B2B) | 50–200 K€ | Flagship Aurora en cours (~250 K€), pipeline de 4 lieux |
| Quietude Experiences (événements) | Variable | 15 K+ participants historiques |
| Quietude Guides | Rev share | Pas encore opérationnel |

**Chiffre d'affaires à ce jour : ~500 K€ sur ~250 K€ levés.** Capital-efficient. Hardware + B2B + abonnements app contribuent tous.

**MRR (snapshot App Store) : 592 €.** Throttlé par la beta, pas en régime permanent. Le ~4 €/abonné/mois implicite face à un prix catalogue de 30 €/mois suggère une forte adoption du plan annuel (qui compresse le revenu mensuel mais améliore la LTV) ou un pricing promotionnel significatif — à réconcilier avec Alex.

### Le plan

**Move 1 — Audit de pricing.**
Qu'est-ce qui est réellement facturé aujourd'hui ? Prix catalogue, mix de plans courant, intro pricing, offres de récupération de churn ? Le calcul implicite à 4 €/abonné/mois ne raconte pas une histoire propre — il faut la vérité terrain avant de recommander des changements.

**Move 2 — Plan annuel par défaut (test).**
Pattern de l'industrie, croisé avec la Rétention. Tester en Q2.

**Move 3 — Bundling hardware → app formalisé.**
Selon le framing du business model événementiel-partenaires dans le deck de seed : le CAC blended via hardware → abonnement app est le play. Aujourd'hui, un acheteur de masque obtient... quoi exactement ? Du Premium gratuit ? Un code d'essai ? Auditer + formaliser. Le masque est le wedge ; l'app est la LTV.

**Move 4 — Optimisation de la boutique Shopify du masque.**
La page actuelle sous-performe par rapport à son potentiel. Ajouter : ciblage SEO (« masque de sommeil lesté », « masque de sommeil occultant »), avis Judge.me (décision de kickoff), politique de retour à 30 jours (décision de kickoff), flow d'upsell vers l'app Premium.

**Move 5 — Envisager un listing Amazon pour le masque.**
Amazon prend de la marge mais c'est son propre moteur de découverte. Tester comme distribution v2 si le volume Shopify valide.

**Move 6 — Études de cas d'installs B2B + support de vente.**
Alex possède les ventes B2B mais le marketing soutient avec : des études de cas post-install (Aurora comme flagship), la réécriture de la page `/partner` dans la voix, du contenu SEO Pilier 4. Chaque install B2B est un ~430 K€/an récurrent + un multiplicateur de cas de référence.

**Move 7 — Licensing de données (long terme, à flagger pour la stack ops).**
Selon le pool de valeur A10–15 du deck de seed : 100–160 M€/an. Pas du revenu immédiat. A sa place dans l'agenda stratégique à 24 mois. Flaggé ici pour ne pas le perdre de vue.

### Moves de revenue à 90 jours

- Semaines 1–2 : audit de pricing. Réconcilier le MRR implicite vs catalogue.
- Semaines 3–4 : flow d'activation hardware → app audité (aussi Move 6 de Rétention).
- Semaines 5–8 : réécriture de la page Shopify du masque + optimisation SEO + Judge.me + politique de retour. Étude de cas Aurora échafaudée pour le post-install.
- Semaines 9–12 : test du plan annuel par défaut cadré.

### Perspective revenue à 12 mois

- Q1 : audit de pricing clôturé. Activation hardware → app formalisée.
- Q2 : test du plan annuel par défaut en live. Page Shopify du masque produisant un lift mesurable.
- Q3 : études de cas d'installs B2B (1–2) publiées. Lancement GA + considération d'un nouveau tier de pricing (ex. un plan supérieur orienté Mira ?).
- Q4 : pricing optimisé via les résultats de test. CAC blended hardware → app tracké et reporté. Premiers chiffres sur la thèse du licensing de données (encore très tôt).

### Skills + outils

- **Skills :** `pricing`, `paywalls`, `sales-enablement`, `revops`, `ab-testing`, `copywriting`
- **MCPs / APIs :** Stripe MCP (tests de pricing, analytics d'abonnement, cohorte de churn, calcul de CAC blended), Customer.io MCP (lifecycle lié au paywall), Shopify (transactions masque), GA4 MCP (events de revenue), Notion (knowledge directory commercial)

---

## 9. Roadmap 90 jours

Couche d'exécution tactique. Chaque item est taggé AARRR pour que la priorité soit visible.

### Semaines 1–2 — Débloquer

| Move | Stage | Owner |
|---|---|---|
| Tuer le hard-gate des écouteurs | Activation | Casey + Devon |
| Décision de consolidation de domaine documentée | Acquisition | Casey + Alex |
| Plan de 301 drafté (page par page) | Acquisition | Casey |
| Réécriture de la fiche App Store — première passe | Activation + Acquisition | Casey + Alex + Sam (revue de voix) |
| Flow 6 (post-achat masque) ship | Rétention | Casey + Customer.io MCP |
| Doc de cadrage du programme d'ambassadeurs | Referral | Casey |
| Audit de pricing lancé | Revenue | Casey + Alex |

### Semaines 3–4 — Fondations

| Move | Stage | Owner |
|---|---|---|
| 301 de consolidation de domaine exécutées | Acquisition | Devon + Casey |
| GSC + GA4 montés sur `quietude.app` | Acquisition | Casey |
| Hub du Pilier 1 SEO drafté (Régulation du système nerveux) | Acquisition | Casey |
| Hub `/science` construit avec l'étude de psychophysiologie peer-reviewed | Acquisition + marque | Casey + Sam |
| Variante 3 (Ressenti d'abord) onboarding prototypée + testée | Activation | Casey + Devon |
| Flow 4 (utilisateur inactif) ship | Rétention | Casey |
| Programme d'ambassadeurs : 5 inbounds onboardés | Referral | Casey |
| Flow d'activation hardware → app audité | Rétention + Revenue | Casey + Devon |
| Réécriture de la fiche App Store — final + ship | Activation + Acquisition | Alex + Sam + Casey |

### Semaines 5–8 — Vélocité

| Move | Stage | Owner |
|---|---|---|
| Hub du Pilier 1 + 3 spokes publiés | Acquisition | Casey |
| Hub du Pilier 2 (Masque) + listicle publiés | Acquisition | Casey |
| Cadence LinkedIn d'Alex opérationnalisée (Typefully) | Acquisition | Alex + Casey |
| Premier push PR : étude + hook influenceur longévité à 5 médias | Acquisition | Casey + Alex |
| Lecture Variante 3 ; ship ou itérer | Activation | Casey |
| Variante 1 (Confiance d'abord) prototypée + testée | Activation | Casey + Devon |
| Subscription center Customer.io construit | Rétention | Casey |
| Réécriture de la boutique Shopify du masque (SEO + avis + retour) | Acquisition + Revenue | Casey + Alex |
| Première attribution ambassadeur vérifiée via Dub | Referral | Casey |

### Semaines 9–12 — Cumuler

| Move | Stage | Owner |
|---|---|---|
| Pierre angulaire du Pilier 4 (WELL/B2B) publiée | Acquisition | Casey |
| 3 spokes de Pilier 1 supplémentaires publiés | Acquisition | Casey |
| Sound Philosophy publié sur `/research/sound-philosophy` | Acquisition + marque | Alex + Casey |
| Lecture Variante 1 ; démarrer le build Variante 2 (Vu d'abord) (dépendant de Mira) | Activation | Casey + Devon |
| Campagne de win-back pour la cohorte churnée | Rétention | Casey |
| Test du plan annuel par défaut cadré | Revenue | Casey + Alex |
| Ouvrir les candidatures ambassadeurs pour les 10–15 prochains | Referral | Casey |
| Revue 90 jours + recalibrage du plan Q2 | Transversal | Casey + Alex |

---

## 10. Perspective à 12 mois

Jalons trimestriels avec les déblocages de capacité par stade de financement nommés explicitement.

### Q1 — Mois 1–3 (juin–août 2026)

**État de financement :** pré-clôture-seed. Budget paid = 0 €. fCMO + porté par les fondateurs + coûts d'outils uniquement.

**Focus :** fondations. Colmater les fuites. Planter le terrain SEO. Faire tourner le lifecycle.

**Résultats fin Q1 :**
- Gate des écouteurs disparu ; vainqueur d'onboarding identifié
- Les quatre piliers SEO ensemencés (hub + premiers spokes)
- Lifecycle Flows 4 + 6 en live
- Fiche App Store dans la voix de marque
- 5 ambassadeurs actifs
- Audit de pricing clôturé
- Domaine consolidé

**Cibles KPI :** lift d'onboarding Jour 1 → payant de 25–50 %. Trafic organique 500–1 500/mois. Taux de conversion App Store +20 %.

### Q2 — Mois 4–6 (sept–nov 2026)

**État de financement :** clôture seed (cible ~Q3 2026). Premier déblocage de budget paid : test à 5–10 K€/mois.

**Focus :** valider le paid. Scaler l'onboarding gagnant. Ajouter le Flow 2.

**Résultats fin Q2 :**
- Acquisition paid qui tourne sur Apple Search Ads + Meta
- Onboarding gagnant shippé en permanence
- Flow 2 (emails d'onboarding) shippé
- Réflexion post-session de Mira en production
- 15–25 ambassadeurs actifs
- Premier cas de référence d'install B2B (Aurora) publié
- Plan annuel par défaut testé

**Cibles KPI :** CAC paid < 50 € blended. Trafic organique 1 500–3 500/mois. Courbes de rétention visiblement en amélioration.

### Q3 — Mois 7–9 (déc 2026–fév 2027)

**État de financement :** déploiement du seed. Le paid scale à 20–50 K€/mois si l'unit economics tient. Premier recrutement marketing (lifecycle + content manager).

**Focus :** scaler + diversifier. App GA. Cas de référence B2B qui se cumulent.

**Résultats fin Q3 :**
- App GA lancée avec un nouveau moment GTM (PR + refresh de créa pub + cycle de contenu science de l'audio spatial Pilier 3)
- Premier pilote de certif Quietude Guides (3–5 hôtes)
- Les quatre piliers produisant du contenu hebdomadaire
- Flow de cadeau de masque en live pour le pic des fêtes
- Nouveau recrutement marketing onboardé

**Cibles KPI :** CAC blended paid + organic en stabilisation. Conversion App GA +50 % vs la baseline beta. Le pilote Guides valide le modèle rev-share + co-marketing.

### Q4 — Mois 10–12 (mars–mai 2027)

**État de financement :** pré–Series A. Le scaling paid continue. Pitch de Series A en mouvement.

**Focus :** cumuler. Se positionner pour la Series A.

**Résultats fin Q4 :**
- Canaux à effet de cumul (organic + ambassadeur + Guides + lifecycle) produisant 50 %+ des nouveaux abonnés
- 50+ ambassadeurs, 5–10 Guides
- 4 piliers SEO + 30+ pièces de contenu en live
- Paid scalant à 50–150 K€/mois si validé
- Narrative de Series A : preuve clinique + lift d'activation + cumul lifecycle + pipeline de cas de référence B2B

**Cibles KPI :** trajectoire claire du run-rate d'ARR D2C. LTV/CAC blended > 3. Narrative fondateur + données + cas de référence prêts pour la Series A.

---

## 11. Stack d'opérations marketing

C'est ce qui rend le plan exécutable à la taille d'équipe de Quietude. Une équipe fondatrice de 4 personnes + fCMO + outillage agentique peut shipper l'output d'une org marketing traditionnelle de 15–20 personnes — parce que la bibliothèque de skills marketing et les intégrations MCP font l'orchestration.

### La thèse

Chaque move du breakdown AARRR ci-dessus mappe vers (a) un ou plusieurs skills marketing qui opérationnalisent le travail, et (b) une ou plusieurs intégrations MCP/API qui lui permettent de s'exécuter sans une tête dédiée par canal.

Le job du fCMO est de :
1. Définir la stratégie et le séquençage (ce document)
2. Lancer les skills contre le bon contexte au bon moment
3. Maintenir le contexte partagé (`quietude-context`) et l'outillage pour qu'Alex + Sam + les futurs recrutements puissent se brancher
4. Déléguer le travail opérationnel à des humains (ou de futurs recrutements) seulement là où le coût de l'exécution agentique > l'exécution humaine

### Skills mappés aux stages AARRR

| Stage | Skills primaires | Skills de support |
|---|---|---|
| **Acquisition** | `seo-audit`, `ai-seo`, `programmatic-seo`, `schema`, `content-strategy`, `competitors`, `ads`, `ad-creative`, `social`, `typefully` | `launch`, `free-tools`, `analytics`, `cold-email`, `copywriting`, `marketing-website-design` |
| **Activation** | `onboarding`, `signup`, `paywalls`, `cro`, `copywriting`, `copy-editing`, `copycraft` | `marketing-website-design`, `ab-testing`, `marketing-psychology`, `cro`, `popups` |
| **Rétention** | `emails`, `churn-prevention` | `copywriting`, `copy-editing`, `ab-testing`, `paywalls` |
| **Referral** | `referrals`, `social` | `copywriting`, `marketing-website-design`, `emails` |
| **Revenue** | `pricing`, `paywalls`, `sales-enablement`, `revops` | `ab-testing`, `copywriting` |
| **Transversal** (marque, intelligence) | `product-marketing`, `customer-research`, `marketing-psychology` | `marketing-ideas`, `diagram-maker` |

### MCPs / APIs mappés aux stages

| Stage | Connexions existantes chez Quietude | Couche d'outillage (stack fCMO de Casey) |
|---|---|---|
| **Acquisition** | App Store Connect (manuel), Shopify, GA4 (en cours), Notion | Ahrefs API, DataForSEO API, Typefully MCP, GitHub MCP (`quietude-promo`), `agent-browser`, `defuddle` |
| **Activation** | App Store Connect, Customer.io, Shopify | App Store Connect (via `dev-browser` pour l'automatisation des screenshots), Figma / Pencil MCP, GitHub MCP (repo app `quietude-app`), Stripe MCP |
| **Rétention** | **Customer.io (avec Claude MCP — validé au kickoff)**, Stripe, Shopify | Customer.io MCP, Stripe MCP, GA4 MCP |
| **Referral** | Dub.co, Stripe | Dub.co, Stripe MCP, GitHub MCP (landing pages par ambassadeur), Customer.io MCP |
| **Revenue** | Stripe, Shopify, Customer.io | Stripe MCP, Shopify, GA4 MCP, Notion |
| **Transversal** | Notion, GitHub (`quietude-context`) | Notion, GitHub MCP, `defuddle`, `obsidian-cli` (pour les notes de travail de Casey) |

### Le déblocage Customer.io MCP (exemple concret)

Selon le call de kickoff : *« Construit en live pendant le call — flow de panier abandonné drafté avec le Claude MCP de Customer.io. Validé que l'équipe non technique peut utiliser le pattern de skill en autonomie. »*

C'est la preuve opérationnelle que la stack marche. Alex, qui n'est pas développeur, a drafté un flow lifecycle fonctionnel avec Claude + Customer.io MCP en temps réel pendant un call de kickoff. Le même pattern s'applique à : ship du Flow 4 (réengagement utilisateur inactif), build du subscription center, campagne de win-back, flow de cadeau de masque, lifecycle ambassadeur. Le rôle du fCMO devient orchestration + QA de la voix de marque, pas le maniement manuel de chaque email.

### Déblocages de capacité par stade de financement

| Stade | Effectif | Outillage | Canaux en live |
|---|---|---|---|
| **Pré-clôture-seed (maintenant)** | fCMO + équipe fondatrice | Tout l'outillage actuel + la bibliothèque de skills marketing de Casey + la couche MCP | Organic uniquement (SEO, contenu, App Store, LinkedIn, événements, bouche-à-oreille, ambassadeur) |
| **Clôture seed (~Q3 2026)** | + premier recrutement marketing (lifecycle/content) d'ici fin Q3 | + comptes ads paid (Apple Search Ads, Meta, LinkedIn) | + pilote d'acquisition paid 5–10 K€/mois |
| **Déploiement seed (Q3–Q4 2026)** | + designer (potentiellement fractional) | + expansion analytics (Mixpanel ou Amplitude si besoin) | + scaling paid 20–50 K€/mois, + pilote de certif Guides |
| **Series A (2027)** | + lead performance marketing + content lead | + dépense d'outillage dédiée (~2–5 K€/mois software) | + scaling paid 50–150 K€/mois, + international, + expansion verticale B2B |

La bibliothèque de skills marketing scale ces stades. Chaque canal ajouté ne nécessite pas une augmentation d'effectif en 1:1 parce que chaque skill encode le workflow.

---

## 12. Banque d'idées tactiques — croisement des 139 idées

Le skill `marketing-ideas` catalogue 139 tactiques marketing éprouvées. Les Sections 4–8 (AARRR) prescrivent ce qu'on *fait*. Cette section mappe l'univers complet de ce qui est *possible* — chaque idée croisée avec le stage AARRR qu'elle sert principalement, avec l'applicabilité Quietude et le timing.

C'est le menu exhaustif. Le plan ci-dessus est le chemin curaté. Quand on passe au Q2 / Q3 / Series A et qu'on débloque de la capacité nouvelle, c'est l'inventaire dans lequel on pioche.

**Légende des statuts :**

- **Maintenant (Q1)** — déjà dans le plan 90 jours OU peut tourner en parallèle sans capacité nouvelle
- **Q2** — post-fix-de-fond, post-fondations ; ajouts de second trimestre
- **Q3+** — post-clôture-seed, post-GA ; moves d'expansion
- **Q4+** — jeu long / moves à fort investissement
- **Skip / hors-marque** — incompatible avec la voix de marque, le business model ou la catégorie produit de Quietude

### 12.1 Idées d'acquisition (88 mappées)

**Maintenant (Q1) :**

| # | Idée | Note Quietude |
|---|---|---|
| 1 | Easy Keyword Ranking | Le cluster Tier-1 du plan SEO (système nerveux, masque de sommeil, B2B) cible ça directement |
| 2 | SEO Audit | Lancer `/seo-audit quietude.app` trimestriellement ; publier les findings en contenu |
| 5 | Content Repurposing | Sound Philosophy → essais → posts LinkedIn → newsletter → boucle podcast |
| 6 | Proprietary Data Content | Étude de psychophysiologie peer-reviewed maintenant ; dataset HRV / sommeil Quietude anonymisé plus tard |
| 7 | Internal Linking | Intégré dans la structure pilier/spoke du plan SEO |
| 10 | Parasite SEO | Le LinkedIn d'Alex fait déjà ça ; envisager un miroir sur Substack |
| 12 | Marketing Jiu-Jitsu | Méditation-vs-Régulation EST ça — retourner l'assomption « la méditation marche » contre elle-même |
| 36 | Quora Marketing | Répondre à « pourquoi la méditation ne marche pas pour moi » + questions HRV + somatiques |
| 37 | Reddit Keyword Research | Miner r/somatic, r/CPTSD, r/HSP, r/ADHD pour le langage ICP (alimente Customer Language #139) |
| 39 | LinkedIn Audience | Le canal d'Alex productisé — top-of-funnel D2C primaire aujourd'hui |
| 59 | Article Quotes | HARO / Help-A-B2B-Writer pour Alex + Sam — wins presse faciles |
| 70 | Conference Speaking | Alex : WELL Conference, événements de design biophilique, Mindful Leadership Summit |
| 74 | Press Coverage | Pitcher l'étude peer-reviewed + le hook influenceur longévité à 5 médias en Q1 |
| 109 | Public Demos | Les événements Quietude live SONT ça ; instrumenter la conversion en-personne → app |
| 114 | Moneyball Marketing | Déjà pratiqué — mots-clés SEO asymétriques, canaux sous-valorisés |
| 133 | Investor Marketing | La levée d'Alex — exploiter le backchannel des angels pour PR + intros |

**Q2 :**

| # | Idée | Note Quietude |
|---|---|---|
| 3 | Glossary Marketing | Glossaire son + système nerveux — « qu'est-ce que le polyvagal », « qu'est-ce que la HRV », « qu'est-ce que l'écoute somatique » |
| 8 | Content Refreshing | Revisiter le Pilier 1 trimestriellement avec de nouvelles données et mises à jour de search-intent |
| 11 | Competitor Comparison Pages | Quietude vs Calm / Headspace / Brain.fm / Endel / Wavepaths — SERP à forte intention |
| 13 | Competitive Ad Research | SpyFu + Facebook Ad Library avant de lancer le paid |
| 17 | Quiz Marketing | « Quel est votre profil de système nerveux ? » — génère une graine de personnalisation + capture de lead |
| 25 | Facebook Ads | Créa masque + contenu somatique + retargeting depuis les participants d'événements |
| 26 | Instagram Ads | Produit visuel + ads natives Reels (le masque surtout) |
| 28 | LinkedIn Ads | Acheteurs B2B de lieux + ICP investisseur-adjacent |
| 31 | Google Ads | Apple Search Ads d'abord (intention App Store) ; Google pour le masque + B2B |
| 38 | Reddit Marketing | Participation authentique dans r/somatic, r/HSP, r/ADHD une fois la base de contenu existante |
| 40 | Instagram Audience | Créateurs masque + somatique ; natif Reels |
| 44 | Comment Marketing | Commentaires réfléchis sur Huberman / le business événementiel-partenaires / Tim Ferriss / créateurs bien-être |
| 49 | Monthly Newsletters | Soit brandée Quietude soit synchronisée avec la newsletter Substack de Sam |
| 54 | Affiliate Discovery via Backlinks | Trouver qui linke vers Calm/Headspace/Brain.fm — les pitcher sur le programme d'affiliation Quietude |
| 58 | Newsletter Swaps | Le business événementiel-partenaires, Substacks de fondateurs bien-être, réseau d'investisseurs d'Alex |
| 64 | Community Sponsorship | Newsletters somatiques, Substacks bien-être, communautés de fondateurs |
| 65 | Live Webinars | Alex + Sam animant « Le son + le système nerveux » |
| 101 | Industry Interviews | Alex + Sam interviewent des experts de la catégorie (devient la graine du podcast Quietude) |
| 102 | Social Screenshots | Réponses de réflexion Mira (anonymisées, consenties) — or de preuve sociale |
| 108 | Changelogs | Changelog public sur `quietude.app/changes` — signal de momentum produit |
| 115 | Curation as Marketing | Feature « field recordings de l'année » curée ; annuaire Quietude Spaces |
| 135 | Support as Marketing | Faire surface les moments de support client / réflexion Mira en contenu |
| 138 | Podcast Tours | Alex sur Huberman, le business événementiel-partenaires, Tim Ferriss, Rich Roll, Rangan Chatterjee |

**Q3+ :**

| # | Idée | Note Quietude |
|---|---|---|
| 4 | Programmatic SEO | Pages de villes Quietude Guides une fois le programme Guides à l'échelle |
| 9 | Knowledge Base SEO | Quand les docs d'aide scalent assez pour avoir une couverture problème-solution |
| 14 | Side Projects | À terme un outil gratuit adjacent à Quietude qui vit hors de l'app |
| 15 | Engineering as Marketing | Guide d'interprétation HRV ; auto-évaluation du système nerveux ; annuaire de finder de sound bath |
| 18 | Calculator Marketing | Calculateur de latence de sommeil ; index de surstimulation |
| 20 | Microsites | Pour des moments GTM spécifiques (ex. lancement GA de Mira) |
| 23 | Podcast Advertising | Huberman, Tim Ferriss, Rich Roll, le business événementiel-partenaires — host-read le plus pertinent |
| 24 | Pre-targeting Ads | Audiences chaudes via le contenu avant la réponse directe |
| 29 | Reddit Ads | r/HSP, r/ADHD, r/somatic — forte densité d'ICP, faible saturation d'annonceurs |
| 30 | Quora Ads | Riche en intention pour les requêtes « pourquoi la méditation ne marche pas » |
| 32 | YouTube Ads | Pre-roll sur les vidéos Huberman / Lex Fridman / créateurs bien-être |
| 33 | Cross-Platform Retargeting | Couche standard une fois le paid en marche |
| 35 | Community Marketing | Communauté Quietude Spaces (Discord/Circle) ; héberger des drop-ins mensuels |
| 42 | Short Form Video | TikTok / Reels — éducation somatique + UGC masque |
| 55 | Influencer Whitelisting | Faire tourner des ads via les comptes ambassadeurs / Guides pour l'authenticité |
| 57 | Expert Networks | Le programme Quietude Guides EST ça — hôtes certifiés qui peuvent faire du marketing |
| 60 | Pixel Sharing | Standard une fois le paid en marche |
| 61 | Shared Slack Channels | Slacks des lieux partenaires (Aurora, Lumen, Stillwater) |
| 63 | Integration Marketing | Apple Health (données HRV), Oura, Whoop — co-marketing |
| 66 | Virtual Summits | Quietude participe ou héberge |
| 68 | Local Meetups | Villes à forte densité d'ICP (SF, NYC, LA, Austin) |
| 69 | Meetup Sponsorship | Sponsoriser des meetups bien-être / biohacking |
| 72 | Conference Sponsorship | Conférences sectorielles une fois le budget débloqué |
| 75 | Fundraising PR | Moment « Quietude lève 3 M€ » quand le seed se boucle |
| 78 | Product Hunt Launch | Moment de lancement public de Mira |
| 79 | Early-Access Referrals | Liste d'early-access de l'App GA (croisé avec Referral) |
| 81 | Early Access Pricing | App GA — tier d'early-access verrouillé pour la première cohorte |
| 82 | Product Hunt Alternatives | BetaList, Launching Next, AlternativeTo à la GA |
| 97 | Playlists as Marketing | Quietude cure des playlists Spotify pour l'écoute somatique |
| 98 | Template Marketing | PDF gratuits de protocole « reset du système nerveux » |
| 100 | Promo Videos | Films de marque haut de gamme — Ed Dorsey conseille, Matt Mikkelsen field audio |
| 103 | Online Courses | Le cours Sound Philosophy d'Alex ; le cours de méthodologie somatique de Sam |
| 107 | Podcasts | Podcast Quietude — format interview avec des experts de catégorie et des clients |
| 111 | Challenges as Marketing | « Reset du système nerveux en 21 jours » — élégant, sans ton fitness-bro |
| 113 | Controversy as Marketing | Méditation-vs-Régulation EST une controverse douce — s'y appuyer avec soin |
| 126 | YouTube Reviews | Pitcher Quietude aux YouTubeurs bien-être — tier fan-créateur de Huberman |
| 127 | YouTube Channel | Behind-the-scenes du sound design ; démos de session de Sam |
| 129 | Review Sites | Avis App Store activement gérés ; Trustpilot pour le masque Shopify |
| 130 | Live Audio | Twitter Spaces / LinkedIn Audio avec Alex sur le son + le corps |
| 134 | Certifications | La certif Quietude Guides EST ça — pilote Q3+ |

**Q4+ / jeu long :**

| # | Idée | Note Quietude |
|---|---|---|
| 56 | Reseller Programs | Plateformes de bien-être corporate (Modern Health, Lyra) comme revendeurs |
| 67 | Roadshows | Quietude Experiences EST ça — pop-ups masque + session d'écoute dans 3 villes |
| 71 | Conferences | « Sound + the Body » hébergée par Quietude — moment de jeu long qui définit la catégorie |
| 76 | Documentaries | L'histoire d'Alex est de niveau documentaire — jeu long |
| 77 | Black Friday Promotions | Bundle masque + Premium des fêtes |
| 80 | New Year Promotions | Campagne de reset du système nerveux du Nouvel An |
| 84 | Giveaways | Giveaway de masque avec une marque partenaire (tier Wellness Mama) |
| 85 | Vacation Giveaways | Giveaway Quietude + partenaire de retraite (quietude.center pourrait être le lieu) |
| 87 | Powered By Marketing | Badge « Système son par Quietude » dans les installs B2B de lieux |
| 104 | Book Marketing | Sound Philosophy en livre — ancre de positionnement de jeu long |
| 105 | Annual Reports | « État du système nerveux » — les données de Quietude + commentaire sectoriel |
| 106 | End of Year Wraps | « Votre année système nerveux » — équivalent Spotify Wrapped |
| 110 | Awards as Marketing | Quietude fonde un prix pour le design acoustique biophilique innovant |
| 116 | Grants as Marketing | Abonnements Quietude gratuits pour thérapeutes, travailleurs sociaux, premiers intervenants |
| 119 | OOH Advertising | Panneaux SF / NYC si le budget de Series A se débloque |
| 120 | Marketing Stunts | Une installation son publique pourrait marcher — cohérente avec la marque |
| 121 | Guerrilla Marketing | Installation son dans le métro / aéroport — intéressant mais nécessite du soin |
| 131 | International Expansion | Siège Finlande + ICP global — Q4 ou post-Series A |

**Skip / hors-marque pour Quietude :**

| # | Idée | Pourquoi skipper |
|---|---|---|
| 16 | Importers as Marketing | Pas de données concurrent à importer (bien-être consumer, pas SaaS) |
| 19 | Chrome Extensions | Hors-plateforme (produit mobile-first) |
| 21 | Scanners | Pas de fit produit évident |
| 22 | Public APIs | Pas le cœur de business |
| 27 | Twitter Ads | Priorité plus basse sauf si la présence X d'Alex grandit |
| 34 | Click-to-Messenger Ads | Hors-marque (pas de pattern de vente piloté par DM) |
| 41 | X Audience | Dépend de la bande passante d'Alex — reporter sauf s'il le veut |
| 43 | Engagement Pods | Hors-marque |
| 73 | Media Acquisitions | Trop capital-intensif à ce stade |
| 83 | Twitter Giveaways | Voix hors-marque |
| 86 | Lifetime Deals | Conflit de marque — pressure la voix « sans pression » et abîme le calcul de LTV |
| 88 | Free Migrations | Pas de données concurrent à migrer |
| 89 | Contract Buyouts | Pas pertinent pour des abonnés D2C |
| 99 | Graphic Novel Marketing | Hors-marque |
| 112 | Reality TV Marketing | Hors-marque |
| 117 | Product Competitions | Pas un produit développeur |
| 118 | Cameo Marketing | Hors-marque |
| 122 | Humor Marketing | La voix de marque est sérieuse ; l'humour sonnerait faux |
| 123 | Open Source as Marketing | Bibliothèque audio propriétaire |
| 125 | App Marketplaces | Pas pertinent pour une app consumer native (pas de pattern app-d'app) |
| 128 | Source Platforms | G2 / Capterra sont orientés B2B ; le D2C utilise les avis App Store |
| 132 | Price Localization | Q4+ — lié à l'expansion internationale |
| 136 | Developer Relations | Pas un produit dev |

### 12.2 Idées d'activation (7 mappées)

| # | Idée | Statut | Note Quietude |
|---|---|---|---|
| 124 | App Store Optimization | Maintenant | Priorité Q1 — réécriture de la fiche dans la voix (aussi Acquisition) |
| 90 | One-Click Registration | Maintenant | OAuth (Apple, Google) pour le signup de l'app — lift d'activation standard |
| 51 | Onboarding Emails | Q2 | Flow 2 — en attente jusqu'à UI stable post-refonte-onboarding |
| 96 | Onboarding Optimization | Q1-Q2 | Le test à 3 variantes EST ça — travail d'activation primaire |
| 47 | Founder Welcome Email | Q2 | Bienvenue personnelle d'Alex ou Sam tôt dans le Flow 2 |
| 48 | Dynamic Email Capture | Q2 | Capture intelligente sur `quietude.app` — exit intent + profondeur de scroll |
| 95 | Concierge Setup | Q3+ | Onboarding high-touch pour les clients B2B de lieux + abonnés à forte valeur |

### 12.3 Idées de rétention (8 mappées)

| # | Idée | Statut | Note Quietude |
|---|---|---|---|
| 46 | Reactivation Emails | Maintenant | Le Flow 4 ship en semaines 3–4 — exactement ça |
| 52 | Win-back Emails | Q1 (semaine 11-12) | Campagne autonome par-dessus le Flow 4 |
| 53 | Trial Reactivation | Q2 | Campagne de récupération d'essai expiré une fois le paywall en marche |
| 45 | Mistake Email Marketing | Q2 | Quand quelque chose tourne vraiment mal, envoyer un « oups » — pilote l'engagement |
| 50 | Inbox Placement | Q1 | La stratégie de silo de sous-domaines (`mail.quietude.app` / `commerce.quietude.app`) adresse ça |
| 91 | In-App Upsells | Q2 | Points d'upsell Premium dans l'app (aussi Revenue) |
| 94 | Offboarding Flows | Q2 | Optimiser le flow d'annulation pour retenir ou apprendre — alimente l'intel de churn |
| 135 | Support as Marketing | Q2 | Les stories de support client font surface en contenu (aussi Acquisition) |

### 12.4 Idées de referral (5 mappées)

| # | Idée | Statut | Note Quietude |
|---|---|---|---|
| 62 | Affiliate Program | Maintenant | Le programme d'ambassadeurs v1 est exactement ça — lancé avec les 5 inbounds |
| 137 | Two-Sided Referrals | Q2 | Récompenser à la fois le parrain et le parrainé — moment share-after-shift + flow de cadeau |
| 92 | Newsletter Referrals | Q3 | Si on lance une newsletter, mécanique de referral à la Sparkloop |
| 93 | Viral Loops | Q3 | Mécaniques de partage intégrées post-réflexion Mira |
| 79 | Early-Access Referrals | Q3 | Referrals de la liste d'early-access de l'App GA (croisé avec Acquisition) |

### 12.5 Idées de revenue (3 mappées — la plupart des idées servent le top-of-funnel)

| # | Idée | Statut | Note Quietude |
|---|---|---|---|
| 91 | In-App Upsells | Q2 | Prompts d'upgrade Premium ; cross-sell de masque depuis l'app (aussi Rétention) |
| 132 | Price Localization | Q4+ | Ajuster le pricing au pouvoir d'achat local une fois à l'international |
| 86 | Lifetime Deals | Skip | Conflit de marque — voir la liste de skip d'Acquisition |

### 12.6 Idées transversales / fondation de marque

| # | Idée | Statut | Note Quietude |
|---|---|---|---|
| 139 | Customer Language | Maintenant | Réponses de réflexion Mira + langage des 7 D = la source de vérité pour le langage client à travers toute la copy |
| 114 | Moneyball Marketing | En continu | Trouver les canaux sous-valorisés à chaque stade — méthodologie, pas une tactique unique |

### Résumé de la banque d'idées

- **88 idées applicables à l'Acquisition** (le stage dominant au stade actuel de Quietude — logique, le produit de Quietude convertit bien ; le goulot est le top of funnel)
- **7 idées à l'Activation, 8 à la Rétention** (plus petites parce que ces stages portent sur la profondeur, pas la largeur — exécuter les quelques bonnes correctement plutôt que de dérouler un large menu de tactiques)
- **5 idées au Referral** (piloté par le programme, pas par la tactique)
- **3 idées au Revenue** (l'essentiel du travail revenue est de la stratégie de pricing, pas des astuces tactiques)
- **2 transversales**
- **23 idées skippées pour le fit marque / business-model** — le positionnement de catégorie de Quietude contraint ce qui est disponible

**Ce que ça prouve :** le plan représente à peu près 30 % de la surface tactique disponible, pas 100 %. C'est approprié à ce stade et à ce budget. À mesure que la capacité se débloque à travers Q2 → Q3 → Series A, le croisement devient l'inventaire dans lequel on pioche pour scaler l'activité sans perdre la cohérence stratégique.

---

## 13. Mesure, RACI, décisions ouvertes, annexe

### Mesure — les métriques qui comptent

**North star (proposé) :**
**Ratio LTV-blended-sur-CAC-blended par utilisateur acquis**, où :
- La LTV blended combine le revenu d'abonnement app + le revenu hardware (masque + enceintes) + tous les cross-sells, par cohorte
- Le CAC blended combine la dépense paid + le coût de production de contenu + les commissions d'ambassadeurs + la dépense d'outils lifecycle, par cohorte

Ça capture le business model : le wedge du masque n'est pas gratuit s'il coûte X€ à fabriquer, et l'abonnement app n'est pas cher à acquérir si un moment de PR à la Bryan-Johnson s'autofinance.

Si une métrique unique est préférée pour le focus au niveau équipe, se rabattre sur : **nouveaux abonnés D2C mensuels issus des canaux non-paid.** Ça isole les canaux à effet de cumul dont dépend la stratégie de jeu long.

**Indicateurs avancés par stage AARRR :**

| Stage | Indicateurs avancés |
|---|---|
| Acquisition | Visites organiques/mois (global + par pilier), taux visite-vers-install App Store, engagement LinkedIn d'Alex → abonnés email, taux de conversion événement-vers-app, visites attribuées aux ambassadeurs |
| Activation | Conversion Jour 1 / Jour 7 / Jour 35 → payant, taux de complétion de session d'onboarding, complétion de la réflexion Mira de première session |
| Rétention | Rétention à 30 / 60 / 90 jours, churn mensuel, taux de réactivation du Flow 4, taux d'activation hardware → app |
| Referral | Nouveaux abonnés attribués aux ambassadeurs (Dub), taux de share-after-shift, referrals du pilote Guides (une fois en live) |
| Revenue | MRR blended, ARPU, % d'adoption du plan annuel, LTV par cohorte, taux d'attach du masque |

**Cadence de revue :**
- **Hebdomadaire :** sync fCMO ↔ Alex de 30 min. Tableau de bord AARRR + les ships de la semaine.
- **Mensuel :** revue complète des métriques (sync étendu, Sam inclus). Comparer aux cibles KPI trimestrielles.
- **Trimestriel :** recalibrage du plan. Ce qui marche, ce qui ne marche pas, quels moves de stade de financement on déclenche.

### RACI

| Domaine | Responsible | Accountable | Consulted | Informed |
|---|---|---|---|---|
| Plan stratégique (ce document) | Casey | Alex | Sam, Emily | Équipe |
| Voix de marque | Alex + Sam | Alex + Sam | Casey | Équipe |
| Implémentation app + onboarding | Devon | Alex | Casey | Équipe |
| Flows lifecycle (Customer.io) | Casey | Alex | Sam (QA copy) | Équipe |
| Contenu SEO | Casey | Casey | Sam, Alex | Équipe |
| Copy App Store | Casey | Alex | Sam | Équipe |
| Cadence LinkedIn d'Alex | Alex | Alex | Casey (orchestration) | Équipe |
| Événements | Alex + Sam | Alex | Casey (instrumentation uniquement) | Équipe |
| Programme d'ambassadeurs | Casey | Casey | Alex | Équipe |
| Ventes B2B | Alex | Alex | Casey (études de cas) | Équipe |
| Pricing | Alex | Alex | Casey | Sam |
| Narrative investisseur | Alex | Alex | Casey, Sam | Équipe |
| Programme Quietude Guides (Q3+) | À définir (probablement futur recrutement) | Alex + Sam | Casey | Équipe |
| Futur recrutement marketing (Q3) | Casey | Alex | Sam | Équipe |

### Décisions ouvertes qui bloquent le plan

Les plus bloquantes, classées par impact :

1. **Domaine canonique.** Les données SEO + ce plan recommandent `quietude.app`. Nécessite une validation exec + un plan d'exécution de 301. *Bloque : consolidation de domaine, fondation SEO, migration de l'expéditeur email.*
2. **Définition de la métrique de rétention.** Réconcilier le claim de 38 % de rétention à 12 mois vs 29 % de churn mensuel App Store. *Bloque : dashboards propres, cohérence de la narrative investisseur, lectures des tests lifecycle.*
3. **Périmètre de la réflexion post-session de Mira.** Est-ce que Mira supporte ça actuellement, ou c'est du nouveau build ? *Bloque : Variantes d'onboarding 1 et 2 (qui dépendent du moment de réflexion Mira), moves de cumul de rétention.*
4. **Timeline de stabilité de l'UI de l'app.** Quand est-ce que le retrait du gate des écouteurs + la refonte de l'onboarding permettent au Flow 2 de shipper sans risque de retravail ? *Bloque : Flow 2, lifecycle complet, timing de l'acquisition paid.*
5. **Timeline de lancement GA.** Quand est-ce que la beta throttlée devient GA ? *Bloque : scale de l'acquisition paid, planning GTM Q3.*
6. **Vérité terrain de la structure de pricing.** Qu'est-ce qui est réellement facturé aujourd'hui ? *Bloque : conclusions de l'audit de pricing, test du plan annuel par défaut, calcul de LTV blended.*
7. **Périmètre du premier recrutement marketing.** Owner lifecycle + content, ou autre chose ? Quand la fiche de poste est-elle rédigée ? *Bloque : plan de capacité Q3, succession du travail opérationnel du fCMO.*
8. **Structure de commission des ambassadeurs.** €/abonné, rev-share, hybride ? *Bloque : lancement du programme d'ambassadeurs, dashboards d'attribution.*

### Annexe — liens d'approfondissement

**Publiés à l'équipe via le repo GitHub `Quietude-Inc/quietude-context` :**
- `marketing/seo/plan.md` — Plan SEO 90 jours complet + keyword research
- `marketing/seo/keyword-shortlist.md` — Shortlist de mots-clés Tier 1
- `marketing/seo/raw/` — Pulls API Ahrefs + DataForSEO
- `marketing/onboarding-recommendation.md` — Plan de test d'onboarding à trois variantes

**Contexte stratégique écrit par les fondateurs** (dans la knowledge base interne de Quietude) :
- Deck de seed — Narrative investisseur
- Sound Philosophy — Doc de travail technique/philosophique d'Alex
- Marketing OS — Voix de marque, rythme de contenu, système visuel
- Doc ICP — Profil d'audience D2C
- Note Méditation-vs-Régulation (2026-05-19) — Pilier de contenu central
- Transcript du call de kickoff (2026-05-18) — Décisions + questions ouvertes
- Snapshot de la copy App Store + analyse d'écart de voix
- Snapshot des métriques App Store (2026-05-16)
- Inventaire des flows lifecycle Customer.io

---

*Plan marketing v1. Préparé par Casey Reed (fCMO), 2026-05-27. Pour relecture et discussion de l'équipe.*
