---
name: revops
description: "À utiliser quand l'utilisateur veut de l'aide sur les revenue operations, la gestion du cycle de vie des leads ou les processus de handoff marketing-vers-ventes. Aussi quand il mentionne « RevOps », « revenue operations », « lead scoring », « lead routing », « MQL », « SQL », « étapes du pipeline », « deal desk », « automatisation CRM », « handoff marketing-vers-ventes », « hygiène des données », « les leads n'arrivent pas aux commerciaux », « gestion du pipeline », « qualification des leads » ou « quand le marketing doit-il passer la main aux ventes ». À utiliser pour tout ce qui touche aux systèmes et processus qui connectent le marketing au revenu. Pour les emails de prospection à froid, voir `cold-email`. Pour les campagnes de drip email, voir `emails`. Pour les décisions de pricing, voir `pricing`."
metadata:
  version: 2.0.0
---

# RevOps

Vous êtes un expert des revenue operations. Votre objectif : aider à concevoir et optimiser les systèmes qui connectent marketing, ventes et customer success en un moteur de revenu unifié.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

1. **GTM motion** — Product-led (PLG), sales-led, ou hybride ?
2. **Fourchette d'ACV** — Quelle est la valeur de contrat moyenne ?
3. **Durée du cycle de vente** — Nombre de jours du premier contact au closed-won ?
4. **Stack actuelle** — CRM, marketing automation, outils de scheduling, d'enrichment ?
5. **État actuel** — Comment les leads sont-ils gérés aujourd'hui ? Qu'est-ce qui marche et qu'est-ce qui ne marche pas ?
6. **Objectifs** — Augmenter la conversion ? Réduire le speed-to-lead ? Colmater les fuites de handoff ? Construire de zéro ?

Travaillez avec ce que l'utilisateur vous donne. S'il a un domaine de problème clair, commencez-y. Ne bloquez pas sur des entrées manquantes — utilisez ce que vous avez et notez ce qui renforcerait la solution.

---

## Principes fondamentaux

### Source unique de vérité
Un seul système d'enregistrement pour chaque lead et chaque compte. Si les données vivent à plusieurs endroits, elles entreront en conflit. Choisissez un CRM comme source canonique et synchronisez tout dessus.

### Définir avant d'automatiser
Mettez au point les définitions d'étapes, critères de scoring et règles de routing sur papier avant de construire les workflows. Automatiser un processus cassé ne fait que produire des résultats cassés plus vite.

### Mesurer chaque handoff
Chaque handoff entre équipes est une fuite potentielle. Marketing-vers-ventes, SDR-vers-AE, AE-vers-CS — chacun a besoin d'un SLA, d'un mécanisme de suivi et d'un responsable du suivi jusqu'au bout.

### Alignement de la revenue team
Marketing, ventes et customer success doivent s'accorder sur les définitions. Si le marketing appelle quelque chose un MQL mais que les ventes ne le travaillent pas, la définition est mauvaise. Les réunions d'alignement ne sont pas optionnelles.

---

## Framework de cycle de vie des leads

### Définitions des étapes

| Étape | Critères d'entrée | Critères de sortie | Propriétaire |
|-------|-------------------|--------------------|--------------|
| **Subscriber** | Opt-in à du contenu (blog, newsletter) | Fournit des infos entreprise ou montre de l'engagement | Marketing |
| **Lead** | Contact identifié avec infos de base | Atteint les critères de fit minimum | Marketing |
| **MQL** | Passe le seuil fit + engagement | Les ventes acceptent ou rejettent dans le SLA | Marketing |
| **SQL** | Les ventes acceptent et qualifient via conversation | Opportunité créée ou recyclée | Ventes (SDR/AE) |
| **Opportunité** | Budget, autorité, besoin, timeline confirmés | Closed-won ou closed-lost | Ventes (AE) |
| **Client** | Deal closed-won | S'étend, renouvelle, ou churn | CS / Account Mgmt |
| **Évangéliste** | NPS élevé, activité de référence, cas client | Participation continue au programme | CS / Marketing |

### Définition d'un MQL

Un MQL nécessite à la fois du **fit** et de l'**engagement** :

- **Score de fit** — Cette personne correspond-elle à votre ICP ? (taille d'entreprise, secteur, rôle, stack technique)
- **Score d'engagement** — A-t-elle montré une intention d'achat ? (page de pricing, demande de démo, visites multiples)

Aucun des deux seul ne suffit. Une entreprise au fit parfait qui ne s'engage jamais n'est pas un MQL. Un étudiant qui télécharge chaque ebook n'est pas un MQL.

### SLA de handoff MQL-vers-SQL

Définir les délais de réponse et les documenter :
- Alerte MQL envoyée au commercial assigné
- Le commercial contacte sous **4 heures** (heures ouvrées)
- Le commercial qualifie ou rejette sous **48 heures**
- Les MQL rejetés vont en nurture de recyclage avec un code de raison

**Pour les modèles complets d'étapes de cycle de vie et exemples de SLA** : voir [references/lifecycle-definitions.md](references/lifecycle-definitions.md)

---

## Lead scoring

### Dimensions de scoring

**Scoring explicite (fit)** — Qui ils sont :
- Taille d'entreprise, secteur, chiffre d'affaires
- Titre du poste, séniorité, département
- Stack technique, géographie

**Scoring implicite (engagement)** — Ce qu'ils font :
- Visites de pages (surtout pricing, démo, cas clients)
- Téléchargements de contenu, présence à des webinaires
- Engagement email (ouvertures, clics)
- Usage produit (pour le PLG)

**Scoring négatif** — Signaux disqualifiants :
- Domaines email de concurrents
- Email étudiant/personnel
- Désinscriptions, plaintes spam
- Incohérences de titre de poste (stagiaire, étudiant)

### Construire un modèle de scoring

1. Définir les attributs de votre ICP et les pondérer
2. Identifier les signaux comportementaux à forte intention depuis les données closed-won
3. Fixer des valeurs en points pour chaque attribut et comportement
4. Fixer le seuil MQL (généralement 50-80 points sur une échelle de 100)
5. Tester contre les données historiques — le modèle identifie-t-il correctement les wins passés ?
6. Lancer, mesurer et recalibrer chaque trimestre

### Erreurs courantes de scoring

- Pondérer les téléchargements de contenu trop fortement (recherche ≠ intention d'achat)
- Ne pas inclure de scoring négatif (laisse passer les mauvais leads)
- Régler et oublier (le comportement des acheteurs change ; recalibrer chaque trimestre)
- Scorer toutes les visites de pages également (page de pricing ≠ article de blog)

**Pour les modèles de scoring détaillés et des modèles d'exemple** : voir [references/scoring-models.md](references/scoring-models.md)

---

## Lead routing

### Méthodes de routing

| Méthode | Comment ça marche | Idéal pour |
|---------|-------------------|------------|
| **Round-robin** | Distribuer équitablement entre les commerciaux | Territoires égaux, tailles de deals similaires |
| **Par territoire** | Assigner par géographie, vertical ou segment | Équipes régionales, spécialistes sectoriels |
| **Par compte** | Les comptes nommés vont à des commerciaux nommés | Stratégies ABM, comptes stratégiques |
| **Par compétence** | Router par complexité du deal, gamme de produits ou langue | Gammes de produits variées, équipes globales |

### Essentiels des règles de routing

- Router vers la **correspondance la plus spécifique** d'abord, puis se rabattre sur le général
- Inclure un **propriétaire de repli** — les leads non assignés refroidissent vite et gaspillent du pipeline
- Le round-robin doit tenir compte de la **capacité et disponibilité des commerciaux** (congés, atteinte de quota)
- Logger chaque décision de routing pour l'audit et l'optimisation

### Speed-to-lead

Le délai de réponse est le facteur le plus important de conversion des leads :
- Contact sous **5 minutes** = 21x plus de chances de qualifier (Lead Connect)
- Après **30 minutes**, la conversion chute de 10x
- Après **24 heures**, le lead est de fait froid

Construisez des règles de routing qui priorisent la rapidité. Alertez les commerciaux immédiatement. Escaladez si le SLA est manqué.

**Pour les arbres de décision de routing et le setup par plateforme** : voir [references/routing-rules.md](references/routing-rules.md)

---

## Gestion des étapes du pipeline

### Étapes du pipeline

| Étape | Champs requis | Critères de sortie |
|-------|---------------|--------------------|
| **Qualifié** | Coordonnées, entreprise, source, score de fit | Appel de découverte planifié |
| **Découverte** | Points de douleur, solution actuelle, timeline | Besoins confirmés, démo planifiée |
| **Démo/Évaluation** | Exigences techniques, décideurs | Évaluation positive, proposition demandée |
| **Proposition** | Tarifs, conditions, cartographie des parties prenantes | Proposition livrée et revue |
| **Négociation** | Annotations, chaîne d'approbation, date de closing | Conditions agréées, contrat envoyé |
| **Closed Won** | Contrat signé, conditions de paiement | Handoff vers le CS terminé |
| **Closed Lost** | Raison de la perte, concurrent (le cas échéant) | Post-mortem loggé |

### Hygiène des étapes

- **Champs requis par étape** — Ne laissez pas les commerciaux faire avancer un deal sans remplir les données requises
- **Alertes de deals stagnants** — Signalez les deals qui restent dans une étape au-delà du temps moyen (ex : 2x les jours moyens)
- **Détection de saut d'étape** — Alertez quand des deals sautent des étapes (Qualifié → Proposition en sautant la Découverte)
- **Discipline des dates de closing** — Les reports de date doivent inclure une raison ; pas de report silencieux

### Métriques du pipeline

| Métrique | Ce que ça vous dit |
|----------|--------------------|
| Taux de conversion par étape | Où les deals meurent |
| Temps moyen dans l'étape | Où les deals stagnent |
| Vélocité du pipeline | Revenu par jour à travers le funnel |
| Ratio de couverture | Valeur du pipeline vs quota (cible 3-4x) |
| Win rate par source | Quels canaux produisent du vrai revenu |

---

## Workflows d'automatisation CRM

### Automatisations essentielles

- **Mises à jour d'étape de cycle de vie** — Faire avancer automatiquement les étapes quand les critères sont atteints
- **Création de tâche au handoff** — Créer une tâche de relance quand un MQL est assigné à un commercial
- **Alertes SLA** — Notifier le manager si un commercial manque le SLA de délai de réponse
- **Déclencheurs d'étape de deal** — Envoyer auto les propositions, mettre à jour les prévisions, notifier le CS au closing

### Automatisations marketing-vers-ventes

- **Alerte MQL** — Notification instantanée au commercial assigné avec le contexte du lead
- **Réunion réservée** — Notifier l'AE quand un prospect réserve via l'outil de scheduling
- **Digest d'activité des leads** — Résumé quotidien des actions à forte intention des leads actifs
- **Déclencheur de réengagement** — Alerter les ventes quand un lead dormant revient sur le site

### Intégration du scheduling calendrier

- **Scheduling round-robin** — Distribuer les réunions équitablement dans l'équipe
- **Routing par critères** — Envoyer les leads enterprise aux AE seniors, les SMB aux commerciaux juniors
- **Enrichment pré-réunion** — Pré-remplir l'enregistrement CRM avant l'appel
- **Workflows de no-show** — Relance auto si le prospect manque la réunion

**Pour les recettes de workflow par plateforme** : voir [references/automation-playbooks.md](references/automation-playbooks.md)

---

## Processus de deal desk

### Quand vous avez besoin d'un deal desk

- ACV au-dessus de **25 000 €** (ou votre seuil pour les deals non standards)
- Conditions de paiement non standards (net-90, facturation trimestrielle)
- Contrats pluriannuels avec pricing personnalisé
- Remises de volume au-delà des paliers publiés
- Conditions légales ou SLA personnalisés

### Paliers de workflow d'approbation

| Taille du deal | Approbation requise |
|----------------|---------------------|
| Pricing standard | Auto-approuvé |
| Remise 10-20% | Manager des ventes |
| Remise 20-40% | VP Sales |
| Remise 40%+ ou conditions personnalisées | Revue deal desk |
| Pluriannuel / enterprise | Finance + Juridique |

### Gestion des conditions non standards

Documentez chaque exception. Suivez quelles conditions non standards sont les plus demandées — si tout le monde demande la même exception, elle devrait devenir standard. Revoyez chaque trimestre.

---

## Hygiène et enrichment des données

### Stratégie de déduplication

- **Règles de matching** — Domaine email + nom d'entreprise + téléphone comme clés de matching principales
- **Priorité de fusion** — L'enregistrement CRM l'emporte sur le marketing automation ; l'activité la plus récente l'emporte pour les champs
- **Dédup planifiée** — Lancer une dédup automatique hebdomadaire avec revue manuelle pour les cas limites

### Application des champs requis

- Imposer les champs requis à chaque étape du cycle de vie
- Bloquer l'avancement d'étape si les champs sont vides
- Utiliser le progressive profiling — ne pas tout exiger d'emblée

### Outils d'enrichment

| Outil | Force |
|-------|-------|
| Clearbit | Enrichment en temps réel, bon pour les entreprises tech |
| Apollo | Données de contact + séquences, fort pour la prospection |
| ZoomInfo | Qualité enterprise, plus grande base de données B2B |

### Checklist d'audit trimestriel

- Revoir et fusionner les doublons
- Valider la délivrabilité email sur les contacts inactifs
- Archiver les contacts sans activité depuis 12+ mois
- Auditer la distribution des étapes du cycle de vie (chercher les goulots d'étranglement)
- Vérifier l'exactitude des données d'enrichment sur un échantillon

---

## Tableau de bord des métriques RevOps

### Métriques clés

| Métrique | Formule / Définition | Benchmark |
|----------|----------------------|-----------|
| Taux Lead-vers-MQL | MQL / Total des leads | 5-15% |
| Taux MQL-vers-SQL | SQL / MQL | 30-50% |
| SQL-vers-Opportunité | Opportunités / SQL | 50-70% |
| Vélocité du pipeline | (nb deals x taille moy. deal x win rate) / cycle de vente moy. | Varie selon l'ACV |
| CAC | Total dépense ventes + marketing / nouveaux clients | LTV:CAC > 3:1 |
| Ratio LTV:CAC | Lifetime value client / CAC | 3:1 à 5:1 sain |
| Speed-to-lead | Temps du remplissage de formulaire au premier contact commercial | < 5 minutes idéal |
| Win rate | Closed-won / total des opportunités | 20-30% (varie) |

### Structure du tableau de bord

Construire trois vues :
1. **Vue marketing** — Volume de leads, taux MQL, attribution par source, coût par MQL
2. **Vue ventes** — Valeur du pipeline, conversion par étape, vélocité, précision des prévisions
3. **Vue dirigeants** — CAC, LTV:CAC, revenu vs cible, couverture du pipeline

---

## Format de sortie

Quand vous livrez des recommandations RevOps, fournir :

1. **Document d'étapes de cycle de vie** — Définitions d'étapes avec critères d'entrée/sortie, propriétaires et SLA
2. **Spécification de scoring** — Attributs de fit et d'engagement avec valeurs en points et seuil MQL
3. **Document de règles de routing** — Arbre de décision avec logique d'assignation et replis
4. **Configuration du pipeline** — Définitions d'étapes, champs requis et déclencheurs d'automatisation
5. **Spec de tableau de bord de métriques** — Métriques clés, sources de données et benchmarks cibles

Formatez chacun comme un document autonome que l'utilisateur peut implémenter directement. Incluez un guide spécifique à la plateforme quand le CRM est connu.

---

## Questions spécifiques à la tâche

1. Quelle plateforme CRM utilisez-vous (ou prévoyez d'utiliser) ?
2. Combien de leads par mois générez-vous ?
3. Quelle est votre définition actuelle d'un MQL ?
4. Où les leads restent-ils coincés dans votre funnel ?
5. Avez-vous des SLA entre marketing et ventes aujourd'hui ?

---

## Intégrations d'outils

Pour l'implémentation, voir le [registre des outils](../../tools/REGISTRY.md). Outils RevOps clés :

| Outil | Ce que ça fait | Guide |
|-------|----------------|-------|
| **HubSpot** | CRM, marketing automation, lead scoring, workflows | [hubspot.md](../../tools/integrations/hubspot.md) |
| **Salesforce** | CRM enterprise, gestion de pipeline, reporting | [salesforce.md](../../tools/integrations/salesforce.md) |
| **Calendly** | Scheduling de réunions, routing round-robin | [calendly.md](../../tools/integrations/calendly.md) |
| **SavvyCal** | Scheduling avec disponibilité basée sur la priorité | [savvycal.md](../../tools/integrations/savvycal.md) |
| **Clearbit** | Enrichment et scoring de leads en temps réel | [clearbit.md](../../tools/integrations/clearbit.md) |
| **Apollo** | Données de contact, enrichment et séquences outbound | [apollo.md](../../tools/integrations/apollo.md) |
| **ActiveCampaign** | Marketing automation pour PME, lead scoring | [activecampaign.md](../../tools/integrations/activecampaign.md) |
| **Zapier** | Automatisation cross-outil et liant de workflow | [zapier.md](../../tools/integrations/zapier.md) |
| **Introw** | Pipeline d'origine partenaire, commissions, deal registration, QBR | [introw.md](../../tools/integrations/introw.md) |
| **Crossbeam** | Recoupements de comptes partenaires et identification de co-sell | [crossbeam.md](../../tools/integrations/crossbeam.md) |

---

## Skills liés

- **cold-email** : pour les emails de prospection outbound
- **emails** : pour les flux d'emails de cycle de vie et de nurture
- **pricing** : pour les décisions de pricing et le packaging
- **analytics** : pour le suivi des métriques de pipeline et l'attribution
- **launch** : pour la planification de lancement go-to-market
- **sales-enablement** : pour les supports de vente, decks et traitement des objections
