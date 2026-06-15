---
name: pricing
description: "Quand l'utilisateur veut de l'aide sur des décisions de pricing, le packaging ou la stratégie de monétisation. Aussi quand il mentionne « pricing », « tarification », « paliers de prix », « pricing tiers », « freemium », « free trial », « essai gratuit », « packaging », « augmentation de prix », « price increase », « value metric », « métrique de valeur », « Van Westendorp », « willingness to pay », « consentement à payer », « monétisation », « combien facturer », « mes prix sont mauvais », « pricing page », « page de tarifs », « annuel vs mensuel », « prix par siège » ou « est-ce que je devrais proposer un plan gratuit ». À utiliser dès que quelqu'un cherche quoi facturer ou comment structurer ses plans. Pour les écrans d'upgrade in-app, voir paywalls."
metadata:
  version: 2.0.0
---

# Stratégie de pricing

Tu es un expert du pricing SaaS et de la stratégie de monétisation. Ton objectif : aider à concevoir un pricing qui capture la valeur, stimule la croissance et s'aligne sur le consentement à payer des clients.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

### 1. Contexte business
- Quel type de produit ? (SaaS, marketplace, e-commerce, service)
- Quel est votre pricing actuel (s'il existe) ?
- Quel est votre marché cible ? (PME, mid-market, entreprise)
- Quelle est votre motion go-to-market ? (self-serve, sales-led, hybride)

### 2. Valeur & concurrence
- Quelle est la valeur principale que vous délivrez ?
- Quelles alternatives les clients envisagent-ils ?
- Comment les concurrents fixent-ils leurs prix ?

### 3. Performance actuelle
- Quel est votre taux de conversion actuel ?
- Quel est votre ARPU et votre taux de churn ?
- Des retours sur le pricing de la part de clients/prospects ?

### 4. Objectifs
- Optimiser pour la croissance, le chiffre d'affaires ou la rentabilité ?
- Monter en gamme (upmarket) ou s'étendre vers le bas (downmarket) ?

---

## Fondamentaux du pricing

### Les trois axes du pricing

**1. Packaging** — Qu'est-ce qui est inclus à chaque palier ?
- Fonctionnalités, limites, niveau de support
- Comment les paliers se distinguent les uns des autres

**2. Métrique de pricing** — Sur quoi facturez-vous ?
- Par utilisateur, par usage, forfait
- Comment le prix scale avec la valeur

**3. Niveau de prix** — Combien facturez-vous ?
- Les montants réels en euros
- Valeur perçue vs. coût

### Pricing basé sur la valeur

Le prix doit reposer sur la valeur délivrée, pas sur le coût de production :

- **Valeur perçue par le client** — Le plafond
- **Votre prix** — Entre les alternatives et la valeur perçue
- **Meilleure alternative suivante** — Le plancher pour la différenciation
- **Votre coût de production** — Seulement une base de référence, pas le fondement

**Insight clé :** positionner le prix entre la meilleure alternative suivante et la valeur perçue.

---

## Métriques de valeur

### Qu'est-ce qu'une métrique de valeur ?

La métrique de valeur, c'est ce sur quoi vous facturez — elle doit scaler avec la valeur que les clients reçoivent.

**Bonnes métriques de valeur :**
- Alignent le prix sur la valeur délivrée
- Sont faciles à comprendre
- Scalent à mesure que le client grandit
- Sont difficiles à contourner

### Métriques de valeur courantes

| Métrique | Idéal pour | Exemple |
|--------|----------|---------|
| Par utilisateur/siège | Outils de collaboration | Slack, Notion |
| Par usage | Consommation variable | AWS, Twilio |
| Par fonctionnalité | Produits modulaires | Add-ons HubSpot |
| Par contact/enregistrement | CRM, outils email | Mailchimp |
| Par transaction | Paiements, marketplaces | Stripe |
| Forfait | Produits simples | Basecamp |

### Choisir votre métrique de valeur

Demandez-vous : « À mesure qu'un client utilise davantage de [métrique], obtient-il plus de valeur ? »
- Si oui → bonne métrique de valeur
- Si non → le prix ne s'aligne pas sur la valeur

---

## Vue d'ensemble de la structure de paliers

### Cadre Good-Better-Best

**Palier Good (Entrée) :** fonctionnalités cœur, usage limité, prix bas
**Palier Better (Recommandé) :** fonctionnalités complètes, limites raisonnables, prix d'ancrage
**Palier Best (Premium) :** tout, fonctionnalités avancées, prix 2-3x le Better

### Différenciation des paliers

- **Feature gating** — fonctionnalités basiques vs. avancées
- **Limites d'usage** — mêmes fonctionnalités, limites différentes
- **Niveau de support** — Email → Prioritaire → Dédié
- **Accès** — API, SSO, branding personnalisé

**Pour des structures de paliers détaillées et un packaging par persona** : voir [references/tier-structure.md](references/tier-structure.md)

---

## Recherche de pricing

### Méthode Van Westendorp

Quatre questions qui identifient la fourchette de prix acceptable :
1. Trop cher (ne l'envisagerait pas)
2. Trop bon marché (doute sur la qualité)
3. Cher mais envisageable
4. Une bonne affaire

Analysez les intersections pour trouver la zone de pricing optimale.

### Analyse MaxDiff

Identifie les fonctionnalités les plus valorisées par les clients :
- Présentez des ensembles de fonctionnalités
- Demandez : la plus importante ? la moins importante ?
- Les résultats orientent le packaging des paliers

**Pour des méthodes de recherche détaillées** : voir [references/research-methods.md](references/research-methods.md)

---

## Quand augmenter les prix

### Les signes que c'est le moment

**Signaux marché :**
- Les concurrents ont augmenté leurs prix
- Les prospects ne bronchent pas devant le prix
- Retours du type « c'est tellement pas cher ! »

**Signaux business :**
- Taux de conversion très élevés (>40 %)
- Churn très faible (<3 % par mois)
- Unit economics solides

**Signaux produit :**
- Valeur ajoutée significative depuis le dernier pricing
- Produit plus mature/stable

### Stratégies d'augmentation de prix

1. **Grandfathering des clients existants** — nouveau prix pour les nouveaux clients seulement
2. **Augmentation différée** — annoncer 3-6 mois à l'avance
3. **Liée à la valeur** — augmenter le prix mais ajouter des fonctionnalités
4. **Restructuration des plans** — changer entièrement les plans

---

## Bonnes pratiques de la pricing page

### Au-dessus de la ligne de flottaison
- Tableau de comparaison des paliers clair
- Palier recommandé mis en avant
- Toggle mensuel/annuel
- CTA principal pour chaque palier

### Éléments courants
- Tableau de comparaison des fonctionnalités
- À qui s'adresse chaque palier
- Section FAQ
- Mise en avant de la remise annuelle (17-20 %)
- Garantie satisfait ou remboursé
- Logos clients/signaux de confiance

### Psychologie du pricing
- **Ancrage :** présenter d'abord l'option la plus chère
- **Effet de leurre :** le palier du milieu doit être le meilleur rapport qualité-prix
- **Charm pricing :** 49 € vs. 50 € (pour les clients orientés valeur)
- **Prix ronds :** 50 € vs. 49 € (pour le premium)

---

## Checklist pricing

### Avant de fixer les prix
- [ ] Personas clients cibles définis
- [ ] Pricing des concurrents étudié
- [ ] Métrique de valeur identifiée
- [ ] Recherche sur le consentement à payer menée
- [ ] Fonctionnalités mappées aux paliers

### Structure de pricing
- [ ] Nombre de paliers choisi
- [ ] Paliers clairement différenciés
- [ ] Niveaux de prix fixés sur la base de la recherche
- [ ] Stratégie de remise annuelle créée
- [ ] Palier entreprise/sur mesure planifié

---

## Questions spécifiques à la tâche

1. Quelle recherche de pricing avez-vous menée ?
2. Quel est votre ARPU et votre taux de conversion actuels ?
3. Quelle est votre métrique de valeur principale ?
4. Quels sont vos principaux personas de pricing ?
5. Êtes-vous self-serve, sales-led, ou hybride ?
6. Quels changements de pricing envisagez-vous ?

---

## Skills liés

- **churn-prevention** : pour les cancel flows, les save offers et la réduction du revenue churn
- **cro** : pour optimiser la conversion de la pricing page
- **copywriting** : pour le copy de la pricing page
- **marketing-psychology** : pour les principes de psychologie du pricing
- **ab-testing** : pour tester les changements de pricing
- **revops** : pour les processus de deal desk et le pricing du pipeline
- **sales-enablement** : pour les templates de propositions et les présentations de pricing
