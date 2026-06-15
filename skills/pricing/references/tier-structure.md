# Structure de paliers et packaging

## Sommaire
- Combien de paliers ?
- Cadre Good-Better-Best
- Stratégies de différenciation des paliers
- Exemple de structure de paliers
- Packaging par persona (identifier les personas de pricing, packaging par persona)
- Freemium vs. free trial (quand utiliser le freemium, quand utiliser le free trial, approches hybrides)
- Pricing entreprise (quand ajouter un pricing sur mesure, éléments du palier entreprise, stratégies de pricing entreprise)

## Combien de paliers ?

**2 paliers :** choix simple et clair
- Fonctionne pour : un découpage net PME vs. entreprise
- Risque : peut laisser de l'argent sur la table

**3 paliers :** standard du secteur
- Palier Good = point d'entrée
- Palier Better = recommandé (ancrer vers le best)
- Palier Best = clients à forte valeur

**4+ paliers :** plus de granularité
- Fonctionne pour : une large gamme de tailles de clients
- Risque : paralysie de la décision, complexité

---

## Cadre Good-Better-Best

**Palier Good (Entrée) :**
- Objectif : lever les barrières à l'entrée
- Inclut : fonctionnalités cœur, usage limité
- Prix : bas, accessible
- Cible : petites équipes, essayer avant d'acheter

**Palier Better (Recommandé) :**
- Objectif : là où atterrissent la plupart des clients
- Inclut : fonctionnalités complètes, limites raisonnables
- Prix : votre prix d'« ancrage »
- Cible : équipes en croissance, utilisateurs sérieux

**Palier Best (Premium) :**
- Objectif : capturer les clients à forte valeur
- Inclut : tout, fonctionnalités avancées, limites supérieures
- Prix : premium (souvent 2-3x le « Better »)
- Cible : grandes équipes, power users, entreprises

---

## Stratégies de différenciation des paliers

**Feature gating :**
- Fonctionnalités basiques dans tous les paliers
- Fonctionnalités avancées dans les paliers supérieurs
- Fonctionne quand les fonctionnalités ont des différences de valeur claires

**Limites d'usage :**
- Mêmes fonctionnalités, limites différentes
- Plus d'utilisateurs, de stockage, d'appels API dans les paliers supérieurs
- Fonctionne quand la valeur scale avec l'usage

**Niveau de support :**
- Support email → Support prioritaire → Success dédié
- Fonctionne pour les produits à complexité d'implémentation

**Accès et personnalisation :**
- Accès API, SSO, branding personnalisé
- Fonctionne pour la différenciation entreprise

---

## Exemple de structure de paliers

```
┌────────────────┬─────────────────┬─────────────────┬─────────────────┐
│                │ Starter         │ Pro             │ Business        │
│                │ 29 €/mois       │ 79 €/mois       │ 199 €/mois      │
├────────────────┼─────────────────┼─────────────────┼─────────────────┤
│ Utilisateurs   │ Jusqu'à 5       │ Jusqu'à 20      │ Illimité        │
│ Projets        │ 10              │ Illimité        │ Illimité        │
│ Stockage       │ 5 Go            │ 50 Go           │ 500 Go          │
│ Intégrations   │ 3               │ 10              │ Illimité        │
│ Analytics      │ Basique         │ Avancé          │ Sur mesure      │
│ Support        │ Email           │ Prioritaire     │ Dédié           │
│ Accès API      │ ✗               │ ✓               │ ✓               │
│ SSO            │ ✗               │ ✗               │ ✓               │
│ Audit logs     │ ✗               │ ✗               │ ✓               │
└────────────────┴─────────────────┴─────────────────┴─────────────────┘
```

---

## Packaging par persona

### Identifier les personas de pricing

Les différents clients ont des différences de :
- Consentement à payer
- Besoins en fonctionnalités
- Processus d'achat
- Perception de la valeur

**Segmentez par :**
- Taille d'entreprise (solopreneur → PME → entreprise)
- Cas d'usage (marketing vs. ventes vs. support)
- Sophistication (débutant → power user)
- Secteur (normes de budget différentes)

### Packaging par persona

**Étape 1 : définir les personas**

| Persona | Taille | Besoins | WTP | Exemple |
|---------|------|-------|-----|---------|
| Freelance | 1 personne | Fonctionnalités basiques | Faible | 19 €/mois |
| Petite équipe | 2-10 | Collaboration | Moyen | 49 €/mois |
| Entreprise en croissance | 10-50 | Scale, intégrations | Plus élevé | 149 €/mois |
| Entreprise | 50+ | Sécurité, support | Élevé | Sur mesure |

**Étape 2 : mapper les fonctionnalités aux personas**

| Fonctionnalité | Freelance | Petite équipe | En croissance | Entreprise |
|---------|------------|------------|---------|------------|
| Fonctionnalités cœur | ✓ | ✓ | ✓ | ✓ |
| Collaboration | — | ✓ | ✓ | ✓ |
| Intégrations | — | Limitées | Complètes | Complètes |
| Accès API | — | — | ✓ | ✓ |
| SSO/SAML | — | — | — | ✓ |
| Audit logs | — | — | — | ✓ |
| Contrat sur mesure | — | — | — | ✓ |

**Étape 3 : pricer à la valeur pour chaque persona**
- Recherchez le consentement à payer par segment
- Fixez des prix qui capturent la valeur sans bloquer l'adoption
- Envisagez des landing pages spécifiques par segment

---

## Freemium vs. free trial

### Quand utiliser le freemium

**Le freemium fonctionne quand :**
- Le produit a des effets viraux/de réseau
- Les utilisateurs gratuits apportent de la valeur (contenu, données, referrals)
- Grand marché où le % de conversion crée du volume
- Faible coût marginal pour servir les utilisateurs gratuits
- Limites de fonctionnalités/usage claires comme déclencheur d'upgrade

**Risques du freemium :**
- Les utilisateurs gratuits peuvent ne jamais convertir
- Dévalorise la perception du produit
- Coûts de support pour des utilisateurs non payants
- Plus difficile d'augmenter les prix ensuite

### Quand utiliser le free trial

**Le free trial fonctionne quand :**
- Le produit a besoin de temps pour démontrer sa valeur
- Un investissement d'onboarding/setup est requis
- B2B avec des comités d'achat
- Niveaux de prix plus élevés
- Le produit est « sticky » une fois configuré

**Bonnes pratiques du trial :**
- 7-14 jours pour les produits simples
- 14-30 jours pour les produits complexes
- Accès complet (pas limité en fonctionnalités)
- Compte à rebours et rappels clairs
- Arbitrage carte bancaire optionnelle vs. obligatoire

**Carte bancaire d'emblée :**
- Meilleure conversion trial-to-paid (40-50 % vs. 15-25 %)
- Volume de trials plus faible
- Leads mieux qualifiés

### Approches hybrides

**Freemium + trial :**
- Palier gratuit avec fonctionnalités limitées
- Trial des fonctionnalités premium
- Exemple : Zoom (40 min gratuites, trial de Pro)

**Reverse trial :**
- Démarrer avec un accès complet
- Après le trial, downgrade vers le palier gratuit
- Exemple : voir la valeur premium, vivre avec les limitations jusqu'à être prêt

---

## Pricing entreprise

### Quand ajouter un pricing sur mesure

Ajoutez « Contacter le service commercial » quand :
- Les tailles de deal dépassent 10 k€+ ARR
- Les clients ont besoin de contrats sur mesure
- Une implémentation/un onboarding est requis
- Il y a des exigences de sécurité/conformité
- Des processus d'achat (procurement) sont impliqués

### Éléments du palier entreprise

**Incontournables :**
- SSO/SAML
- Audit logs
- Contrôles admin
- SLA de disponibilité
- Certifications de sécurité

**Valeurs ajoutées :**
- Support/success dédié
- Onboarding sur mesure
- Sessions de formation
- Intégrations sur mesure
- Influence prioritaire sur la roadmap

### Stratégies de pricing entreprise

**Par siège à grande échelle :**
- Remises sur volume pour les grandes équipes
- Exemple : 15 €/utilisateur (standard) → 10 €/utilisateur (100+)

**Frais de plateforme + usage :**
- Frais de base pour l'accès
- Basé sur l'usage au-delà de seuils
- Exemple : 500 €/mois de base + 0,01 € par appel API

**Contrats basés sur la valeur :**
- Prix lié au chiffre d'affaires/aux résultats du client
- Exemple : % des transactions, partage de revenu
```
