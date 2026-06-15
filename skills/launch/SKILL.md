---
name: launch
description: "À utiliser quand l'utilisateur veut planifier un lancement de produit, une annonce de fonctionnalité ou une stratégie de release. Aussi quand il mentionne « launch », « lancement », « Product Hunt », « feature release », « sortie de fonctionnalité », « annonce », « go-to-market », « GTM », « beta launch », « lancement beta », « early access », « accès anticipé », « waitlist », « liste d'attente », « product update », « mise à jour produit », « comment je lance ça », « checklist de lancement », « plan GTM » ou « on est sur le point de shipper ». À utiliser dès que quelqu'un se prépare à rendre quelque chose public. Pour le marketing continu après le lancement, voir marketing-ideas."
metadata:
  version: 2.0.0
---

# Launch Strategy

Vous êtes un·e expert·e des lancements de produit SaaS et des annonces de fonctionnalités. Votre objectif est d'aider les utilisateurs à planifier des lancements qui créent de l'élan, captent l'attention et convertissent l'intérêt en utilisateurs.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

---

## Philosophie de fond

Les meilleures entreprises ne lancent pas une seule fois — elles lancent encore et encore. Chaque nouvelle fonctionnalité, amélioration et mise à jour est une occasion de capter l'attention et d'engager votre audience.

Un bon lancement ne se résume pas à un instant unique. Il s'agit de :
- Mettre votre produit tôt entre les mains des utilisateurs
- Apprendre des retours réels
- Faire parler de soi à chaque étape
- Construire un élan qui se cumule dans le temps

---

## Le cadre ORB

Structurez votre marketing de lancement sur trois types de canaux. Tout doit, à terme, ramener vers les canaux owned.

### Canaux owned
Vous possédez le canal (mais pas l'audience). Accès direct, sans algorithmes ni règles de plateforme.

**Exemples :**
- Liste email
- Blog
- Podcast
- Communauté de marque (Slack, Discord)
- Site web/produit

**Pourquoi ils comptent :**
- Deviennent plus efficaces avec le temps
- Pas de changements d'algorithme ni de pay-to-play
- Relation directe avec l'audience
- Valeur cumulée du contenu

**Commencez par 1-2 selon l'audience :**
- Le secteur manque de contenu de qualité → lancer un blog
- Les gens veulent des updates directes → se concentrer sur l'email
- L'engagement compte → construire une communauté

**Exemple - Superhuman :**
A construit la demande via une waitlist sur invitation et des sessions d'onboarding en tête-à-tête. Chaque nouvel utilisateur avait droit à une démo live de 30 minutes. Cela créait de l'exclusivité, de la FOMO et du bouche-à-oreille — le tout via des relations owned. Des années plus tard, leurs supports d'onboarding originaux génèrent encore de l'engagement.

### Canaux rented
Des plateformes qui offrent de la visibilité mais que vous ne contrôlez pas. Les algorithmes changent, les règles évoluent, le pay-to-play augmente.

**Exemples :**
- Réseaux sociaux (Twitter/X, LinkedIn, Instagram)
- App stores et marketplaces
- YouTube
- Reddit

**Comment les utiliser correctement :**
- Choisir 1-2 plateformes où votre audience est active
- Les utiliser pour générer du trafic vers les canaux owned
- Ne pas en faire votre seule stratégie

**Exemple - Notion :**
A hacké la viralité via Twitter, YouTube et Reddit où les passionnés de productivité étaient actifs. A encouragé la communauté à partager templates et workflows. Mais ils canalisaient toute la visibilité vers des assets owned — chaque post viral menait à des inscriptions, puis à un onboarding email ciblé.

**Tactiques spécifiques par plateforme :**
- Twitter/X : threads qui suscitent la conversation → lien vers la newsletter
- LinkedIn : posts à forte valeur → vers du contenu gated ou une inscription email
- Marketplaces (Shopify, Slack) : optimiser la fiche → diriger vers le site pour en savoir plus

Les canaux rented donnent de la vitesse, pas de la stabilité. Capturez l'élan en amenant les utilisateurs dans votre écosystème owned.

### Canaux borrowed
Puiser dans l'audience de quelqu'un d'autre pour court-circuiter le plus dur — se faire remarquer.

**Exemples :**
- Contenu invité (articles de blog, interviews podcast, features de newsletter)
- Collaborations (webinaires, co-marketing, takeovers sociaux)
- Prises de parole (conférences, panels, sommets virtuels)
- Partenariats influenceurs

**Soyez proactif, pas passif :**
1. Lister les leaders du secteur que votre audience suit
2. Pitcher des collaborations gagnant-gagnant
3. Utiliser des outils comme SparkToro ou Listen Notes pour trouver le recouvrement d'audience
4. Mettre en place des incentives affiliés/parrainage (pour les lancements via partenaires de canal, utiliser [Introw](../../tools/integrations/introw.md) pour gérer l'enregistrement de deals et les commissions)

**Exemple - TRMNL :**
A envoyé un écran e-ink gratuit au YouTubeur Snazzy Labs — pas un sponsoring payé, juste l'espoir qu'il l'apprécie. Il a réalisé un test approfondi qui a cumulé 500K+ vues et généré 500K+ € de ventes. Ils ont aussi mis en place un programme d'affiliation pour une promotion continue.

Les canaux borrowed donnent une crédibilité instantanée, mais ne fonctionnent que si vous convertissez l'attention empruntée en relations owned.

---

## Approche de lancement en cinq phases

Lancer n'est pas un événement d'une journée. C'est un processus par phases qui construit l'élan.

### Phase 1 : Lancement interne
Recueillir les premiers retours et résoudre les problèmes majeurs avant de devenir public.

**Actions :**
- Recruter des early users en tête-à-tête pour tester gratuitement
- Collecter des retours sur les lacunes d'utilisabilité et les fonctionnalités manquantes
- S'assurer que le prototype est assez fonctionnel pour être démontré (pas besoin qu'il soit prêt pour la production)

**Objectif :** valider la fonctionnalité de base avec des utilisateurs bienveillants.

### Phase 2 : Lancement alpha
Mettre le produit devant des utilisateurs externes de façon contrôlée.

**Actions :**
- Créer une landing page avec un formulaire d'inscription early access
- Annoncer l'existence du produit
- Inviter les utilisateurs individuellement à commencer à tester
- Le MVP doit fonctionner en production (même s'il évolue encore)

**Objectif :** première validation externe et début de construction de la waitlist.

### Phase 3 : Lancement beta
Monter en charge l'early access tout en générant du buzz externe.

**Actions :**
- Traiter la liste d'early access (certains gratuits, certains payants)
- Commencer à marketer avec des teasers sur les problèmes que vous résolvez
- Recruter amis, investisseurs et influenceurs pour tester et partager

**À envisager d'ajouter :**
- Landing page « coming soon » ou waitlist
- Badge « Beta » dans la navigation du dashboard
- Invitations email vers la liste d'early access
- Toggle early access dans les paramètres pour les fonctionnalités expérimentales

**Objectif :** créer du buzz et affiner le produit avec des retours plus larges.

### Phase 4 : Lancement early access
Passer du test à petite échelle à une expansion contrôlée.

**Actions :**
- Laisser fuiter des détails produit : screenshots, GIFs de fonctionnalités, démos
- Recueillir des données d'usage quantitatives et des retours qualitatifs
- Mener de la recherche utilisateur avec les utilisateurs engagés (inciter avec des crédits)
- Optionnellement, lancer une enquête de product/market fit pour affiner le messaging

**Options d'expansion :**
- Option A : throttler les invitations par batches (5-10 % à la fois)
- Option B : inviter tous les utilisateurs d'un coup sous l'angle « early access »

**Objectif :** valider à l'échelle et préparer le lancement complet.

### Phase 5 : Lancement complet
Ouvrir les vannes.

**Actions :**
- Ouvrir les inscriptions en self-serve
- Commencer à facturer (si ce n'est pas déjà fait)
- Annoncer la disponibilité générale sur tous les canaux

**Points de contact du lancement :**
- Emails clients
- Popups in-app et tours produit
- Bannière site web pointant vers les assets de lancement
- Badge « New » dans la navigation du dashboard
- Article de blog d'annonce
- Posts sociaux sur toutes les plateformes
- Product Hunt, BetaList, Hacker News, etc.

**Objectif :** visibilité maximale et conversion en utilisateurs payants.

---

## Stratégie de lancement Product Hunt

Product Hunt peut être puissant pour atteindre les early adopters, mais ce n'est pas magique — ça demande de la préparation.

### Avantages
- Exposition à une audience d'early adopters tech-savvy
- Bump de crédibilité (surtout si Product of the Day)
- Couverture presse potentielle et backlinks

### Inconvénients
- Très compétitif pour bien se classer
- Pics de trafic éphémères
- Demande une planification pré-lancement significative

### Comment lancer avec succès

**Avant le jour J :**
1. Construire des relations avec des supporters influents, des content hubs et des communautés
2. Optimiser votre fiche : tagline percutante, visuels soignés, courte vidéo démo
3. Étudier les lancements réussis pour identifier ce qui a marché
4. S'engager dans les communautés pertinentes — apporter de la valeur avant de pitcher
5. Préparer votre équipe à un engagement sur toute la journée

**Le jour J :**
1. Le traiter comme un événement d'une journée entière
2. Répondre à chaque commentaire en temps réel
3. Répondre aux questions et lancer des discussions
4. Encourager votre audience existante à s'engager
5. Rediriger le trafic vers votre site pour capturer des inscriptions

**Après le jour J :**
1. Relancer tous ceux qui se sont engagés
2. Convertir le trafic Product Hunt en relations owned (inscriptions email)
3. Maintenir l'élan avec du contenu post-lancement

### Études de cas

**SavvyCal** (outil de prise de RDV) :
- A optimisé la landing page et l'onboarding avant le lancement
- A construit des relations avec des influenceurs productivité/SaaS en amont
- A répondu à chaque commentaire le jour J
- Résultat : #2 Product of the Month

**Reform** (form builder) :
- A étudié les lancements réussis et appliqué les enseignements
- A façonné une tagline claire, des visuels soignés, une vidéo démo
- S'est engagé dans les communautés avant le lancement (a apporté de la valeur d'abord)
- A traité le lancement comme un événement d'engagement d'une journée entière
- A redirigé le trafic pour capturer des inscriptions
- Résultat : #1 Product of the Day

---

## Product marketing post-lancement

Votre lancement n'est pas terminé quand l'annonce passe en ligne. Vient maintenant le travail d'adoption et de rétention.

### Actions immédiates post-lancement

**Former les nouveaux utilisateurs :**
Mettre en place une séquence email d'onboarding automatisée présentant les fonctionnalités clés et les cas d'usage.

**Renforcer le lancement :**
Inclure l'annonce dans votre email récap hebdo/bimensuel/mensuel pour toucher ceux qui l'ont manquée.

**Se différencier des concurrents :**
Publier des pages de comparaison soulignant pourquoi vous êtes le choix évident.

**Mettre à jour les pages web :**
Ajouter des sections dédiées à la nouvelle fonctionnalité/au nouveau produit sur tout votre site.

**Offrir un aperçu interactif :**
Créer une démo interactive no-code (avec des outils comme Navattic) pour que les visiteurs puissent explorer avant de s'inscrire.

### Maintenir l'élan
Il est plus facile de capitaliser sur un élan existant que de repartir de zéro. Chaque point de contact renforce le lancement.

---

## Stratégie de lancement continue

Ne comptez pas sur un événement de lancement unique. Des updates régulières et des déploiements de fonctionnalités soutiennent l'engagement.

### Comment prioriser ce qu'il faut annoncer

Utilisez cette matrice pour décider du niveau de marketing que chaque update mérite :

**Updates majeures** (nouvelles fonctionnalités, refontes produit) :
- Campagne complète sur plusieurs canaux
- Article de blog, campagne email, messages in-app, réseaux sociaux
- Maximiser l'exposition

**Updates moyennes** (nouvelles intégrations, améliorations UI) :
- Annonce ciblée
- Email aux segments pertinents, bannière in-app
- Pas besoin de tout le tralala

**Updates mineures** (corrections de bugs, petits ajustements) :
- Changelog et release notes
- Signaler que le produit s'améliore
- Ne pas dominer le marketing

### Tactiques d'annonce

**Espacer les releases :**
Plutôt que de tout shipper d'un coup, étaler les annonces pour maintenir l'élan.

**Réutiliser les tactiques performantes :**
Si une annonce précédente a résonné, appliquer ces enseignements aux futures updates.

**Continuer à engager :**
Continuer à utiliser email, social et messaging in-app pour mettre en avant les améliorations.

**Signaler un développement actif :**
Même de petites updates de changelog rappellent aux clients que votre produit évolue. Cela construit la rétention et le bouche-à-oreille — les clients sont confiants que vous serez encore là.

---

## Checklist de lancement

### Pré-lancement
- [ ] Landing page avec proposition de valeur claire
- [ ] Capture d'email / inscription waitlist
- [ ] Liste d'early access construite
- [ ] Canaux owned établis (email, blog, communauté)
- [ ] Présence sur canaux rented (profils sociaux optimisés)
- [ ] Opportunités de canaux borrowed identifiées (podcasts, influenceurs)
- [ ] Fiche Product Hunt préparée (si utilisée)
- [ ] Assets de lancement créés (screenshots, vidéo démo, GIFs)
- [ ] Flow d'onboarding prêt
- [ ] Analytics/tracking en place

### Jour du lancement
- [ ] Email d'annonce à la liste
- [ ] Article de blog publié
- [ ] Posts sociaux planifiés et publiés
- [ ] Fiche Product Hunt en ligne (si utilisée)
- [ ] Annonce in-app pour les utilisateurs existants
- [ ] Bannière/notification site web active
- [ ] Équipe prête à engager et répondre
- [ ] Surveiller les problèmes et les retours

### Post-lancement
- [ ] Séquence email d'onboarding active
- [ ] Relance des prospects engagés
- [ ] Email récap incluant l'annonce
- [ ] Pages de comparaison publiées
- [ ] Démo interactive créée
- [ ] Recueillir et agir sur les retours
- [ ] Planifier le prochain moment de lancement

---

## Questions spécifiques à la tâche

1. Que lancez-vous ? (Nouveau produit, fonctionnalité majeure, update mineure)
2. Quelle est votre taille d'audience et votre engagement actuels ?
3. Quels canaux owned avez-vous ? (Taille de liste email, trafic blog, communauté)
4. Quel est votre calendrier de lancement ?
5. Avez-vous déjà lancé ? Qu'est-ce qui a marché/pas marché ?
6. Envisagez-vous Product Hunt ? Où en est votre préparation ?

---

## Skills associés

- **marketing-ideas** : pour des tactiques de lancement supplémentaires (#22 Product Hunt, #23 Early Access Referrals)
- **emails** : pour les séquences email de lancement et d'onboarding
- **cro** : pour optimiser les landing pages de lancement
- **marketing-psychology** : pour la psychologie derrière les waitlists et l'exclusivité
- **programmatic-seo** : pour les pages de comparaison mentionnées en post-lancement
- **sales-enablement** : pour les supports de vente et matériels d'enablement de lancement
