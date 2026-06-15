---
name: churn-prevention
description: "Quand l'utilisateur veut réduire le churn, construire des cancel flows, mettre en place des save offers, récupérer des paiements échoués ou implémenter des stratégies de rétention. Aussi quand il mentionne « churn », « cancel flow », « flow d'annulation », « offboarding », « save offer », « offre de rétention », « dunning », « relance de paiement », « failed payment recovery », « win-back », « rétention », « retention », « exit survey », « sondage de sortie », « mettre l'abonnement en pause », « pause subscription », « churn involontaire », « involuntary churn », « les gens n'arrêtent pas d'annuler », « mon taux de churn est trop élevé », « comment retenir mes utilisateurs » ou « mes clients partent ». À utiliser dès que quelqu'un perd des abonnés ou veut bâtir des systèmes pour l'éviter. Pour les séquences email de win-back post-annulation, voir emails. Pour les paywalls d'upgrade in-app, voir paywalls."
metadata:
  version: 2.0.0
---

# Churn Prevention

Tu es un expert de la rétention SaaS et de la prévention du churn. Ton objectif : aider à réduire à la fois le churn volontaire (clients qui choisissent d'annuler) et le churn involontaire (paiements échoués) grâce à des cancel flows bien conçus, des save offers dynamiques, une rétention proactive et des stratégies de dunning.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

### 1. Situation de churn actuelle
- Quel est votre taux de churn mensuel ? (volontaire vs. involontaire si connu)
- Combien d'abonnés actifs ?
- Quel est le MRR moyen par client ?
- Avez-vous un cancel flow aujourd'hui, ou l'annulation est-elle instantanée ?

### 2. Facturation & plateforme
- Quel prestataire de facturation ? (Stripe, Chargebee, Paddle, Recurly, Braintree)
- Intervalles de facturation mensuels, annuels, ou les deux ?
- Gérez-vous la mise en pause des plans ou les downgrades ?
- Un outillage de rétention existant ? (Churnkey, ProsperStack, Raaft)

### 3. Données produit & usage
- Suivez-vous l'usage des fonctionnalités par utilisateur ?
- Pouvez-vous identifier les baisses d'engagement ?
- Disposez-vous de données sur les raisons d'annulation issues des churns passés ?
- Quelle est votre métrique d'activation ? (Que font les utilisateurs retenus que les churnés ne font pas ?)

### 4. Contraintes
- B2B ou B2C ? (Influe sur la conception du flow)
- Annulation self-serve obligatoire ? (Certaines réglementations imposent une annulation facile)
- Ton de marque pour l'offboarding ? (Empathique, direct, joueur)

---

## Comment fonctionne ce skill

Le churn a deux types qui nécessitent des stratégies différentes :

| Type | Cause | Solution |
|------|-------|----------|
| **Volontaire** | Le client choisit d'annuler | Cancel flows, save offers, exit surveys |
| **Involontaire** | Le paiement échoue | Emails de dunning, smart retries, card updaters |

Le churn volontaire représente typiquement 50-70 % du churn total. Le churn involontaire représente 30-50 % mais est souvent plus facile à corriger.

Ce skill prend en charge trois modes :

1. **Construire un cancel flow** — concevoir de zéro avec sondage, save offers et confirmation
2. **Optimiser un flow existant** — analyser les données d'annulation et améliorer les taux de sauvegarde
3. **Mettre en place le dunning** — récupération des paiements échoués avec retries et séquences email

---

## Conception du cancel flow

### La structure du cancel flow

Tout cancel flow suit cette séquence :

```
Déclencheur → Sondage → Offre dynamique → Confirmation → Post-annulation
```

**Étape 1 : déclencheur**
Le client clique sur « Annuler l'abonnement » dans les paramètres du compte.

**Étape 2 : exit survey**
Demander pourquoi il annule. Cela détermine quelle save offer afficher.

**Étape 3 : save offer dynamique**
Présenter une offre ciblée en fonction de sa raison (remise, pause, downgrade, etc.)

**Étape 4 : confirmation**
S'il veut toujours annuler, confirmer clairement avec un message de fin de période de facturation.

**Étape 5 : post-annulation**
Poser les attentes, offrir un chemin de réactivation facile, déclencher une séquence de win-back.

### Conception de l'exit survey

L'exit survey est le fondement. Bonnes catégories de raisons :

| Raison | Ce que ça vous dit |
|--------|-------------------|
| Trop cher | Sensibilité au prix, peut répondre à une remise ou un downgrade |
| Pas assez utilisé | Faible engagement, peut répondre à une pause ou de l'aide à l'onboarding |
| Fonctionnalité manquante | Manque produit, montrer la roadmap ou un contournement |
| Passe à un concurrent | Pression concurrentielle, comprendre ce qu'il propose |
| Problèmes techniques / bugs | Qualité produit, escalader au support |
| Besoin temporaire / saisonnier | Pattern d'usage, proposer une pause |
| Entreprise fermée / changée | Inévitable, en tirer des leçons et lâcher prise élégamment |
| Autre | Fourre-tout, inclure un champ texte libre |

**Bonnes pratiques de sondage :**
- 1 question, choix unique avec texte libre optionnel
- 5-8 options de raison maximum (éviter la fatigue de décision)
- Mettre les raisons les plus fréquentes en premier (revoir les données chaque trimestre)
- Ne pas donner l'impression d'une culpabilisation
- Le cadrage « Aidez-nous à nous améliorer » fonctionne mieux que « Pourquoi partez-vous ? »

### Save offers dynamiques

L'insight clé : **faire coller l'offre à la raison.** Une remise ne sauvera pas quelqu'un qui n'utilise pas le produit. Une roadmap de fonctionnalités ne sauvera pas quelqu'un qui n'en a pas les moyens.

**Mapping offre-raison :**

| Raison d'annulation | Offre principale | Offre de repli |
|---------------|---------------|----------------|
| Trop cher | Remise (20-30 % pendant 2-3 mois) | Downgrade vers un plan inférieur |
| Pas assez utilisé | Pause (1-3 mois) | Session d'onboarding gratuite |
| Fonctionnalité manquante | Aperçu roadmap + timeline | Guide de contournement |
| Passe à un concurrent | Comparaison concurrentielle + remise | Session de feedback |
| Problèmes techniques | Escalader au support immédiatement | Crédit + correctif prioritaire |
| Temporaire / saisonnier | Mettre l'abonnement en pause | Downgrade temporaire |
| Entreprise fermée | Sauter l'offre (respecter la situation) | — |

### Types de save offers

**Remise**
- 20-30 % de remise pendant 2-3 mois est le point idéal
- Éviter les remises de 50 %+ (ça habitue les clients à annuler pour obtenir des deals)
- Limiter l'offre dans le temps (« Cette offre expire quand vous quittez cette page »)
- Montrer le montant économisé en euros, pas seulement le pourcentage

**Mettre l'abonnement en pause**
- Pause de 1-3 mois maximum (les pauses plus longues réactivent rarement)
- 60-80 % de ceux qui mettent en pause finissent par revenir en actif
- Réactivation automatique avec un email d'avis préalable
- Garder leurs données et réglages intacts

**Downgrade de plan**
- Proposer un palier inférieur au lieu d'une annulation complète
- Montrer ce qu'ils gardent vs. ce qu'ils perdent
- Positionner comme « ajustez votre plan » et non « downgrade »
- Chemin facile pour remonter quand ils sont prêts

**Déblocage / extension de fonctionnalité**
- Débloquer une fonctionnalité premium qu'ils n'ont pas essayée
- Prolonger le trial d'un palier supérieur
- Fonctionne mieux pour les raisons « pas assez de valeur »

**Contact personnel**
- Pour les comptes à forte valeur (top 10-20 % par MRR)
- Router vers le customer success pour un appel
- Email personnel du fondateur pour les petites entreprises

### Patterns d'UI de cancel flow

```
┌─────────────────────────────────────┐
│  Désolés de vous voir partir        │
│                                     │
│  Quelle est la raison principale    │
│  de votre annulation ?              │
│                                     │
│  ○ Trop cher                        │
│  ○ Pas assez utilisé                │
│  ○ Une fonctionnalité me manque     │
│  ○ Je passe à un autre outil        │
│  ○ Problèmes techniques             │
│  ○ Temporaire / pas besoin là       │
│  ○ Autre : [____________]           │
│                                     │
│  [Continuer]                        │
│  [Laisser tomber, garder mon abo]   │
└─────────────────────────────────────┘
         ↓ (sélectionne « Trop cher »)
┌─────────────────────────────────────┐
│  Et si on pouvait vous aider ?      │
│                                     │
│  On adorerait vous garder. Voici    │
│  une offre spéciale :               │
│                                     │
│  ┌───────────────────────────────┐  │
│  │  25 % de remise sur 3 mois    │  │
│  │  Économisez XX €/mois         │  │
│  │                               │  │
│  │  [Accepter l'offre]           │  │
│  └───────────────────────────────┘  │
│                                     │
│  Ou passez au [Plan Basic] à        │
│  X €/mois →                         │
│                                     │
│  [Non merci, continuer l'annulation]│
└─────────────────────────────────────┘
```

**Principes d'UI :**
- Garder l'option « continuer l'annulation » visible (pas de dark patterns)
- Une offre principale + une de repli, pas un mur d'options
- Montrer des économies précises en euros, pas des pourcentages abstraits
- Utiliser le nom du client et les données du compte quand c'est possible
- Adapté au mobile (beaucoup d'annulations se font sur mobile)

Pour des patterns de cancel flow détaillés par secteur et prestataire de facturation, voir [references/cancel-flow-patterns.md](references/cancel-flow-patterns.md).

---

## Prédiction du churn & rétention proactive

La meilleure sauvegarde se produit avant que le client ne clique sur « Annuler ».

### Signaux de risque

Suivre ces indicateurs avancés de churn :

| Signal | Niveau de risque | Délai |
|--------|-----------|-----------|
| La fréquence de connexion chute de 50 %+ | Élevé | 2-4 semaines avant l'annulation |
| L'usage d'une fonctionnalité clé s'arrête | Élevé | 1-3 semaines avant l'annulation |
| Pic de tickets de support puis arrêt | Élevé | 1-2 semaines avant l'annulation |
| Les taux d'ouverture email déclinent | Moyen | 2-6 semaines avant l'annulation |
| Les visites de la page de facturation augmentent | Élevé | Quelques jours avant l'annulation |
| Des sièges d'équipe sont retirés | Élevé | 1-2 semaines avant l'annulation |
| Un export de données est lancé | Critique | Quelques jours avant l'annulation |
| Le score NPS descend sous 6 | Moyen | 1-3 mois avant l'annulation |

### Modèle de health score

Construire un health score simple (0-100) à partir de signaux pondérés :

```
Health Score = (
  Score de fréquence de connexion × 0.30 +
  Score d'usage des fonctionnalités × 0.25 +
  Sentiment du support             × 0.15 +
  Santé de la facturation          × 0.15 +
  Score d'engagement               × 0.15
)
```

| Score | Statut | Action |
|-------|--------|--------|
| 80-100 | Sain | Opportunités d'upsell |
| 60-79 | À surveiller | Check-in proactif |
| 40-59 | À risque | Campagne d'intervention |
| 0-39 | Critique | Contact personnel |

### Interventions proactives

**Avant qu'ils ne pensent à annuler :**

| Déclencheur | Intervention |
|---------|-------------|
| Baisse d'usage >50 % pendant 2 semaines | Email « On a remarqué que vous n'avez pas utilisé [fonctionnalité]. Besoin d'aide ? » |
| Approche de la limite du plan | Nudge d'upgrade (pas un mur — paywalls gère ça) |
| Pas de connexion depuis 14 jours | Email de réengagement avec les dernières nouveautés produit |
| Détracteur NPS (0-6) | Suivi personnel dans les 24 heures |
| Ticket de support non résolu >48h | Escalade + mise à jour proactive du statut |
| Renouvellement annuel dans 30 jours | Email de récap de valeur + confirmation de renouvellement |

---

## Churn involontaire : récupération des paiements

Les paiements échoués causent 30-50 % du churn total mais sont les plus récupérables.

### La stack de dunning

```
Pré-dunning → Smart retry → Emails de dunning → Période de grâce → Annulation ferme
```

### Pré-dunning (prévenir les échecs)

- **Alertes d'expiration de carte** : email 30, 15 et 7 jours avant l'expiration de la carte
- **Moyen de paiement de secours** : proposer un second moyen de paiement à l'inscription
- **Services de card updater** : programmes de mise à jour automatique Visa/Mastercard (réduit les hard declines de 30-50 %)
- **Notification de pré-facturation** : email 3-5 jours avant le prélèvement pour les plans annuels

### Logique de smart retry

Tous les échecs ne se valent pas. Stratégie de retry par type de refus :

| Type de refus | Exemples | Stratégie de retry |
|-------------|----------|----------------|
| Soft decline (temporaire) | Fonds insuffisants, timeout du processeur | Retry 3-5 fois sur 7-10 jours |
| Hard decline (permanent) | Carte volée, compte fermé | Pas de retry — demander une nouvelle carte |
| Authentification requise | 3D Secure, SCA | Envoyer le client mettre à jour le paiement |

**Bonnes pratiques de timing des retries :**
- Retry 1 : 24 heures après l'échec
- Retry 2 : 3 jours après l'échec
- Retry 3 : 5 jours après l'échec
- Retry 4 : 7 jours après l'échec (avec escalade de l'email de dunning)
- Après 4 retries : annulation ferme avec chemin de réactivation

**Astuce smart retry :** réessayer le jour du mois où le paiement a initialement réussi (si le 1er a marché avant, réessayer le 1er). Les Smart Retries de Stripe gèrent ça automatiquement.

### Séquence d'emails de dunning

| Email | Timing | Ton | Contenu |
|-------|--------|------|---------|
| 1 | Jour 0 (échec) | Alerte amicale | « Votre paiement n'est pas passé. Mettez à jour votre carte. » |
| 2 | Jour 3 | Rappel utile | « Petit rappel — mettez à jour votre paiement pour garder l'accès. » |
| 3 | Jour 7 | Urgence | « Votre compte sera mis en pause dans 3 jours. Mettez à jour maintenant. » |
| 4 | Jour 10 | Dernier avertissement | « Dernière chance de garder votre compte actif. » |

**Bonnes pratiques d'email de dunning :**
- Lien direct vers la page de mise à jour du paiement (sans login si possible)
- Montrer ce qu'ils vont perdre (leurs données, l'accès de leur équipe)
- Ne pas blâmer (« votre paiement a échoué » et non « vous n'avez pas payé »)
- Inclure un contact support pour de l'aide
- Le texte brut performe mieux que les emails designés pour le dunning

### Benchmarks de récupération

| Métrique | Faible | Moyen | Bon |
|--------|------|---------|------|
| Récupération soft decline | <40 % | 50-60 % | 70 %+ |
| Récupération hard decline | <10 % | 20-30 % | 40 %+ |
| Récupération globale des paiements | <30 % | 40-50 % | 60 %+ |
| Prévention pré-dunning | Aucune | 10-15 % | 20-30 % |

Pour le playbook de dunning complet avec un setup spécifique par prestataire, voir [references/dunning-playbook.md](references/dunning-playbook.md).

---

## Métriques & mesure

### Métriques de churn clés

| Métrique | Formule | Cible |
|--------|---------|--------|
| Taux de churn mensuel | Clients churnés / Clients en début de mois | <5 % B2C, <2 % B2B |
| Revenue churn (net) | (MRR perdu - MRR d'expansion) / MRR de départ | Négatif (net expansion) |
| Taux de sauvegarde du cancel flow | Sauvés / Total des sessions d'annulation | 25-35 % |
| Taux d'acceptation des offres | Offres acceptées / Offres affichées | 15-25 % |
| Taux de réactivation après pause | Réactivés / Total mis en pause | 60-80 % |
| Taux de récupération dunning | Récupérés / Total des paiements échoués | 50-60 % |
| Délai jusqu'à l'annulation | Jours du premier signal de churn à l'annulation | Suivre la tendance |

### Analyse de cohortes

Segmenter le churn par :
- **Canal d'acquisition** — quels canaux amènent les clients les plus fidèles ?
- **Type de plan** — quels plans churnent le plus ?
- **Ancienneté** — quand la plupart des annulations se produisent-elles ? (30, 60, 90 jours ?)
- **Raison d'annulation** — quelles raisons sont en hausse ?
- **Type de save offer** — quelles offres marchent le mieux pour quels segments ?

### A/B tests de cancel flow

Tester une variable à la fois :

| Test | Hypothèse | Métrique |
|------|-----------|--------|
| % de remise (20 % vs 30 %) | Une remise plus forte sauve plus | Taux de sauvegarde, impact LTV |
| Durée de pause (1 vs 3 mois) | Une pause plus longue augmente le taux de retour | Taux de réactivation |
| Placement du sondage (avant vs après l'offre) | Le sondage en premier personnalise les offres | Taux de sauvegarde |
| Présentation de l'offre (modale vs pleine page) | La pleine page attire plus l'attention | Taux de sauvegarde |
| Ton du copy (empathique vs direct) | L'empathie réduit la friction | Taux de sauvegarde |

**Comment mener des expériences de cancel flow :** utiliser le skill **ab-testing** pour concevoir des tests statistiquement rigoureux. PostHog est bien adapté aux expériences de cancel flow — ses feature flags peuvent répartir les utilisateurs dans différents flows côté serveur, et ses funnel analytics suivent chaque étape du cancel flow (sondage → offre → accepter/refuser → confirmer). Voir le [guide d'intégration PostHog](../../tools/integrations/posthog.md) pour le setup.

---

## Erreurs courantes

- **Pas de cancel flow du tout** — l'annulation instantanée laisse de l'argent sur la table. Même un simple sondage + une offre sauve 10-15 %
- **Rendre l'annulation difficile à trouver** — des boutons d'annulation cachés génèrent du ressentiment et de mauvais avis. De nombreuses juridictions exigent une annulation facile (règle Click-to-Cancel de la FTC)
- **La même offre pour chaque raison** — une remise générale ne traite pas « fonctionnalité manquante » ou « pas d'usage »
- **Remises trop profondes** — les remises de 50 %+ habituent les clients à annuler-et-revenir pour les deals
- **Ignorer le churn involontaire** — souvent 30-50 % du churn total et le plus facile à corriger
- **Pas d'emails de dunning** — laisser les échecs de paiement annuler silencieusement les comptes
- **Copy culpabilisant** — « Vous êtes sûr de vouloir nous abandonner ? » abîme la confiance dans la marque
- **Ne pas suivre la LTV des save offers** — un client « sauvé » qui churne 30 jours plus tard n'était pas vraiment sauvé
- **Mettre en pause trop longtemps** — les pauses au-delà de 3 mois réactivent rarement. Fixer des limites.
- **Pas de chemin post-annulation** — rendre la réactivation facile et déclencher des emails de win-back, car certains utilisateurs churnés voudront revenir

---

## Intégrations d'outils

Pour l'implémentation, voir le [registre des outils](../../tools/REGISTRY.md).

### Plateformes de rétention

| Outil | Idéal pour | Fonctionnalité clé |
|------|----------|-------------|
| **Churnkey** | Cancel flow complet + dunning | Offres adaptatives pilotées par IA, taux de sauvegarde moyen de 34 % |
| **ProsperStack** | Cancel flows avec analytics | Moteur de règles avancé, intégration Stripe/Chargebee |
| **Raaft** | Constructeur de cancel flow simple | Setup facile, bon pour les early-stage |
| **Chargebee Retention** | Clients Chargebee | Intégration native, anciennement Brightback |

### Prestataires de facturation (dunning)

| Prestataire | Smart Retries | Emails de dunning | Card Updater |
|----------|:------------:|:--------------:|:------------:|
| **Stripe** | Intégré (Smart Retries) | Intégré | Automatique |
| **Chargebee** | Intégré | Intégré | Via la gateway |
| **Paddle** | Intégré | Intégré | Géré |
| **Recurly** | Intégré | Intégré | Intégré |
| **Braintree** | Config manuelle | Manuel | Via la gateway |

### Outils CLI liés

| Outil | À utiliser pour |
|------|---------|
| `stripe` | Gestion d'abonnements, config dunning, retries de paiement |
| `customer-io` | Séquences d'emails de dunning, campagnes de rétention |
| `posthog` | A/B tests de cancel flow via feature flags, funnel analytics |
| `mixpanel` / `ga4` | Tracking d'usage, analyse des signaux de churn |
| `segment` | Routage d'événements pour le health scoring |

---

## Skills liés

- **emails** : pour les séquences d'emails de win-back après annulation
- **paywalls** : pour les moments d'upgrade in-app et l'expiration du trial
- **pricing** : pour la structure des plans et la stratégie de remise annuelle
- **onboarding** : pour l'activation afin de prévenir le churn précoce
- **analytics** : pour mettre en place les événements de signaux de churn
- **ab-testing** : pour tester les variations de cancel flow avec rigueur statistique
