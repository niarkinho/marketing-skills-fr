# Définitions des étapes de cycle de vie

Modèles complets pour les étapes de cycle de vie des leads, critères MQL par type d'activité, SLA, et workflows de rejet/recyclage.

## Modèles d'étapes

### Subscriber

**Critères d'entrée :**
- Opt-in au blog, à la newsletter ou aux mises à jour de contenu
- Aucune information entreprise requise

**Critères de sortie :**
- Fournit des informations entreprise via formulaire ou enrichment
- Visite 3+ pages dans une session
- Télécharge du contenu gated

**Propriétaire :** Marketing (automatisé)

**Actions à l'entrée :**
- Ajouter au nurture newsletter
- Commencer à suivre le score d'engagement

---

### Lead

**Critères d'entrée :**
- Contact identifié avec nom + email + entreprise
- Peut provenir d'un remplissage de formulaire, d'enrichment ou d'import

**Critères de sortie :**
- Atteint le seuil MQL (fit + engagement)
- Qualifié manuellement par le marketing/SDR

**Propriétaire :** Marketing

**Actions à l'entrée :**
- Enrichir les données de contact (taille d'entreprise, secteur, rôle)
- Commencer le scoring
- Ajouter à la séquence de nurture pertinente

---

### MQL (Marketing Qualified Lead)

**Critères d'entrée :**
- Atteint le seuil de score de fit ET le seuil de score d'engagement
- OU déclenche une action à forte intention (demande de démo, page de pricing + remplissage de formulaire)

**Critères de sortie :**
- Les ventes acceptent (devient SQL)
- Les ventes rejettent (recyclé en nurture avec code de raison)
- Aucune réponse dans le SLA (escaladé au manager)

**Propriétaire :** Marketing → Ventes (handoff)

**Actions à l'entrée :**
- Alerte instantanée au commercial assigné
- Créer une tâche de relance avec SLA de 4 heures
- Mettre en pause les séquences de nurture marketing
- Logger toute l'activité récente pour le contexte des ventes

---

### SQL (Sales Qualified Lead)

**Critères d'entrée :**
- Le commercial a eu une conversation de qualification
- Confirmé : budget, autorité, besoin ou timeline (au moins 2 sur 4)

**Critères de sortie :**
- Opportunité créée avec valeur projetée
- Disqualifié (recyclé avec code de raison)

**Propriétaire :** Ventes (SDR ou AE)

**Actions à l'entrée :**
- Mettre à jour l'étape de cycle de vie dans le CRM
- Notifier l'AE si qualifié par le SDR
- Commencer la séquence de vente si pas déjà en conversation

---

### Opportunité

**Critères d'entrée :**
- Opportunité formelle créée dans le CRM
- Valeur du deal, date de closing et étape assignées

**Critères de sortie :**
- Closed-won ou closed-lost

**Propriétaire :** Ventes (AE)

**Actions à l'entrée :**
- Ajouter au reporting du pipeline
- Créer les tâches du deal (proposition, démo, etc.)
- Notifier le CS si le deal est susceptible de se conclure

---

### Client

**Critères d'entrée :**
- Deal closed-won
- Contrat signé et conditions de paiement fixées

**Critères de sortie :**
- Churn, s'étend ou renouvelle

**Propriétaire :** Customer Success / Account Management

**Actions à l'entrée :**
- Déclencher la séquence d'onboarding
- Assigner un manager CS
- Planifier l'appel de kickoff
- Retirer de toutes les séquences de vente

---

### Évangéliste

**Critères d'entrée :**
- Score NPS 9-10, ou comportement de référence actif
- A accepté un cas client, un témoignage ou un programme de référence

**Critères de sortie :**
- Participation continue au programme

**Propriétaire :** Customer Success + Marketing

**Actions à l'entrée :**
- Ajouter au programme d'advocacy
- Demander un cas client ou un témoignage
- Inviter au programme de référence
- Mettre en avant dans les campagnes marketing (avec permission)

---

## Modèles de critères MQL par type d'activité

### PLG (Product-Led Growth)

**Score de fit (pondération 40%) :**

| Attribut | Points |
|----------|--------|
| Taille d'entreprise 10-500 | +15 |
| Taille d'entreprise 500-5000 | +20 |
| Secteur cible | +10 |
| Rôle décideur | +15 |
| Utilise un outil complémentaire | +10 |

**Score d'engagement (pondération 60%) — pondérer fortement l'usage produit :**

| Signal | Points |
|--------|--------|
| A créé un compte gratuit | +15 |
| A complété l'onboarding | +20 |
| A utilisé une feature cœur 3+ fois | +25 |
| A invité un membre d'équipe | +20 |
| A atteint la limite d'usage | +15 |
| A visité la page de pricing | +10 |

**Seuil MQL :** 65 points

---

### Sales-Led (Enterprise)

**Score de fit (pondération 60%) — pondérer fortement le fit :**

| Attribut | Points |
|----------|--------|
| Taille d'entreprise 500+ | +20 |
| Secteur cible | +15 |
| Titre VP+ | +20 |
| Autorité budgétaire confirmée | +15 |
| Utilise un produit concurrent | +10 |

**Score d'engagement (pondération 40%) :**

| Signal | Points |
|--------|--------|
| A demandé une démo | +25 |
| A assisté à un webinaire | +10 |
| A téléchargé un livre blanc | +10 |
| A visité la page de pricing 2+ fois | +15 |
| A engagé avec un email de vente | +10 |

**Seuil MQL :** 70 points

---

### Mid-Market (Équilibré)

**Score de fit (pondération 50%) :**

| Attribut | Points |
|----------|--------|
| Taille d'entreprise 50-1000 | +15 |
| Secteur cible | +10 |
| Titre Manager+ | +15 |
| Géographie cible | +10 |

**Score d'engagement (pondération 50%) :**

| Signal | Points |
|--------|--------|
| Demande de démo | +25 |
| Inscription à un free trial | +20 |
| Visite de la page de pricing | +10 |
| Téléchargement de contenu (2+) | +10 |
| Clic email (3+) | +10 |
| Présence à un webinaire | +10 |

**Seuil MQL :** 60 points

---

## Modèles de SLA

### SLA MQL-vers-SQL

| Métrique | Cible | Escalade |
|----------|-------|----------|
| Première tentative de contact | Sous 4 heures ouvrées | Alerte au manager des ventes à 4 heures |
| Décision de qualification | Sous 48 heures | Auto-escalade à 48 heures |
| Réunion planifiée (si qualifié) | Sous 5 jours ouvrés | Signalement à la revue hebdomadaire du pipeline |

### SLA SQL-vers-Opportunité

| Métrique | Cible | Escalade |
|----------|-------|----------|
| Appel de découverte effectué | Sous 3 jours ouvrés après le SQL | Alerte au manager AE |
| Opportunité créée | Sous 5 jours ouvrés après le SQL | Signalement à la revue du pipeline |

### SLA Opportunité-vers-Closing

| Métrique | Cible | Escalade |
|----------|-------|----------|
| Proposition livrée | Sous 5 jours ouvrés après la démo | Alerte au manager AE |
| Deal stagnant dans l'étape | 2x les jours moyens pour cette étape | Signalement à la revue du pipeline |
| Date de closing reportée 2+ fois | Immédiat | Revue de prévision requise |

---

## Rejet et recyclage des leads

### Codes de raison de rejet

| Code | Raison | Action de recyclage |
|------|--------|---------------------|
| **FIT-01** | Entreprise trop petite | Nurture ; re-scorer si l'entreprise grandit |
| **FIT-02** | Mauvais secteur | Archiver ; ne pas recycler |
| **FIT-03** | Mauvais rôle / pas d'autorité | Nurture ; surveiller les changements d'organisation |
| **ENG-01** | Pas de réponse après 3 tentatives | Recycler en nurture sous 90 jours |
| **ENG-02** | Intéressé mais mauvais timing | Recycler en nurture ; réengager sous 60 jours |
| **QUAL-01** | Pas de budget | Recycler en nurture sous 90 jours |
| **QUAL-02** | Utilise un concurrent, verrouillé | Recycler ; déclencher avant le renouvellement de contrat |
| **QUAL-03** | Pas un vrai projet | Archiver ; ne pas recycler |

### Workflow de recyclage

1. Les ventes rejettent le MQL avec un code de raison
2. Le CRM met à jour l'étape de cycle de vie à « Recyclé »
3. Le lead entre dans la séquence de nurture de recyclage (différente du nurture original)
4. Le score d'engagement se réinitialise à la baseline (conserver le score de fit)
5. Si le lead se réengage et franchit le seuil MQL, le re-router vers les ventes avec le flag « Recycled MQL »
6. Suivre le taux de conversion des MQL recyclés séparément

### Séquence de nurture de recyclage

- **Fréquence :** Bimensuelle ou mensuelle (fréquence plus basse que le nurture initial)
- **Contenu :** Insights sectoriels, cas clients, mises à jour produit
- **Durée :** 6 mois, puis archiver si pas d'engagement
- **Déclencheur de re-MQL :** Action à forte intention (demande de démo, revisite de la page de pricing)
