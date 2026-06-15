# Playbook de dunning

Guide complet pour récupérer les paiements échoués et réduire le churn involontaire.

---

## Pourquoi le dunning est important

- Les paiements échoués causent 30-50 % de tout le churn d'abonnement
- La plupart des paiements échoués sont récupérables avec la bonne stratégie
- Les entreprises d'abonnement perdent environ 129 milliards de dollars par an à cause du churn involontaire
- Un dunning efficace récupère 50-60 % des paiements échoués

---

## La timeline de dunning

```
Jour -30 à -7 : Pré-dunning (prévenir les échecs)
Jour 0 :        Le paiement échoue → Smart retry #1 + Email #1
Jour 1-3 :      Smart retry #2 + Email #2
Jour 3-5 :      Smart retry #3
Jour 5-7 :      Smart retry #4 + Email #3
Jour 7-10 :     Retry final + Email #4 (dernier avertissement)
Jour 10-14 :    Fin de la période de grâce → Compte mis en pause/annulé
Jour 14+ :      Démarrage de la séquence de win-back
```

---

## Pré-dunning : prévenir les échecs avant qu'ils n'arrivent

### Gestion de l'expiration des cartes

| Timing | Action |
|--------|--------|
| 30 jours avant l'expiration | Email : « Votre carte se terminant par 4242 expire le mois prochain » |
| 15 jours avant l'expiration | Email : « Mettez à jour votre moyen de paiement pour éviter une interruption » |
| 7 jours avant l'expiration | Email : « Votre carte expire dans 7 jours — mettez à jour maintenant » |
| 3 jours avant l'expiration | Bannière in-app : « Moyen de paiement bientôt expiré » |

**Template d'email — Carte qui expire :**
```
Objet : Votre carte se terminant par 4242 expire bientôt

Bonjour [Prénom],

La carte enregistrée pour votre abonnement [Produit] expire le [date].

Mettez à jour votre moyen de paiement maintenant pour éviter toute interruption :

[Mettre à jour le moyen de paiement →]

Ça prend moins de 30 secondes.

— L'équipe [Produit]
```

### Services de card updater

Les grands réseaux de cartes proposent des programmes de mise à jour automatique :

| Service | Réseau | Ce qu'il fait |
|---------|---------|--------------|
| Visa Account Updater (VAU) | Visa | Met à jour automatiquement les numéros de carte et dates d'expiration stockés |
| Mastercard Automatic Billing Updater (ABU) | Mastercard | Idem pour Mastercard |
| Amex Cardrefresher | American Express | Idem pour Amex |

**Impact :** réduit les hard declines dus aux cartes expirées/remplacées de 30-50 %.

**Comment l'activer :**
- **Stripe** : automatique — activé par défaut
- **Chargebee** : activé via les paramètres de la gateway
- **Recurly** : intégré, activé par défaut
- **Braintree** : contacter le processeur pour l'activer

### Moyens de paiement de secours

Proposer un second moyen de paiement :
- Pendant l'inscription : « Ajoutez un moyen de paiement de secours » (faible conversion)
- Après le premier paiement réussi : « Protégez votre compte avec une carte de secours » (meilleur timing)
- Après la récupération d'un paiement échoué : « Ajoutez une carte de secours pour éviter de futures interruptions » (meilleur timing — ils ont ressenti la douleur)

### Notifications de pré-facturation

Pour les plans annuels ou les abonnements à forte valeur :
- Email 7 jours avant le renouvellement avec le montant et la date
- Inclure un lien pour mettre à jour le moyen de paiement
- Montrer ce qui est inclus dans le renouvellement
- Exigé par certaines réglementations pour les renouvellements automatiques

---

## Stratégie de smart retry

### Classification des types de refus

| Code | Type | Signification | Retry ? |
|------|------|---------|--------|
| `insufficient_funds` | Soft | Solde temporairement faible | Oui — retry dans 2-3 jours |
| `card_declined` (générique) | Soft | Diverses raisons temporaires | Oui — retry 3-4 fois |
| `processing_error` | Soft | Problème gateway/réseau | Oui — retry dans les 24h |
| `expired_card` | Hard | La carte est expirée | Non — demander une nouvelle carte |
| `stolen_card` | Hard | Carte déclarée volée | Non — demander une nouvelle carte |
| `do_not_honor` | Soft/Hard | Banque a refusé (ambigu) | Réessayer une fois, puis demander une nouvelle carte |
| `authentication_required` | Auth | SCA/3DS nécessaire | Envoyer le client s'authentifier |

### Calendrier de retry par prestataire

**Stripe (Smart Retries — recommandé) :**
- Activer « Smart Retries » dans Stripe Dashboard → Billing → Settings
- Le modèle ML de Stripe choisit le timing de retry optimal d'après des milliards de transactions
- Typiquement 4-8 tentatives de retry sur 3-4 semaines
- Récupère ~15 % de plus que les retries à calendrier fixe

**Calendrier de retry manuel (sans smart retries) :**

| Retry | Timing | Meilleur jour/heure |
|-------|--------|--------------|
| 1 | Jour 1 (24h après l'échec) | Matin, même jour de la semaine que l'original |
| 2 | Jour 3 | Essayer un autre moment de la journée |
| 3 | Jour 5 | Après un jour de paie typique (1er, 15) |
| 4 | Jour 7 | Matin du jour ouvré suivant |
| 5 (final) | Jour 10 | Dernière tentative avant la fin de la période de grâce |

**Insights sur le timing des retries :**
- Réessayer le jour du mois où le paiement original a réussi
- Réessayer après les jours de paie courants (1er et 15 du mois)
- Éviter de réessayer le week-end (taux d'approbation plus faibles)
- Les retries du matin (8h-10h heure locale) performent légèrement mieux

---

## Séquence d'emails de dunning

### Email 1 : Paiement échoué (Jour 0)

**Ton :** amical, factuel. Pas d'alarme.

```
Objet : Action requise — votre paiement n'est pas passé

Bonjour [Prénom],

Nous avons tenté de débiter votre [type de carte] se terminant par [4 derniers]
pour votre abonnement [Produit] ([montant] €), mais ça n'est pas passé.

Ça arrive parfois — une simple mise à jour de carte règle généralement le problème.

[Mettre à jour le moyen de paiement →]

Votre accès n'est pas encore affecté. Nous réessaierons automatiquement,
mais mettre à jour votre carte est le moyen le plus rapide.

Besoin d'aide ? Répondez simplement à cet email.

— L'équipe [Produit]
```

### Email 2 : Rappel (Jour 3)

**Ton :** utile, légèrement plus urgent.

```
Objet : Petit rappel — mettez à jour votre paiement pour [Produit]

Bonjour [Prénom],

Juste un mot — nous n'avons toujours pas pu traiter votre paiement de
[montant] € pour [Produit].

[Mettre à jour le moyen de paiement →]

Ça prend moins de 30 secondes. Vos [données/projets/accès équipe]
sont en sécurité, mais nous aurons besoin d'un moyen de paiement valide
pour garder votre compte actif.

Des questions ? Répondez ici et on vous aidera.

— L'équipe [Produit]
```

### Email 3 : Urgence (Jour 7)

**Ton :** direct, conséquences claires.

```
Objet : Votre compte [Produit] sera mis en pause dans 3 jours

Bonjour [Prénom],

Nous avons tenté de traiter votre paiement plusieurs fois, mais votre
[type de carte] se terminant par [4 derniers] continue d'être refusée.

Si nous ne recevons pas le paiement d'ici le [date], votre compte sera
mis en pause et vous perdrez l'accès à :

• [Fonctionnalité/donnée clé qu'ils utilisent]
• [Leurs projets/workspace]
• [Accès équipe pour X membres]

[Mettre à jour le moyen de paiement maintenant →]

Vos données ne seront pas supprimées — vous pouvez réactiver à tout moment
en mettant à jour votre moyen de paiement.

— L'équipe [Produit]
```

### Email 4 : Dernier avertissement (Jour 10)

**Ton :** final, clair, sans culpabilisation.

```
Objet : Dernière chance de garder votre compte [Produit] actif

Bonjour [Prénom],

Ceci est notre dernier rappel. Votre paiement de [montant] € est en retard,
et votre compte sera mis en pause demain ([date]).

[Mettre à jour le moyen de paiement →]

Après la mise en pause :
• Vos données sont conservées pendant [90 jours]
• Vous pouvez réactiver à tout moment
• Mettez simplement à jour votre carte pour rétablir l'accès

Si vous comptiez annuler, aucune action nécessaire — votre compte
sera mis en pause automatiquement.

— L'équipe [Produit]
```

---

## Gestion de la période de grâce

### Ce qui se passe pendant la période de grâce

| Réglage | Recommandation |
|---------|---------------|
| Durée | 7-14 jours après le retry final |
| Accès | Dégradé (lecture seule) ou accès complet |
| Visibilité | Bannière in-app : « Paiement en retard — mettez à jour pour continuer » |
| Retry | Continuer les retries en arrière-plan pendant la grâce |
| Communication | Les emails de dunning continuent |

### Options de dégradation de l'accès

**Option A : accès complet pendant la grâce (recommandé pour le B2B)**
- Friction plus faible, le client se sent respecté
- Taux de récupération plus élevé (ils voient toujours la valeur)
- Risque : certains clients exploitent la période de grâce

**Option B : accès en lecture seule (recommandé pour le B2C)**
- Peuvent consulter mais pas créer/éditer
- Crée de l'urgence sans la peur de la perte de données
- Message clair : « Mettez à jour le paiement pour rétablir l'accès complet »

**Option C : verrouillage immédiat (non recommandé)**
- Agressif, abîme la relation
- Taux de récupération plus faible
- Approprié seulement pour les plans à très bas coût

### Après la période de grâce

| Timing | Action |
|--------|--------|
| Fin de la période de grâce | Mettre le compte en pause (pas le supprimer) |
| Jour 1 post-pause | Email « Votre compte a été mis en pause » |
| Jour 7 post-pause | Rappel « Vos données sont toujours là » |
| Jour 30 post-pause | Tentative de win-back avec une nouvelle offre |
| Jour 60 post-pause | Win-back final |
| Jour 90 post-pause | Avertissement de suppression des données (le cas échéant) |

---

## Setup spécifique par prestataire

### Stripe

**Activer les Smart Retries :**
1. Dashboard → Settings → Billing → Subscriptions and emails
2. Activer « Smart Retries » sous les règles de retry
3. Définir les emails de paiement échoué dans Dashboard → Settings → Emails

**Règles de retry personnalisées (si pas de Smart Retries) :**
```
Retry 1 : 3 jours après l'échec
Retry 2 : 5 jours après l'échec
Retry 3 : 7 jours après l'échec
Final :   Marquer l'abonnement comme impayé après le dernier retry
```

**Événements webhook à gérer :**
- `invoice.payment_failed` — déclencher le dunning
- `invoice.paid` — annuler le dunning, rétablir l'accès
- `customer.subscription.updated` — changements de statut
- `customer.subscription.deleted` — annulation finale

### Chargebee

**Dunning intégré :**
1. Settings → Configure Chargebee → Retry Settings
2. Configurer les tentatives de retry et les intervalles
3. Settings → Configure Chargebee → Email Notifications → Dunning

**Options de dunning :**
- Retries automatiques avec calendrier configurable
- Emails de dunning intégrés (templates personnalisables)
- Configuration de la période de grâce par plan

### Paddle

**Dunning géré :**
- Paddle gère les retries et le dunning automatiquement
- Personnalisation limitée (Paddle gère la relation)
- Webhook : `subscription.payment_failed`, `subscription.cancelled`
- Idéal pour une approche sans intervention

### Recurly

**Revenue Recovery :**
1. Configuration → Dunning Management
2. Définir le calendrier de retry par plan
3. Configurer la période de grâce et l'action finale (pause vs annulation)

**Fonctionnalités avancées :**
- Optimisation des retries par machine learning
- Calendriers de dunning par plan
- Account Updater intégré

---

## Dunning in-app

Ne pas se reposer uniquement sur l'email. Afficher les échecs de paiement dans l'app :

### Pattern de bannière
```
┌──────────────────────────────────────────────────────┐
│ ⚠ Votre paiement de 29 € a échoué. Mettez à jour     │
│ votre carte pour éviter de perdre l'accès.           │
│ [Mettre à jour →]  [Ignorer]                         │
└──────────────────────────────────────────────────────┘
```

**Règles :**
- Afficher à chaque chargement de page pendant la période de dunning
- Autoriser l'ignorance (mais réafficher à la session suivante)
- Lien direct vers la mise à jour du paiement (le moins de clics possible)
- Ne pas bloquer le produit — les laisser continuer à l'utiliser

### Pattern de modale (pour le dernier avertissement)
```
┌─────────────────────────────────────┐
│                                     │
│  Votre compte sera mis en pause     │
│  le [date]                          │
│                                     │
│  Mettez à jour votre moyen de       │
│  paiement pour garder l'accès à     │
│  vos [X] projets et [Y] membres     │
│  d'équipe.                          │
│                                     │
│  [Mettre à jour le moyen de paiement]│
│  [Me rappeler plus tard]            │
│                                     │
└─────────────────────────────────────┘
```

---

## Mesurer la performance du dunning

### Métriques clés

| Métrique | Comment calculer | Cible |
|--------|-----------------|--------|
| Taux de récupération | Paiements récupérés / Total échoués | 50-60 % |
| Taux de récupération par type de refus | Récupérés / Échoués par type | Soft : 70 %+, Hard : 40 %+ |
| Délai de récupération | Jours de l'échec au paiement réussi | <5 jours |
| Taux de prévention pré-dunning | Échecs évités / Échecs attendus | 20-30 % |
| Taux d'ouverture des emails de dunning | Ouvertures / Envoyés par email | 60 %+ |
| Taux de clic des emails de dunning | Clics / Ouvertures par email | 30 %+ |
| Revenu récupéré (mensuel) | Somme des montants de paiements récupérés | Suivre la tendance |
| Revenu perdu au churn involontaire | Somme des montants échoués + non récupérés | Suivre la tendance |

### Benchmarking

**Par stade de l'entreprise :**

| Stade | Churn involontaire typique | Cible après optimisation |
|-------|--------------------------|--------------------------|
| Early (< 1 M€ ARR) | 3-5 % du MRR/mois | 1-2 % |
| Growth (1-10 M€ ARR) | 2-4 % du MRR/mois | 0,5-1,5 % |
| Scale (10 M€+ ARR) | 1-3 % du MRR/mois | 0,3-0,8 % |

### Calcul du ROI

```
MRR mensuel de paiements échoués :   10 000 €
Taux de récupération actuel :         30 % (3 000 € récupérés)
Taux de récupération cible :          60 % (6 000 € récupérés)
Amélioration mensuelle :              3 000 €/mois
Amélioration annuelle :               36 000 €/an
Coût de l'optimisation dunning :      ~200-500 €/mois (outillage)
ROI :                                 6-15x
```
