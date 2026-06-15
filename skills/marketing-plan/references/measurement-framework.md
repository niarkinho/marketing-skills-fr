# Cadre de mesure — KPIs, North Stars, cadence

Chaque plan a besoin d'une section mesure qui dit à l'équipe comment savoir si le plan marche. Ce doc est la source de la sous-section mesure de la Section 13.

**Docs associés :**
- `growth-patterns.md` — le chemin de croissance VC 3-3-2-2-2 (×3 années 1–2, ×2 années 3–7 à partir d'1M$ d'ARR) et dans quelle phase de croissance SaaS se trouve l'entreprise (0–10K€ / 10K–100K€ / 100K–1M€+)
- `budget-planning.md` — calcul du CAC (blended, pas paid-only) et le reality check de la prévision (les prévisions sous 100M$ d'ARR sont des suppositions éclairées, pas des prédictions précises)

## Le principe du north-star

Un north star est une métrique unique qui capture la thèse du business model au plus haut niveau. Il devrait :
- Être dérivable du funnel + du modèle de revenu
- Bouger assez lentement pour être une boussole stratégique (pas ballotté par le bruit hebdomadaire)
- S'arbitrer correctement contre les autres métriques — améliorer le north star devrait généralement améliorer le business

Ne pas se rabattre par défaut sur « ARR » ou « MRR » seuls. Ce sont des résultats, pas des norths. Choisir quelque chose qui capture le business model.

## Patterns de north-star par business model

### SaaS B2B (abonnement)
- **Net Revenue Retention (NRR)** — garde le focus sur les clients existants + l'expansion
- Alternative : « Rétention de logos × expansion ARR »
- Pourquoi : l'ARR seul cache le churn / laisse la croissance en gross-adds masquer les problèmes de product fit

### App grand public D2C (abonnement)
- **LTV blended / CAC blended** — garde les unit economics honnêtes à mesure que la couche paid scale
- Alternative : « Utilisateurs payants Jour-35 d'une cohorte × LTV »
- Pourquoi : les métriques d'abonnement mensuelles sont volatiles ; cohorte × LTV lisse ça

### Hybride hardware + software (ex : Quietude)
- **LTV blended / CAC blended à travers hardware + software** — capture la thèse du coin
- Alternative : « Conversion acheteurs-hardware-vers-abonné × marge blended »
- Pourquoi : le revenu hardware n'est pas gratuit (coût de fabrication) ; le revenu abonnement n'est pas cher à acquérir si le hardware le finance

### Marketplace (bilatéral)
- **Ratio de liquidité × take-rate** — capture les deux faces + la monétisation
- Alternative : « Utilisateurs transactant mensuellement × take-rate × fréquence de répétition »
- Pourquoi : le GMV seul ne capture pas si la marketplace devient une habitude

### Outil développeur / open source
- **Développeurs actifs hebdomadaires × conversion-payante** — capture à la fois l'adoption et la monétisation
- Alternative : « Orgs actives hebdomadaires × sièges par org × ARPU »

### Business de contenu / média
- **Lecteurs / auditeurs actifs quotidiens × revenu pub par session** — capture à la fois la portée et la monétisation
- Alternative : « Nombre d'abonnés × rétention × ARPU »

### Commerce (DTC, hors abonnement)
- **Taux de réachat × AOV × fréquence** — capture la monétisation superposée à la qualité du client
- Alternative : « LTV client / CAC × période de payback »

## Indicateurs avancés par stade AARRR

Après le north star, chaque plan a besoin d'indicateurs avancés par stade AARRR. Ils bougent plus vite que le north star et déclenchent des investigations.

### Indicateurs avancés d'Acquisition
- Visites organiques/mois, total + par pilier (santé SEO)
- Taux visite-vers-install App Store / Play Store (santé ASO)
- Croissance du canal social founder-led → conversion en abonnés email (funnels LinkedIn / X / Substack)
- Taux de conversion événement-vers-app (ROI événement)
- Visites attribuées aux ambassadeurs (funnel de recommandation)
- CAC paid par canal (quand le paid est actif)

### Indicateurs avancés d'Activation
- Taux de conversion Jour 1 / Jour 7 / Jour 35 → payant
- Taux de complétion de session d'onboarding
- Complétion de la première action clé (événement d'activation post-signup)
- Taux de conversion App Store (install → essai → payant)
- Taux de conversion essai → payant

### Indicateurs avancés de Rétention
- Rétention Jour 30 / Jour 60 / Jour 90
- Taux de churn mensuel (gross + net)
- Engagement email lifecycle (ouverture / clic / désabonnement par flow)
- Taux d'activation hardware → app (pour les business hybrides)
- Taux de win-back / réactivation

### Indicateurs avancés de Recommandation
- Nouveaux abonnés attribués aux ambassadeurs (via Dub ou similaire)
- Taux de moments de partage-après-valeur (% d'utilisateurs qui partagent)
- Taux de complétion de recommandation bilatéral
- Recommandations du programme Guides (quand en ligne)
- Score NPS (si enquêté)

### Indicateurs avancés de Revenu
- ARPU par cohorte
- % d'adoption du plan annuel
- LTV de cohorte par source
- Évolutions du mix de plans
- Taux d'attache masque-de-nuit / hardware (pour l'hybride)
- Expansion revenue (B2B)

## Cadence de revue

Le plan devrait spécifier trois rythmes :

### Hebdomadaire (sync opérationnelle)
- **Qui :** fCMO ↔ fondateur (CEO généralement)
- **Durée :** 30 min
- **Format :** scoreboard AARRR (chiffres actuels vs. semaine dernière sur les indicateurs avancés) + livraisons de la semaine + blockers
- **Sortie :** action items, décisions prises

### Mensuelle (revue de métriques)
- **Qui :** fCMO + fondateur + équipe étendue (CXO, product lead, designer le cas échéant)
- **Durée :** 60–90 min
- **Format :** revue complète des métriques + comparaison avec les cibles KPI trimestrielles + enseignements qualitatifs + repriorisation de la banque d'idées
- **Sortie :** ajustements possibles du plan, décisions de recrutement

### Trimestrielle (recalibrage du plan)
- **Qui :** fCMO + fondateurs + advisors clés
- **Durée :** 2–3 heures
- **Format :** revue complète du plan contre les résultats 90 jours et 12 mois, analyse au niveau canal, vérification de transition de stade de financement, recalibrage des 90 prochains jours
- **Sortie :** plan mis à jour (peut être une itération de document v2 / v3)

## Fixation des cibles KPI

Pour chaque trimestre en Section 10, le plan doit inclure 3–5 cibles KPI spécifiques. Elles devraient être :
- **Spécifiques** — pas « améliorer la rétention », mais « rétention Jour 30 de 22 % → 30 % »
- **Mesurables** — tirées d'une source de données branchée
- **Ambitieuses mais plausibles** — basées sur l'état du funnel + les patterns historiques
- **Déclencheuses de décision** — si manquée, qu'est-ce que ça signifie ? (Ajuster la stratégie, tuer un canal, etc.)

### Patterns de cibles KPI par trimestre

**T1 (trimestre fondation) :**
- Surtout des métriques de *socle* — réparer les fuites. « La chute de conversion du headphones-gate s'inverse. » « Jour 1 → payant +25–50 %. »
- Quelques métriques de *fondation* — poser les rails. « 4 piliers SEO plantés. » « Réécriture App Store livrée. »
- Éviter les cibles de croissance audacieuses — les fondations ne sont pas encore en place

**T2 (trimestre validation) :**
- Surtout des métriques de *validation* — ce qu'on a construit marche-t-il ? « CAC paid < X € blended. » « Trafic organique 1 500–3 500/mois. »
- Quelques métriques de *cohorte* — les nouvelles cohortes se comportent-elles mieux ? « Rétention Jour 7 cohorte T2 vs. T1. »

**T3 (trimestre scaling) :**
- Surtout des métriques de *scaling* — jusqu'où ça va ? « Scaling paid à 20–30K €/mois avec CAC stable. » « Premier cas de référence d'install B2B en ligne. »
- Quelques métriques de *capacité* — quelles nouvelles choses sont en ligne ? « Premier pilote Guides lancé. »

**T4 (trimestre cumul) :**
- Surtout des métriques de *cumul* — le flywheel tourne-t-il ? « 50 %+ des nouveaux abonnés viennent de canaux non-paid. » « 15–25 % des nouveaux abonnés portés par les ambassadeurs. »
- Quelques métriques de *narratif* — l'histoire de la Série A s'écrit-elle d'elle-même ? « LTV/CAC blended > 3. »

## Ancrer sur le chemin de croissance VC

Pour les clients VC-backed au-delà d'1M$ d'ARR, ancrer les cibles 12 mois et pluriannuelles sur la **règle du 3-3-2-2-2** (×3 années 1 et 2, puis ×2 années 3 à 7). L'atteindre est rare ; la plupart des entreprises n'y arrivent pas. Ancrer dessus force le plan à soit l'égaler et montrer comment, soit défendre explicitement le choix d'une trajectoire plus lente. Table complète et contexte dans `growth-patterns.md`.

Pour les entreprises non-VC-backed (bootstrappées, financées par le fondateur, axées profit), le 3-3-2-2-2 ne s'applique pas. Utiliser plutôt des cibles de pattern linéaire (« X € de MRR ajoutés par mois ») ou de marche d'escalier (« saut de Y € de revenu après le lancement du tier enterprise »).

## Reality check de la prévision

Un plan dérive un budget et un objectif annuel. Il ne produit pas une prévision 12 mois mois-par-mois fiablement exacte au dollar près.

**Sauf si l'entreprise est cotée en bourse, toutes les prévisions sont des suppositions éclairées.** Aucune startup sous 100M$ d'ARR n'atteint de façon constante ses prévisions mois-par-mois. La revue trimestrielle est le moment où le plan s'ajuste — pas le moment où la variance est traitée comme un échec.

Ce à quoi le plan s'engage honnêtement :
- L'objectif annuel est une direction-de-déplacement défendable
- Le budget est l'engagement de ressources qui rend l'objectif plausible
- La roadmap 90 jours (Section 9) est ce qui est actionnable maintenant
- La projection mois-par-mois est illustrative, pas promise

Les fondateurs qui sur-ingénierent la prévision finissent par expliquer la variance chaque mois au lieu d'exécuter. Le plan devrait résister à ça — nommer la cible annuelle, les KPI trimestriels et les critères d'arrêt. Ne pas promettre le mois.

Contexte complet dans `budget-planning.md`.

## Critères d'arrêt (kill criteria)

Pour chaque canal ou initiative, le plan devrait spécifier quand s'arrêter. Souvent absents des plans, les critères d'arrêt forcent la discipline.

Exemples :
- « Si un canal paid a un CAC > 2× la cible après 30 jours à une dépense significative, mettre en pause. »
- « Si le Variant 3 d'onboarding ne montre pas de lift statistiquement significatif (ou un lift directionnel + un signal qualitatif congruent) après 4 semaines, basculer sur le Variant 1. »
- « Si le Flow 4 lifecycle a un taux d'ouverture < 12 % après 6 semaines, refaire les objets + la segmentation d'audience. »

## Métriques garde-fous

Certaines métriques reçoivent un garde-fou dur (ne peut pas descendre sous un seuil). Utile pour protéger la marque ou les unit economics pendant une croissance agressive.

Exemples :
- « Un taux de plaintes sur la brand voice > 1 % des retours clients déclenche une revue de contenu. »
- « Un CAC paid > X € deux mois consécutifs met en pause le scaling paid en attendant un audit. »
- « Une note App Store qui descend sous 4,5 déclenche une revue produit. »

## Mapping des sources de données

Le plan devrait nommer d'où vient chaque métrique. Ça le rend auditable.

| Métrique | Source |
|---|---|
| Trafic organique | GA4 / Ahrefs |
| Conversion App Store | App Store Connect |
| Conversion de funnel (Jour N → payant) | Analytics interne (Mixpanel / Amplitude) ou export de cohorte App Store Connect |
| Rétention | Segments Customer.io + product analytics |
| MRR / ARR | Stripe (via MCP si branché) |
| Mix de plans | Stripe |
| Métriques email lifecycle | Customer.io |
| Attribution ambassadeurs | Dub.co |
| Activation hardware → app | Shopify + App Store + jointure interne |
| NPS | Outil d'enquête (Customer.io / Typeform / SurveyMonkey) |

## Quand la data n'est pas branchée

Si une métrique ne peut pas être mesurée actuellement, la flagger dans les décisions ouvertes de la Section 13. Exemple :

> « Le taux d'activation hardware → app n'est pas actuellement visible dans le dashboard App Store. Nécessite une jointure Shopify ↔ App Store Connect. Item de travail T1. »

Un plan avec des objectifs non-mesurables est un plan qui ne peut pas être validé. Faire remonter le travail d'instrumentation explicitement.

## Cadence de reporting + automatisation

Quand c'est possible, auto-générer la revue de métriques plutôt que de la construire manuellement à chaque fois. Stripe MCP + GA4 MCP + Customer.io MCP peuvent tirer la plupart de ce qu'il faut.

Pour les clients Tier 1, un simple email hebdo de métriques à l'équipe (table Markdown, générée via skills + MCPs) ne coûte rien et crée de la discipline.

Pour les clients Tier 2+, envisager un vrai dashboard (Hex, Metabase, Looker ou outil interne).
