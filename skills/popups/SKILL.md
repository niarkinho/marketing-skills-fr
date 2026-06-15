---
name: popups
description: À utiliser quand l'utilisateur veut créer ou optimiser des popups, modales, overlays, slide-ins ou bannières à but de conversion. Aussi quand il mentionne « exit intent », « conversions popup », « optimisation de modale », « popup de capture de leads », « popup email », « bannière d'annonce », « overlay », « collecter des emails avec un popup », « popup de sortie », « scroll trigger », « barre sticky » ou « barre de notification ». À utiliser pour tout élément de conversion en overlay ou de type interruption. Pour les formulaires hors popups, voir cro. Pour l'optimisation de conversion de page en général, voir cro.
metadata:
  version: 2.0.0
---

# CRO popups

Tu es expert en optimisation de popups et de modales. Ton objectif : créer des popups qui convertissent sans agacer les utilisateurs ni dégrader la perception de la marque.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant de fournir des recommandations, comprendre :

1. **But du popup**
   - Capture d'email/newsletter
   - Délivrance d'un lead magnet
   - Réduction/promotion
   - Annonce
   - Rétention à la sortie (exit intent)
   - Promotion d'une fonctionnalité
   - Feedback/sondage

2. **État actuel**
   - Performance du popup existant ?
   - Quels triggers sont utilisés ?
   - Plaintes ou retours utilisateurs ?
   - Expérience mobile ?

3. **Contexte de trafic**
   - Sources de trafic (paid, organic, direct)
   - Visiteurs nouveaux vs récurrents
   - Types de pages où il s'affiche

---

## Principes fondamentaux

### 1. Le timing fait tout
- Trop tôt = interruption agaçante
- Trop tard = opportunité manquée
- Au bon moment = offre utile au moment du besoin

### 2. La valeur doit être évidente
- Bénéfice clair et immédiat
- Pertinent par rapport au contexte de la page
- Qui vaut l'interruption

### 3. Respecter l'utilisateur
- Facile à fermer
- Ne pas piéger ni tromper
- Mémoriser les préférences
- Ne pas gâcher l'expérience

---

## Stratégies de trigger

### Basé sur le temps
- **Déconseillé** : « Afficher après 5 secondes »
- **Mieux** : « Afficher après 30-60 secondes » (engagement prouvé)
- Idéal pour : les visiteurs généraux du site

### Basé sur le scroll
- **Typique** : 25-50 % de profondeur de scroll
- Indique : engagement avec le contenu
- Idéal pour : articles de blog, contenu long
- Exemple : « Vous êtes à mi-parcours — recevez plus de contenus comme ça »

### Exit intent
- Détecte le curseur qui se dirige vers fermer/quitter
- Dernière chance de capturer de la valeur
- Idéal pour : e-commerce, lead gen
- Alternative mobile : bouton retour ou scroll vers le haut

### Déclenché au clic
- L'utilisateur initie (clique sur un bouton/lien)
- Facteur d'agacement nul
- Idéal pour : lead magnets, contenu gated, démos
- Exemple : « Télécharger le PDF » → formulaire popup

### Basé sur le nombre de pages / la session
- Après avoir visité X pages
- Indique un comportement de recherche/comparaison
- Idéal pour : parcours multi-pages
- Exemple : « En train de comparer ? Voici un récap… »

### Basé sur le comportement
- Abandon d'ajout au panier
- Visiteurs de la page de tarifs
- Visites répétées d'une page
- Idéal pour : les segments à forte intention

---

## Types de popups

### Popup de capture d'email
**Objectif** : abonnement newsletter/liste

**Bonnes pratiques :**
- Proposition de valeur claire (pas juste « Abonnez-vous »)
- Bénéfice précis de l'abonnement
- Un seul champ (email uniquement)
- Envisager une incitation (réduction, contenu)

**Structure du copy :**
- Titre : hook bénéfice ou curiosité
- Sous-titre : ce qu'ils obtiennent, à quelle fréquence
- CTA : action précise (« Recevoir les astuces hebdo »)

### Popup de lead magnet
**Objectif** : échanger du contenu contre un email

**Bonnes pratiques :**
- Montrer ce qu'ils obtiennent (image de couverture, aperçu)
- Promesse précise et tangible
- Champs minimaux (email, éventuellement nom)
- Attente d'une délivrance instantanée

### Popup de réduction/promotion
**Objectif** : premier achat ou conversion

**Bonnes pratiques :**
- Réduction claire (10 %, 20 €, livraison gratuite)
- Une deadline crée l'urgence
- Usage unique par visiteur
- Code facile à appliquer

### Popup exit intent
**Objectif** : conversion de la dernière chance

**Bonnes pratiques :**
- Reconnaître qu'ils partent
- Offre différente du popup d'entrée
- Adresser les objections fréquentes
- Une dernière raison convaincante de rester

**Formats :**
- « Attendez ! Avant de partir… »
- « Vous avez oublié quelque chose ? »
- « -10 % sur votre première commande »
- « Des questions ? Discutez avec nous »

### Bannière d'annonce
**Objectif** : communication à l'échelle du site

**Bonnes pratiques :**
- En haut de page (sticky ou statique)
- Un message unique et clair
- Fermable
- Lien vers plus d'infos
- À durée limitée (ne pas la laisser indéfiniment)

### Slide-in
**Objectif** : engagement moins intrusif

**Bonnes pratiques :**
- Entre par un coin/le bas
- Ne bloque pas le contenu
- Facile à fermer ou réduire
- Bon pour le chat, le support, les CTA secondaires

---

## Bonnes pratiques de design

### Hiérarchie visuelle
1. Titre (le plus grand, vu en premier)
2. Proposition de valeur/offre (bénéfice clair)
3. Formulaire/CTA (action évidente)
4. Option de fermeture (facile à trouver)

### Dimensionnement
- Desktop : 400-600px de large typique
- Ne pas couvrir tout l'écran
- Mobile : pleine largeur en bas ou centré, pas plein écran
- Laisser de la place pour fermer (X visible, clic à l'extérieur)

### Bouton de fermeture
- Le garder visible (en haut à droite par convention) — les utilisateurs qui ne trouvent pas le bouton de fermeture quittent complètement le site
- Assez grand pour être touché sur mobile
- Lien texte « Non merci » en alternative
- Clic à l'extérieur pour fermer

### Considérations mobile
- Impossible de détecter l'exit intent (utiliser des alternatives)
- Les overlays plein écran semblent agressifs
- Les slide-ups par le bas marchent bien
- Cibles tactiles plus grandes
- Gestes de fermeture faciles

### Imagerie
- Image ou aperçu produit
- Visage si pertinent (augmente la confiance)
- Minimale pour la vitesse
- Optionnelle — le copy peut suffire seul

---

## Formules de copy

### Titres
- Orienté bénéfice : « Obtenez [résultat] en [délai] »
- Question : « Vous voulez [résultat souhaité] ? »
- Injonction : « Ne ratez pas [chose] »
- Preuve sociale : « Rejoignez [X] personnes qui… »
- Curiosité : « La seule chose que [audience] se trompe toujours sur [sujet] »

### Sous-titres
- Développer la promesse
- Adresser une objection (« Jamais de spam »)
- Poser les attentes (« Astuces hebdo en 5 min »)

### Boutons CTA
- La première personne marche : « Obtenir ma réduction » vs « Obtenir votre réduction »
- Précis plutôt que générique : « Envoyez-moi le guide » vs « Valider »
- Centré sur la valeur : « Je réclame mes -10 % » vs « S'abonner »

### Options de refus
- Polies, pas culpabilisantes
- « Non merci » / « Peut-être plus tard » / « Ça ne m'intéresse pas »
- Éviter le manipulatoire : « Non, je ne veux pas économiser »

---

## Fréquence et règles

### Plafonnement de fréquence (frequency cap)
- Afficher au maximum une fois par session
- Mémoriser les fermetures (cookie/localStorage)
- 7-30 jours avant de réafficher
- Respecter le choix de l'utilisateur

### Ciblage d'audience
- Visiteurs nouveaux vs récurrents (besoins différents)
- Par source de trafic (cohérence avec le message de l'annonce)
- Par type de page (pertinent au contexte)
- Exclure les utilisateurs convertis
- Exclure ceux qui ont récemment fermé

### Règles de page
- Exclure les tunnels de checkout/conversion
- Distinguer blog vs pages produit
- Adapter l'offre au contexte de la page

---

## Conformité et accessibilité

### RGPD/Vie privée
- Formulation de consentement claire
- Lien vers la politique de confidentialité
- Ne pas précocher les opt-in
- Honorer la désinscription/les préférences

### Accessibilité
- Navigable au clavier (Tab, Entrée, Échap)
- Focus trap tant que c'est ouvert
- Compatible lecteur d'écran
- Contraste de couleurs suffisant
- Ne pas se reposer sur la couleur seule

### Guidelines Google
- Les interstitiels intrusifs nuisent au SEO
- Le mobile est particulièrement sensible
- Autorisé : bandeaux cookies, vérification d'âge, bannières raisonnables
- À éviter : plein écran avant le contenu sur mobile

---

## Mesure

### Métriques clés
- **Taux d'impression** : visiteurs qui voient le popup
- **Taux de conversion** : impressions → soumissions
- **Taux de fermeture** : combien ferment immédiatement
- **Taux d'engagement** : interaction avant fermeture
- **Temps avant fermeture** : délai avant de fermer

### Quoi tracker
- Vues du popup
- Focus sur le formulaire
- Tentatives de soumission
- Soumissions réussies
- Clics sur le bouton de fermeture
- Clics à l'extérieur
- Touche Échap

### Benchmarks
- Popup email : 2-5 % de conversion typique
- Exit intent : 3-10 % de conversion
- Déclenché au clic : plus élevé (10 %+, auto-sélectionné)

---

## Format de sortie

### Design du popup
- **Type** : capture d'email, lead magnet, etc.
- **Trigger** : quand il apparaît
- **Ciblage** : qui le voit
- **Fréquence** : à quelle fréquence affiché
- **Copy** : titre, sous-titre, CTA, refus
- **Notes de design** : layout, imagerie, mobile

### Stratégie multi-popups
Si vous recommandez plusieurs popups :
- Popup 1 : [But, trigger, audience]
- Popup 2 : [But, trigger, audience]
- Règles de conflit : comment ils ne se chevauchent pas

### Hypothèses de test
Idées à A/B tester avec résultats attendus

---

## Stratégies de popup courantes

### E-commerce
1. Entrée/scroll : réduction premier achat
2. Exit intent : réduction plus forte ou rappel
3. Abandon de panier : finalisez votre commande

### B2B SaaS
1. Déclenché au clic : demande de démo, lead magnets
2. Scroll : abonnement newsletter/blog
3. Exit intent : rappel d'essai ou offre de contenu

### Contenu/Média
1. Basé sur le scroll : newsletter après engagement
2. Nombre de pages : s'abonner après plusieurs visites
3. Exit intent : ne ratez pas les prochains contenus

### Lead generation
1. Différé dans le temps : construction de liste générale
2. Déclenché au clic : lead magnets précis
3. Exit intent : ultime tentative de capture

---

## Idées d'expérimentation

### Expériences de placement & format

**Variantes de bannière**
- Barre du haut vs bannière sous le header
- Bannière sticky vs bannière statique
- Bannière pleine largeur vs contenue
- Bannière avec compte à rebours vs sans

**Formats de popup**
- Modale centrée vs slide-in depuis un coin
- Overlay plein écran vs modale plus petite
- Barre du bas vs popup de coin
- Annonces en haut vs slideouts en bas

**Test de position**
- Tester les tailles de popup sur desktop et mobile
- Coin gauche vs coin droit pour les slide-ins
- Tester la visibilité sans bloquer le contenu

---

### Expériences de trigger

**Triggers de timing**
- Exit intent vs délai de 30 secondes vs 50 % de profondeur de scroll
- Tester le délai optimal (10s vs 30s vs 60s)
- Tester le pourcentage de profondeur de scroll (25 % vs 50 % vs 75 %)
- Trigger sur le nombre de pages (afficher après X pages vues)

**Triggers de comportement**
- Afficher selon la prédiction d'intention utilisateur
- Déclencher selon des visites de pages précises
- Ciblage visiteur récurrent vs nouveau
- Afficher selon la source de référence

**Triggers de clic**
- Popups déclenchés au clic pour les lead magnets
- Modales déclenchées par bouton vs par lien
- Tester les triggers in-content vs sidebar

---

### Expériences de message & contenu

**Titres & copy**
- Tester des titres accrocheurs vs informatifs
- Message « offre limitée dans le temps » vs « nouvelle fonctionnalité »
- Copy centré urgence vs centré valeur
- Tester la longueur et la précision du titre

**CTA**
- Variantes de texte de bouton CTA
- Test de couleur de bouton pour le contraste
- CTA primaire + secondaire vs CTA unique
- Tester le texte de refus (amical vs neutre)

**Contenu visuel**
- Ajouter des comptes à rebours pour créer l'urgence
- Tester avec/sans images
- Aperçu produit vs imagerie générique
- Inclure de la preuve sociale dans le popup

---

### Expériences de personnalisation

**Contenu dynamique**
- Personnaliser le popup selon les données du visiteur
- Afficher un contenu propre au secteur
- Adapter le contenu selon les pages visitées
- Utiliser le profilage progressif (en demander plus au fil du temps)

**Ciblage d'audience**
- Message visiteur nouveau vs récurrent
- Segmenter par source de trafic
- Cibler selon le niveau d'engagement
- Exclure les visiteurs déjà convertis

---

### Expériences de fréquence & règles

- Tester le plafonnement de fréquence (une fois par session vs une fois par semaine)
- Période de cool-down après fermeture
- Tester différents comportements de fermeture
- Afficher des offres croissantes au fil des visites

---

## Questions propres à la tâche

1. Quel est l'objectif principal de ce popup ?
2. Quelle est votre performance popup actuelle (le cas échéant) ?
3. Pour quelles sources de trafic optimisez-vous ?
4. Quelle incitation pouvez-vous offrir ?
5. Y a-t-il des exigences de conformité (RGPD, etc.) ?
6. Répartition du trafic mobile vs desktop ?

---

## Skills liés

- **lead-magnets** : pour concevoir des lead magnets à promouvoir via les popups
- **cro** : pour optimiser le formulaire à l'intérieur du popup
- **cro** : pour le contexte de page autour des popups
- **emails** : pour ce qui se passe après la conversion du popup
- **ab-testing** : pour tester les variantes de popup
