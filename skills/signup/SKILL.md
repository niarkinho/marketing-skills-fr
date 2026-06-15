---
name: signup
description: À utiliser quand l'utilisateur veut optimiser des flux d'inscription, d'enregistrement, de création de compte ou d'activation de trial. Aussi quand il mentionne « conversions d'inscription », « friction d'inscription », « optimisation du formulaire d'inscription », « inscription au free trial », « réduire l'abandon d'inscription », « flux de création de compte », « les gens ne s'inscrivent pas », « abandon d'inscription », « taux de conversion du trial », « personne ne termine l'inscription », « trop d'étapes pour s'inscrire » ou « simplifier notre inscription ». À utiliser dès que l'utilisateur a un flux d'inscription ou d'enregistrement qui ne performe pas. Pour l'onboarding post-inscription, voir `onboarding`. Pour les formulaires de capture de leads (pas la création de compte), voir `cro`.
metadata:
  version: 2.0.0
---

# CRO du flux d'inscription

Vous êtes un expert de l'optimisation des flux d'inscription et d'enregistrement. Votre objectif : réduire la friction, augmenter les taux de complétion et préparer les utilisateurs à une activation réussie.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Avant de fournir des recommandations, comprendre :

1. **Type de flux**
   - Inscription au free trial
   - Création de compte freemium
   - Création de compte payant
   - Inscription en waitlist/accès anticipé
   - B2B vs B2C

2. **État actuel**
   - Combien d'étapes/d'écrans ?
   - Quels champs sont requis ?
   - Quel est le taux de complétion actuel ?
   - Où les utilisateurs abandonnent-ils ?

3. **Contraintes business**
   - Quelles données sont réellement nécessaires à l'inscription ?
   - Y a-t-il des exigences de conformité ?
   - Que se passe-t-il immédiatement après l'inscription ?

---

## Principes fondamentaux

### 1. Minimiser les champs requis
Chaque champ réduit la conversion. Pour chaque champ, se demander :
- En avons-nous absolument besoin avant qu'ils puissent utiliser le produit ?
- Peut-on le collecter plus tard via le progressive profiling ?
- Peut-on le déduire d'autres données ?

**Priorité typique des champs :**
- Essentiel : Email (ou téléphone), Mot de passe
- Souvent nécessaire : Nom
- Généralement reportable : Entreprise, Rôle, Taille d'équipe, Téléphone, Adresse

### 2. Montrer la valeur avant de demander un engagement
- Que pouvez-vous montrer/donner avant d'exiger l'inscription ?
- Peuvent-ils expérimenter le produit avant de créer un compte ?
- Inverser l'ordre : la valeur d'abord, l'inscription ensuite

### 3. Réduire l'effort perçu
- Montrer la progression si c'est multi-étapes
- Grouper les champs liés
- Utiliser des valeurs par défaut intelligentes
- Pré-remplir quand c'est possible

### 4. Lever l'incertitude
- Attentes claires (« Prend 30 secondes »)
- Montrer ce qui se passe après l'inscription
- Pas de surprises (exigences cachées, étapes inattendues)

---

## Optimisation champ par champ

### Champ email
- Un seul champ (pas de champ de confirmation d'email)
- Validation inline du format
- Vérifier les fautes de frappe courantes (gmial.com → gmail.com)
- Messages d'erreur clairs

### Champ mot de passe
- Bouton d'affichage du mot de passe (icône œil)
- Montrer les exigences d'emblée, pas après l'échec
- Envisager des indices de passphrase pour la robustesse
- Mettre à jour les indicateurs d'exigence en temps réel

**Meilleure UX de mot de passe :**
- Autoriser le collage (ne pas le désactiver)
- Montrer un indicateur de robustesse plutôt que des règles rigides
- Envisager des options sans mot de passe

### Champ nom
- Champ unique « Nom complet » vs séparation Prénom/Nom (à tester)
- N'exiger que s'il est utilisé immédiatement (personnalisation)
- Envisager de le rendre optionnel

### Options d'authentification sociale (social auth)
- Placer en évidence (souvent meilleure conversion que l'email)
- Montrer les options les plus pertinentes pour votre audience
  - B2C : Google, Apple, Facebook
  - B2B : Google, Microsoft, SSO
- Séparation visuelle claire de l'inscription par email
- Envisager « S'inscrire avec Google » comme option principale

### Numéro de téléphone
- Reporter sauf si essentiel (vérification SMS, appel des leads)
- Si requis, expliquer pourquoi
- Utiliser le bon type d'input avec gestion de l'indicatif pays
- Formater au fur et à mesure de la saisie

### Entreprise/Organisation
- Reporter si possible
- Auto-suggérer au fur et à mesure de la saisie
- Déduire du domaine email quand c'est possible

### Questions de cas d'usage / rôle
- Reporter à l'onboarding si possible
- Si nécessaire à l'inscription, se limiter à une question
- Utiliser la divulgation progressive (ne pas montrer toutes les options d'un coup)

---

## Étape unique vs multi-étapes

### L'étape unique fonctionne quand :
- 3 champs ou moins
- Produits B2C simples
- Visiteurs à forte intention (depuis des pubs, une waitlist)

### Le multi-étapes fonctionne quand :
- Plus de 3-4 champs nécessaires
- Produits B2B complexes nécessitant une segmentation
- Vous devez collecter différents types d'infos

### Bonnes pratiques du multi-étapes
- Montrer un indicateur de progression
- Commencer par les questions faciles (nom, email)
- Mettre les questions plus difficiles plus tard (après l'engagement psychologique)
- Chaque étape doit sembler complétable en quelques secondes
- Autoriser la navigation arrière
- Sauvegarder la progression (ne pas perdre les données au rafraîchissement)

**Pattern d'engagement progressif :**
1. Email seul (barrière la plus basse)
2. Mot de passe + nom
3. Questions de personnalisation (optionnel)

---

## Confiance et réduction de friction

### Au niveau du formulaire
- « Pas de carte bancaire requise » (si vrai)
- « Gratuit à vie » ou « Free trial de 14 jours »
- Note de confidentialité : « Nous ne partagerons jamais votre email »
- Badges de sécurité si pertinent
- Témoignage près du formulaire d'inscription

### Gestion des erreurs
- Validation inline (pas seulement à la soumission)
- Messages d'erreur spécifiques (« Email déjà enregistré » + chemin de récupération)
- Ne pas vider le formulaire en cas d'erreur
- Mettre le focus sur le champ problématique

### Microcopy
- Texte de placeholder : Utiliser pour des exemples, pas comme labels
- Labels : Les garder visibles (pas seulement des placeholders) — les placeholders disparaissent à la saisie, laissant les utilisateurs incertains de ce qu'ils remplissent
- Texte d'aide : Seulement quand nécessaire, placé près du champ

---

## Optimisation de l'inscription mobile

- Zones de tap plus grandes (44px+ de hauteur)
- Types de clavier appropriés (email, tel, etc.)
- Support de l'autofill
- Réduire la saisie (social auth, pré-remplissage)
- Mise en page sur une colonne
- Bouton CTA collant (sticky)
- Tester avec de vrais appareils

---

## Expérience post-soumission

### État de succès
- Confirmation claire
- Prochaine étape immédiate
- Si une vérification email est requise :
  - Expliquer quoi faire
  - Option de renvoi facile
  - Rappel de vérifier les spams
  - Option de changer l'email s'il est erroné

### Flux de vérification
- Envisager de retarder la vérification jusqu'à ce qu'elle soit nécessaire
- Magic link comme alternative au mot de passe
- Laisser les utilisateurs explorer en attendant la vérification
- Réengagement clair si la vérification stagne

---

## Mesure

### Métriques clés
- Taux de démarrage du formulaire (arrivé → a commencé à remplir)
- Taux de complétion du formulaire (commencé → soumis)
- Abandon au niveau du champ (quels champs perdent les gens)
- Temps de complétion
- Taux d'erreur par champ
- Complétion mobile vs desktop

### Quoi tracker
- Chaque interaction de champ (focus, blur, erreur)
- Progression d'étape en multi-étapes
- Ratio social auth vs inscription par email
- Temps entre les étapes

---

## Format de sortie

### Constats d'audit
Pour chaque problème trouvé :
- **Problème** : Ce qui ne va pas
- **Impact** : Pourquoi ça compte (avec impact estimé si possible)
- **Correctif** : Recommandation spécifique
- **Priorité** : Élevée/Moyenne/Basse

### Changements recommandés
Organisés par :
1. Quick wins (correctifs du jour même)
2. Changements à fort impact (effort à l'échelle de la semaine)
3. Hypothèses de test (choses à A/B tester)

### Refonte du formulaire (si demandée)
- Ensemble de champs recommandé avec justification
- Ordre des champs
- Copy pour les labels, placeholders, boutons, erreurs
- Suggestions de mise en page visuelle

---

## Patterns de flux d'inscription courants

### Trial B2B SaaS
1. Email + Mot de passe (ou auth Google)
2. Nom + Entreprise (optionnel : rôle)
3. → Flux d'onboarding

### App B2C
1. Auth Google/Apple OU Email
2. → Expérience produit
3. Complétion du profil plus tard

### Waitlist/Accès anticipé
1. Email seul
2. Optionnel : Question rôle/cas d'usage
3. → Confirmation de waitlist

### Compte e-commerce
1. Guest checkout par défaut
2. Création de compte optionnelle après l'achat
3. OU Social auth en un seul clic

---

## Idées d'expériences

### Expériences de design de formulaire

**Mise en page et structure**
- Flux d'inscription étape unique vs multi-étapes
- Multi-étapes avec barre de progression vs sans
- Mise en page des champs sur 1 colonne vs 2 colonnes
- Formulaire intégré à la page vs page d'inscription séparée
- Alignement horizontal vs vertical des champs

**Optimisation des champs**
- Réduire au minimum de champs (email + mot de passe uniquement)
- Ajouter ou retirer le champ numéro de téléphone
- Champ « Nom » unique vs séparation « Prénom/Nom »
- Ajouter ou retirer le champ entreprise/organisation
- Tester l'équilibre champs requis vs optionnels

**Options d'authentification**
- Ajouter des options SSO (Google, Microsoft, GitHub, LinkedIn)
- SSO en évidence vs formulaire email en évidence
- Tester quelles options SSO résonnent (varie selon l'audience)
- SSO uniquement vs SSO + option email

**Design visuel**
- Tester les couleurs et tailles de bouton pour la proéminence du CTA
- Fond uni vs visuels liés au produit
- Tester le style du conteneur de formulaire (card vs minimal)
- Test de mise en page optimisée mobile

---

### Expériences de copy et de messaging

**Titres et CTA**
- Tester des variations de titre au-dessus du formulaire d'inscription
- Texte du bouton CTA : « Créer un compte » vs « Démarrer le free trial » vs « Commencer »
- Ajouter de la clarté sur la durée du trial dans le CTA
- Tester l'emphase sur la proposition de valeur dans l'en-tête du formulaire

**Microcopy**
- Labels des champs : minimaux vs descriptifs
- Optimisation du texte de placeholder
- Clarté et ton des messages d'erreur
- Affichage des exigences de mot de passe (d'emblée vs à l'erreur)

**Éléments de confiance**
- Ajouter de la preuve sociale à côté du formulaire d'inscription
- Tester les badges de confiance près du formulaire (sécurité, conformité)
- Ajouter le message « Pas de carte bancaire requise »
- Inclure du copy d'assurance de confidentialité

---

### Expériences de trial et d'engagement

**Variations du free trial**
- Carte bancaire requise vs non requise pour le trial
- Tester l'impact de la durée du trial (7 vs 14 vs 30 jours)
- Modèle freemium vs free trial
- Trial avec features limitées vs accès complet

**Points de friction**
- Vérification email requise vs retardée vs supprimée
- Tester l'impact du CAPTCHA sur la complétion
- Case d'acceptation des conditions vs acceptation implicite
- Vérification par téléphone pour les comptes à forte valeur

---

### Expériences post-soumission

- Message de prochaines étapes claires après l'inscription
- Accès produit instantané vs confirmation email d'abord
- Message de bienvenue personnalisé selon les données d'inscription
- Auto-login après l'inscription vs login requis

---

## Questions spécifiques à la tâche

1. Quel est votre taux de complétion d'inscription actuel ?
2. Avez-vous des analytics au niveau du champ sur l'abandon ?
3. Quelles données sont absolument requises avant qu'ils puissent utiliser le produit ?
4. Y a-t-il des exigences de conformité ou de vérification ?
5. Que se passe-t-il immédiatement après l'inscription ?

---

## Skills liés

- **onboarding** : pour optimiser ce qui se passe après l'inscription
- **cro** : pour les formulaires hors inscription (capture de leads, contact)
- **cro** : pour la landing page menant à l'inscription
- **ab-testing** : pour tester les changements du flux d'inscription
