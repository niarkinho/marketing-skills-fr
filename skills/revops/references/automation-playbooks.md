# Playbooks d'automatisation

Recettes de workflow spécifiques aux plateformes pour HubSpot, Salesforce, outils de scheduling et automatisation cross-outil.

## Recettes de workflow HubSpot

### 1. Alerte et assignation MQL

**Nom :** Notification MQL et création de tâche
**Déclencheur :** La propriété de contact « Lifecycle Stage » passe à « Marketing Qualified Lead »
**Actions :**
1. Faire tourner le propriétaire du contact dans l'équipe commerciale (round-robin)
2. Envoyer une notification email interne au propriétaire du contact avec le contexte du lead
3. Créer une tâche : « Relancer [Nom du contact] » — échéance dans 4 heures
4. Envoyer une notification Slack au canal #sales-alerts
5. Inscrire dans la séquence « MQL Follow-Up » (si vous utilisez les Sequences HubSpot)
**Résultat :** Chaque MQL est assigné instantanément avec un SLA clair
**Notes :** Régler les critères d'inscription pour exclure les leads déjà détenus par un commercial

---

### 2. Escalade SLA MQL

**Nom :** Alerte de dépassement de SLA MQL
**Déclencheur :** La propriété de contact « Lifecycle Stage » égale « MQL » ET « Jours depuis le dernier contact » est supérieur à 0,5 (12 heures)
**Actions :**
1. Envoyer un email interne au propriétaire du contact : « Avertissement SLA : [Nom du contact] n'a pas été contacté »
2. Si toujours aucune activité après 24 heures → envoyer une alerte au manager des ventes
3. Si toujours aucune activité après 48 heures → réassigner le propriétaire du contact par rotation
4. Créer une tâche pour le nouveau propriétaire : « Urgent : contacter [Nom du contact] — réassigné pour dépassement de SLA »
**Résultat :** Aucun MQL ne reste non travaillé plus de 48 heures
**Notes :** Exclure les contacts dont le dernier type d'activité est « Appel » ou « Réunion » (déjà engagés)

---

### 3. Mise à jour du lead scoring et promotion MQL

**Nom :** Auto-MQL au seuil de score
**Déclencheur :** La propriété de contact « HubSpot Score » est supérieure ou égale à 65
**Actions :**
1. Régler l'étape de cycle de vie sur « Marketing Qualified Lead »
2. Régler « MQL Date » à la date du jour
3. Supprimer des workflows de nurture marketing
4. Déclencher le workflow d'alerte MQL (recette n°1)
**Résultat :** Les leads sont automatiquement promus en MQL quand ils atteignent le seuil de scoring
**Notes :** Ajouter une liste de suppression pour les clients existants et les concurrents

---

### 4. Notification de réunion réservée

**Nom :** Alerte de réunion réservée à l'AE
**Déclencheur :** Une activité de réunion est loggée pour le contact (via Calendly/HubSpot meetings)
**Actions :**
1. Envoyer un email interne au propriétaire du contact avec les détails de la réunion
2. Mettre à jour la propriété de contact « Last Meeting Booked » à la date du jour
3. Si l'étape de cycle de vie est « Lead » → passer à « MQL »
4. Créer une tâche : « Préparer la réunion avec [Nom du contact] » — échéance 1 heure avant la réunion
5. Envoyer une notification Slack au canal #meetings
**Résultat :** Les AE sont préparés pour chaque réunion avec le contexte complet
**Notes :** Inclure les visites de pages récentes et les téléchargements de contenu dans l'email de notification

---

### 5. Handoff Closed-Won vers le CS

**Nom :** Déclencheur d'onboarding client
**Déclencheur :** L'étape du deal passe à « Closed Won »
**Actions :**
1. Mettre à jour l'étape de cycle de vie du contact associé à « Client »
2. Régler la date « Customer Since » à la date du jour
3. Assigner le propriétaire du contact à un membre de l'équipe CS (selon segment/territoire)
4. Créer une tâche pour le CS : « Planifier l'appel de kickoff avec [Nom de l'entreprise] » — échéance dans 2 jours ouvrés
5. Inscrire le contact dans la séquence email « Customer Onboarding »
6. Envoyer une notification interne au manager CS
7. Retirer de toutes les séquences de vente
**Résultat :** Handoff fluide des ventes au customer success
**Notes :** Inclure les notes du deal, la valeur du contrat et les parties prenantes clés dans la notification CS

---

### 6. Alerte de deal stagnant

**Nom :** Hygiène du pipeline — Détection de deal stagnant
**Déclencheur :** La propriété de deal « Jours dans l'étape actuelle » est supérieure à [2x la moyenne pour cette étape]
**Actions :**
1. Envoyer un email interne au propriétaire du deal : « Alerte deal stagnant : [Nom du deal] est dans [Étape] depuis [X] jours »
2. Créer une tâche : « Mettre à jour ou clôturer [Nom du deal] » — échéance dans 3 jours ouvrés
3. Si aucune mise à jour après 7 jours → alerter le manager des ventes
4. Ajouter à la liste du tableau de bord « Deals stagnants »
**Résultat :** Le pipeline reste propre et la prévision reste précise
**Notes :** Personnaliser les seuils par étape (Découverte : 14 jours, Proposition : 10 jours, Négociation : 21 jours)

---

### 7. Réentrée en nurture des leads recyclés

**Nom :** Recyclage MQL vers nurture
**Déclencheur :** La propriété de contact « Sales Rejection Reason » est connue (n'importe quelle valeur)
**Actions :**
1. Mettre à jour l'étape de cycle de vie à « Recyclé »
2. Réinitialiser le score d'engagement à la baseline (conserver le score de fit)
3. Inscrire dans la séquence « Recycled Lead Nurture » (fréquence plus basse)
4. Régler « Recycle Date » à la date du jour
5. Régler le déclencheur de réinscription : si le HubSpot Score dépasse à nouveau le seuil, re-déclencher le workflow MQL
**Résultat :** Les leads rejetés obtiennent une seconde chance sans encombrer le pipeline
**Notes :** Suivre le taux de conversion recyclé-vers-MQL comme métrique séparée

---

### 8. Digest d'activité des leads

**Nom :** Résumé quotidien d'activité des leads
**Déclencheur :** Planifié — quotidien à 8h00 heure locale
**Actions :**
1. Filtrer les contacts : étape de cycle de vie « SQL » ou « Opportunité » ET activité sur le site dans les dernières 24 heures
2. Envoyer un email de digest à chaque propriétaire de contact avec l'activité de ses leads
3. Inclure : pages visitées, contenu téléchargé, emails ouverts/cliqués
**Résultat :** Les commerciaux commencent chaque journée en sachant quels leads sont actifs
**Notes :** Inclure uniquement les leads avec une activité significative (exclure les simples visites de page d'accueil)

---

## Équivalents Salesforce Flow

### 1. Alerte et assignation MQL (Salesforce Flow)

**Type :** Record-Triggered Flow
**Objet :** Lead
**Déclencheur :** Le champ Lead « Status » passe à « MQL »
**Étapes du flow :**
1. Get Records : Interroger l'objet personnalisé « Rep Assignment » pour le prochain commercial disponible
2. Update Records : Régler le Lead Owner sur le commercial assigné
3. Create Records : Créer une tâche — « Contacter MQL : {Lead.Name} » avec échéance = NOW + 4 heures
4. Action : Envoyer une alerte email au nouveau propriétaire du lead
5. Update Records : Mettre à jour le timestamp de dernière assignation de « Rep Assignment »
**Notes :** Utiliser un objet personnalisé « Rep Assignment » pour gérer l'état du round-robin

### 2. Escalade SLA (Salesforce Flow)

**Type :** Scheduled-Triggered Flow
**Planning :** Toutes les 4 heures pendant les heures ouvrées
**Étapes du flow :**
1. Get Records : Leads où Status = « MQL » ET LastActivityDate < TODAY - 1
2. Decision : Le lead a-t-il plus de 48 heures sans activité ?
   - OUI → Réassigner au commercial suivant, créer une tâche urgente, alerter le manager
   - NON → Envoyer un email de rappel au propriétaire actuel
**Notes :** Coupler avec Process Builder pour des alertes en temps réel sur l'assignation initiale

### 3. Automatisation des étapes du pipeline (Salesforce Flow)

**Type :** Record-Triggered Flow
**Objet :** Opportunity
**Déclencheur :** Le champ Stage est mis à jour
**Étapes du flow :**
1. Decision : Vers quelle étape a-t-il changé ?
2. Pour chaque étape :
   - **Découverte :** Créer une tâche « Compléter le questionnaire de découverte »
   - **Démo :** Créer une tâche « Préparer l'environnement de démo »
   - **Proposition :** Créer une tâche « Envoyer la proposition » + alerter le deal desk si ACV > 25 000 €
   - **Closed Won :** Déclencher le handoff CS (créer un Case, assigner un propriétaire CS, envoyer un email de bienvenue)
   - **Closed Lost :** Créer une tâche « Logger la raison de la perte » + ajouter au rapport d'analyse win/loss

### 4. Détection de deal stagnant (Salesforce Flow)

**Type :** Scheduled-Triggered Flow
**Planning :** Quotidien à 7h00
**Étapes du flow :**
1. Get Records : Opportunités ouvertes où Days_In_Stage > Stage_SLA_Threshold
2. Boucler sur les résultats :
   - Create Task : « Mettre à jour le deal stagnant : {Opportunity.Name} »
   - Envoyer un email à l'Opportunity Owner
   - Si Days_In_Stage > 2x le seuil → envoyer un email au Manager du propriétaire
3. Update : champ personnalisé « Stale Flag » = true pour la visibilité du tableau de bord

---

## Patterns d'intégration Calendly / SavvyCal

### Scheduling de réunions round-robin

**Setup Calendly :**
1. Créer un type d'event d'équipe avec tous les commerciaux éligibles
2. Distribution : « Optimiser pour une distribution égale »
3. Disponibilité : Chaque commercial gère son propre calendrier
4. Buffer : 15 min avant et après les réunions
5. Préavis minimum : 4 heures (éviter les réservations de dernière minute)

**Intégration CRM :**
1. Le webhook Calendly se déclenche à la réservation
2. Matcher l'email de l'invité au contact CRM
3. Si le contact existe → assigner la réunion au propriétaire du contact (outrepasser le round-robin si détenu)
4. Si nouveau contact → créer le lead, assigner via les règles de routing, logger la réunion
5. Régler l'étape de cycle de vie sur MQL (réunion = forte intention)

### Setup SavvyCal

**Avantages sur Calendly :**
- Scheduling basé sur la priorité (préférer certains créneaux)
- Superposition de calendriers (montrer la disponibilité de l'équipe dans une vue)
- Liens de réservation personnalisés par commercial

**Pattern d'intégration :**
1. Créer un lien de scheduling d'équipe avec des règles de priorité
2. Webhook à la réservation → Zapier/Make → CRM
3. Matcher ou créer le contact, assigner le propriétaire, créer une tâche
4. Envoyer une confirmation avec les supports de préparation de réunion

### Routing de réunion par critères

```
Formulaire de réservation soumis
├─ Taille d'entreprise > 500 ? (champ de formulaire)
│  ├─ OUI → Router vers le calendrier de l'AE enterprise
│  └─ NON ↓
├─ Client existant ? (lookup CRM)
│  ├─ OUI → Router vers le calendrier du propriétaire du compte
│  └─ NON ↓
└─ Round-robin dans l'équipe SDR
```

### Workflow de no-show

**Déclencheur :** L'heure de la réunion passe + aucune note de réunion loggée dans les 30 minutes
**Actions :**
1. Attendre 30 minutes après l'heure planifiée de la réunion
2. Vérifier : Un appel ou une réunion a-t-il été loggé ?
   - OUI → Aucune action
   - NON → Envoyer un email « Désolé de vous avoir manqué » au prospect
3. Créer une tâche : « Replanifier avec [Nom du contact] » — échéance le prochain jour ouvré
4. Si deuxième no-show → signaler le contact et alerter le manager

---

## Patterns cross-outil Zapier

### 1. Nouveau lead → CRM + Slack + Tâche

**Déclencheur :** Nouvelle soumission de formulaire (Typeform, HubSpot, Webflow)
**Actions :**
1. Créer/mettre à jour le contact dans le CRM
2. Enrichir avec Clearbit (si disponible)
3. Poster sur Slack #new-leads avec les données enrichies
4. Créer une tâche dans l'outil de gestion de projet (Asana, Linear)

### 2. Réunion réservée → CRM + Email de prép

**Déclencheur :** Nouvelle réservation Calendly/SavvyCal
**Actions :**
1. Trouver ou créer le contact CRM
2. Mettre à jour l'étape de cycle de vie à MQL
3. Envoyer un email de prép au commercial assigné (inclure lien CRM, profil LinkedIn, activité récente)
4. Créer une tâche pré-réunion

### 3. Deal clôturé → Stack d'onboarding

**Déclencheur :** L'étape du deal CRM passe à « Closed Won »
**Actions :**
1. Créer l'enregistrement client dans l'outil CS (Vitally, Gainsight, ChurnZero)
2. Ajouter au template de projet d'onboarding
3. Envoyer un email de bienvenue via l'outil d'email
4. Créer un canal Slack : #customer-[nom-entreprise]
5. Notifier l'équipe CS sur Slack

### 4. Lead scoring → Synchro cross-outil

**Déclencheur :** Le score de lead CRM franchit le seuil MQL
**Actions :**
1. Mettre à jour le statut de la plateforme de marketing automation
2. Ajouter à l'audience de retargeting (Facebook, Google Ads)
3. Déclencher la séquence d'outreach SDR
4. Logger l'event dans l'analytics (Mixpanel, Amplitude)

### 5. Dépassement de SLA → Alerte multi-canal

**Déclencheur :** Tâche CRM en retard (tâche de relance MQL)
**Actions :**
1. Envoyer un DM Slack au commercial
2. Envoyer un email au commercial
3. Si 2h+ de retard → DM Slack au manager
4. Si 4h+ de retard → réassigner dans le CRM (via webhook retour vers le CRM)

### 6. Digest hebdomadaire du pipeline

**Déclencheur :** Planifié — chaque lundi à 8h00
**Actions :**
1. Interroger le CRM pour le résumé du pipeline (valeur totale, nouveaux deals, deals stagnants, closings attendus)
2. Formater en résumé
3. Poster sur Slack #sales-team
4. Envoyer un digest email à la direction des ventes
