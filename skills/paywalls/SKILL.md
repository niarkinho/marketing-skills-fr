---
name: paywalls
description: À utiliser quand l'utilisateur veut créer ou optimiser des paywalls in-app, des écrans d'upgrade, des modales d'upsell ou des feature gates. Aussi quand il mentionne « paywall », « écran d'upgrade », « modale d'upgrade », « upsell », « feature gate », « convertir le free en payant », « conversion freemium », « écran d'expiration de trial », « écran de limite atteinte », « invitation d'upgrade de plan », « tarification in-app », « les utilisateurs free ne passent pas en payant », « conversion trial vers payant » ou « comment faire payer les utilisateurs ». À utiliser pour tout moment in-product où vous demandez aux utilisateurs de passer en payant. Distinct des pages de pricing publiques (voir `cro`) — ce skill se concentre sur les moments d'upgrade in-product où l'utilisateur a déjà expérimenté la valeur. Pour les décisions de pricing, voir `pricing`.
metadata:
  version: 2.0.0
---

# CRO des paywalls et écrans d'upgrade

Vous êtes un expert des paywalls in-app et des flux d'upgrade. Votre objectif est de convertir les utilisateurs free en payants, ou de faire monter les utilisateurs vers des paliers supérieurs, aux moments où ils ont expérimenté assez de valeur pour justifier l'engagement.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Avant de fournir des recommandations, comprendre :

1. **Contexte d'upgrade** - Freemium → Payant ? Trial → Payant ? Montée de palier ? Upsell de fonctionnalité ? Limite d'usage ?

2. **Modèle produit** - Qu'est-ce qui est gratuit ? Qu'y a-t-il derrière le paywall ? Qu'est-ce qui déclenche les invitations ? Taux de conversion actuel ?

3. **Parcours utilisateur** - Quand cela apparaît-il ? Qu'ont-ils expérimenté ? Qu'essaient-ils de faire ?

---

## Principes fondamentaux

### 1. La valeur avant la demande
- L'utilisateur doit avoir expérimenté une vraie valeur d'abord
- L'upgrade doit sembler une suite naturelle
- Timing : après l'« aha moment », pas avant

### 2. Montrer, pas seulement dire
- Démontrez la valeur des fonctionnalités payantes
- Donnez un aperçu de ce qu'ils manquent
- Rendez l'upgrade tangible

### 3. Un chemin sans friction
- Facile à upgrader quand on est prêt
- Ne les faites pas chercher le pricing

### 4. Respecter le non
- Ne pas piéger ni mettre la pression
- Rendez facile de continuer en gratuit
- Maintenez la confiance pour une conversion future

---

## Points de déclenchement du paywall

### Feature gates
Quand l'utilisateur clique sur une fonctionnalité réservée au payant :
- Explication claire de pourquoi elle est payante
- Montrer ce que fait la fonctionnalité
- Chemin rapide vers le déblocage
- Option de continuer sans

### Limites d'usage
Quand l'utilisateur atteint une limite :
- Indication claire de la limite atteinte
- Montrer ce qu'apporte l'upgrade
- Ne pas bloquer brutalement

### Expiration du trial
Quand le trial touche à sa fin :
- Alertes précoces (7, 3, 1 jour)
- « Ce qui se passe » à l'expiration, clairement
- Résumer la valeur reçue

### Invitations basées sur le temps
Après X jours d'usage gratuit :
- Rappel d'upgrade en douceur
- Mettre en avant les fonctionnalités payantes inutilisées
- Facile à fermer

---

## Composants de l'écran de paywall

1. **Titre** - Se concentrer sur ce qu'ils obtiennent : « Débloquez [Fonctionnalité] pour [Bénéfice] »

2. **Démonstration de valeur** - Preview, avant/après, « Avec Pro vous pourriez... »

3. **Comparaison de fonctionnalités** - Mettre en avant les différences clés, plan actuel marqué

4. **Pricing** - Clair, simple, options annuel vs. mensuel

5. **Preuve sociale** - Citations clients, « X équipes utilisent ceci »

6. **CTA** - Spécifique et orienté valeur : « Commencez à obtenir [Bénéfice] »

7. **Porte de sortie** - « Pas maintenant » ou « Continuer en gratuit », clairement

---

## Types de paywall spécifiques

### Paywall de verrouillage de fonctionnalité
```
[Icône cadenas]
Cette fonctionnalité est disponible sur Pro

[Preview/capture de la fonctionnalité]

[Nom de la fonctionnalité] vous aide à [bénéfice] :
• [Capacité]
• [Capacité]

[Passer à Pro - X €/mois]
[Peut-être plus tard]
```

### Paywall de limite d'usage
```
Vous avez atteint votre limite gratuite

[Barre de progression à 100%]

Free : 3 projets | Pro : Illimité

[Passer à Pro]  [Supprimer un projet]
```

### Paywall d'expiration de trial
```
Votre trial se termine dans 3 jours

Ce que vous allez perdre :
• [Fonctionnalité utilisée]
• [Données créées]

Ce que vous avez accompli :
• Créé X projets

[Continuer avec Pro]
[Me le rappeler plus tard]  [Rétrograder]
```

---

## Timing et fréquence

### Quand montrer
- Après un moment de valeur, avant la frustration
- Après l'activation/aha moment
- Quand on atteint de vraies limites

### Quand NE PAS montrer
- Pendant l'onboarding (trop tôt)
- Quand ils sont en plein flow
- À répétition après un refus

### Règles de fréquence
- Limite par session
- Délai de récupération après refus (en jours, pas en heures)
- Suivre les signaux d'agacement

---

## Optimisation du flux d'upgrade

### Du paywall au paiement
- Minimiser les étapes
- Garder en contexte si possible
- Pré-remplir les informations connues

### Post-upgrade
- Accès immédiat aux fonctionnalités
- Confirmation et reçu
- Guide vers les nouvelles fonctionnalités

---

## A/B testing

### Quoi tester
- Timing du déclenchement
- Variations de titre/copy
- Présentation du prix
- Longueur du trial
- Mise en avant de fonctionnalités
- Design/layout

### Métriques à suivre
- Taux d'impression du paywall
- Click-through vers l'upgrade
- Taux de complétion
- Revenu par utilisateur
- Taux de churn post-upgrade

**Pour des idées d'expériences complètes** : voir [references/experiments.md](references/experiments.md)

---

## Anti-patterns à éviter

### Dark patterns
- Cacher le bouton de fermeture
- Sélection de plan confuse
- Copy culpabilisant

### Tueurs de conversion
- Demander avant que la valeur soit délivrée
- Invitations trop fréquentes
- Bloquer des flux critiques
- Processus d'upgrade compliqué

---

## Questions spécifiques à la tâche

1. Quel est votre taux de conversion free → payant actuel ?
2. Qu'est-ce qui déclenche les invitations d'upgrade aujourd'hui ?
3. Quelles fonctionnalités sont derrière le paywall ?
4. Quel est votre « aha moment » pour les utilisateurs ?
5. Quel modèle de pricing ? (par siège, à l'usage, forfait)
6. Appli mobile, web app, ou les deux ?

---

## Skills liés

- **churn-prevention** : pour les flux d'annulation, les offres de rétention et la réduction du churn post-upgrade
- **cro** : pour l'optimisation de la page de pricing publique
- **onboarding** : pour mener à l'aha moment avant l'upgrade
- **ab-testing** : pour tester les variations de paywall
