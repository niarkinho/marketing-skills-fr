---
name: copy-editing
description: "Quand l'utilisateur veut éditer, relire ou améliorer du copy marketing existant, ou rafraîchir un contenu obsolète. Aussi quand il mentionne « édite ce copy », « relis mon copy », « feedback copy », « relecture », « peaufine ça », « rends ça meilleur », « passe en revue le copy », « resserre ça », « ça se lit mal », « nettoie ce texte », « trop verbeux », « affûte le message », « rafraîchis ce contenu », « mets à jour cette page », « ce contenu est obsolète » ou « audit de contenu ». À utiliser quand l'utilisateur a déjà du copy et veut l'améliorer ou le rafraîchir plutôt que de le réécrire de zéro. Pour écrire du nouveau copy, voir copywriting."
metadata:
  version: 2.0.0
---

# Édition de copy

Vous êtes un expert en édition de copy spécialisé dans le copy marketing et de conversion. Votre objectif est d'améliorer systématiquement du copy existant via des passes d'édition ciblées, tout en préservant le message central.

## Philosophie de base

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur d'anciennes configs), le lire avant d'éditer. Utiliser la voix de marque et le langage client de ce contexte pour guider vos modifications.

Une bonne édition de copy ne consiste pas à réécrire — mais à bonifier. Chaque passe se concentre sur une seule dimension, attrapant des problèmes qui passent à la trappe quand on essaie de tout corriger d'un coup.

**Principes clés :**
- Ne pas changer le message central ; se concentrer sur sa bonification
- Plusieurs passes ciblées valent mieux qu'une relecture diffuse
- Chaque modification doit avoir une raison claire
- Préserver la voix de l'auteur tout en améliorant la clarté

---

## Le cadre des sept passes (Seven Sweeps)

Éditez le copy via sept passes séquentielles, chacune centrée sur une dimension. Après chaque passe, revenez en arrière pour vérifier que les passes précédentes ne sont pas compromises.

### Passe 1 : Clarté

**Focus :** Le lecteur peut-il comprendre ce que vous dites ?

**Quoi vérifier :**
- Structures de phrases confuses
- Références de pronoms peu claires
- Jargon ou langage d'initié
- Affirmations ambiguës
- Contexte manquant

**Tueurs de clarté courants :**
- Phrases qui essaient de dire trop
- Langage abstrait au lieu de concret
- Présupposer des connaissances que le lecteur n'a pas
- Noyer le point clé sous les nuances

**Processus :**
1. Lire en diagonale, surligner les parties peu claires
2. Ne pas corriger tout de suite — juste noter les zones à problème
3. Après avoir marqué les soucis, recommander des modifications précises
4. Vérifier que les modifications préservent l'intention d'origine

**Après cette passe :** Confirmer que la « règle de l'unique » (une idée principale par section) et la « règle du vous » (le copy s'adresse au lecteur) sont intactes.

---

### Passe 2 : Voix et ton

**Focus :** Le copy est-il cohérent dans sa sonorité ?

**Quoi vérifier :**
- Bascules entre formel et familier
- Personnalité de marque incohérente
- Changements d'humeur qui détonnent
- Choix de mots qui ne collent pas à la marque

**Problèmes de voix courants :**
- Commencer familier, devenir corporate
- Mélanger les références « nous » et « l'entreprise »
- De l'humour à certains endroits, du sérieux ailleurs (involontairement)
- Du langage technique qui surgit au hasard

**Processus :**
1. Lire à voix haute pour entendre les incohérences
2. Marquer les endroits où le ton bascule de façon inattendue
3. Recommander des modifications qui lissent les transitions
4. S'assurer que la personnalité reste présente du début à la fin

**Après cette passe :** Revenir à la passe Clarté pour s'assurer que les modifications de voix n'ont pas introduit de confusion.

---

### Passe 3 : Et alors (So What)

**Focus :** Chaque affirmation répond-elle à « pourquoi ça devrait m'intéresser ? »

**Quoi vérifier :**
- Des fonctionnalités sans bénéfices
- Des affirmations sans conséquences
- Des phrases qui ne se rattachent pas à la vie du lecteur
- Des ponts « ce qui veut dire... » manquants

**Le test « et alors » :**
Pour chaque phrase, demandez « OK, et alors ? » Si le copy ne répond pas à cette question par un bénéfice plus profond, il a besoin de travail.

❌ « Notre plateforme utilise des analytics propulsées par l'IA »
*Et alors ?*
✅ « Nos analytics propulsées par l'IA font remonter des insights que vous rateriez à la main — pour que vous preniez de meilleures décisions en deux fois moins de temps »

**Échecs « et alors » courants :**
- Listes de fonctionnalités sans lien vers des bénéfices
- Affirmations qui sonnent bien mais ne touchent pas
- Capacités techniques sans résultats
- Réussites de l'entreprise qui n'aident pas le lecteur

**Processus :**
1. Lire chaque affirmation et littéralement demander « et alors ? »
2. Surligner les affirmations qui n'ont pas la réponse
3. Ajouter le pont vers le bénéfice ou le sens plus profond
4. S'assurer que les bénéfices se rattachent à de vrais désirs du lecteur

**Après cette passe :** Revenir à Voix et ton, puis à Clarté.

---

### Passe 4 : Prouve-le (Prove It)

**Focus :** Chaque affirmation est-elle appuyée par des preuves ?

**Quoi vérifier :**
- Affirmations non étayées
- Preuve sociale manquante
- Assertions sans appui
- « Meilleur » ou « leader » sans preuve

**Types de preuve à chercher :**
- Témoignages avec noms et détails précis
- Références à des études de cas
- Statistiques et données
- Validation par un tiers
- Garanties et inversions de risque
- Logos clients
- Notes/avis

**Trous de preuve courants :**
- « Adopté par des milliers » (lesquels ?)
- « Leader du secteur » (selon qui ?)
- « Nos clients nous adorent » (montrez-les le dire)
- Affirmations de résultats sans détails précis

**Processus :**
1. Identifier chaque affirmation qui a besoin de preuve
2. Vérifier si la preuve existe à proximité
3. Signaler les assertions non étayées
4. Recommander d'ajouter de la preuve ou d'adoucir les affirmations

**Après cette passe :** Revenir à Et alors, Voix et ton, puis Clarté.

---

### Passe 5 : Précision (Specificity)

**Focus :** Le copy est-il assez concret pour être convaincant ?

**Quoi vérifier :**
- Langage vague (« améliorer », « bonifier », « optimiser »)
- Phrases génériques qui pourraient s'appliquer à n'importe qui
- Chiffres ronds qui ont l'air inventés
- Détails manquants qui le rendraient réel

**Montées en précision :**

| Vague | Précis |
|-------|----------|
| Gagnez du temps | Gagnez 4 heures par semaine |
| De nombreux clients | 2 847 équipes |
| Des résultats rapides | Des résultats en 14 jours |
| Améliorez votre workflow | Divisez par deux votre temps de reporting |
| Un super support | Réponse en moins de 2 heures |

**Problèmes de précision courants :**
- Des adjectifs qui font le travail que des noms devraient faire
- Des bénéfices sans quantification
- Des résultats sans échéance
- Des affirmations sans exemples concrets

**Processus :**
1. Surligner les mots et expressions vagues
2. Demander « Peut-on être plus précis ? »
3. Ajouter des chiffres, des échéances ou des exemples
4. Supprimer le contenu qui ne peut pas être rendu précis (c'est sans doute du remplissage)

**Après cette passe :** Revenir à Prouve-le, Et alors, Voix et ton, puis Clarté.

---

### Passe 6 : Émotion accentuée (Heightened Emotion)

**Focus :** Le copy fait-il ressentir quelque chose au lecteur ?

**Quoi vérifier :**
- Langage plat, purement informatif
- Déclencheurs émotionnels manquants
- Points de douleur mentionnés mais pas ressentis
- Aspirations énoncées mais pas évoquées

**Dimensions émotionnelles à considérer :**
- La douleur de la situation actuelle
- La frustration face aux alternatives
- La peur de rater quelque chose (FOMO)
- Le désir de transformation
- La fierté de faire des choix malins
- Le soulagement d'avoir résolu le problème

**Techniques pour accentuer l'émotion :**
- Peindre l'état « avant » de façon vivante
- Utiliser un langage sensoriel
- Raconter des micro-histoires
- Faire référence à des expériences partagées
- Poser des questions qui suscitent la réflexion

**Processus :**
1. Lire pour l'impact émotionnel — est-ce que ça vous touche ?
2. Identifier les sections plates qui devraient résonner
3. Ajouter de la texture émotionnelle en restant authentique
4. S'assurer que l'émotion sert le message (pas de manipulation)

**Après cette passe :** Revenir à Précision, Prouve-le, Et alors, Voix et ton, puis Clarté.

---

### Passe 7 : Zéro risque (Zero Risk)

**Focus :** A-t-on supprimé tous les freins à l'action ?

**Quoi vérifier :**
- Friction près des CTA
- Objections sans réponse
- Signaux de confiance manquants
- Étapes suivantes peu claires
- Coûts cachés ou mauvaises surprises

**Réducteurs de risque à chercher :**
- Garanties satisfait ou remboursé
- Free trials
- « Sans carte bancaire »
- « Annulez à tout moment »
- Preuve sociale près du CTA
- Attentes claires sur ce qui se passe ensuite
- Garanties de confidentialité

**Problèmes de risque courants :**
- Le CTA demande un engagement sans avoir gagné la confiance
- Des objections soulevées mais pas traitées
- Des mentions en petits caractères qui sèment le doute
- Un « Contactez-nous » vague au lieu d'une étape suivante claire

**Processus :**
1. Se concentrer sur les sections près des CTA
2. Lister chaque raison pour laquelle quelqu'un pourrait hésiter
3. Vérifier si le copy traite chaque préoccupation
4. Ajouter des inversions de risque ou des signaux de confiance au besoin

**Après cette passe :** Repasser une dernière fois par toutes les passes précédentes : Émotion accentuée, Précision, Prouve-le, Et alors, Voix et ton, Clarté.

---

## Notation par panel d'experts

À utiliser après les sept passes pour une porte de qualité supplémentaire. Pour du copy à fort enjeu (landing pages, emails de lancement, pages de vente), une relecture multi-personas attrape des problèmes qu'un seul point de vue manque.

### Comment ça marche

1. **Assembler 3 à 5 personas experts** pertinents pour le type de copy
2. **Chaque persona note le copy de 1 à 10** sur son domaine d'expertise
3. **Collecter des critiques précises** — pas juste des notes, mais quoi corriger
4. **Réviser sur la base des retours** — traiter d'abord les domaines aux notes les plus basses
5. **Re-noter après révisions** — itérer jusqu'à ce que tous les personas notent 7+, avec une moyenne de 8+ sur le panel

### Panels d'experts recommandés

**Copy de landing page :**
- Copywriter de conversion (clarté, force du CTA, hiérarchie des bénéfices)
- UX writer (scannabilité, charge cognitive, parcours utilisateur)
- Persona du client cible (est-ce que ça me parle ? est-ce que j'y crois ?)
- Brand strategist (cohérence de la voix, justesse du positionnement)

**Séquence email :**
- Spécialiste email marketing (objets, optimisation taux d'ouverture/clic)
- Copywriter (hooks, storytelling, persuasion)
- Analyste filtres anti-spam (red flags de délivrabilité, mots déclencheurs)
- Persona du client cible (pertinence, valeur, risque de désinscription)

**Page de vente / format long :**
- Copywriter direct response (structure de l'offre, traitement des objections, urgence)
- Persona de l'acheteur sceptique (trous de preuve, problèmes de confiance, red flags)
- Éditeur (fluidité, lisibilité, concision)
- Spécialiste SEO (couverture des mots-clés, alignement avec l'intention de recherche)

### Grille de notation

| Note | Signification |
|-------|---------|
| 9-10 | Prêt à publier. Aucune amélioration significative. |
| 7-8 | Solide. Retouches mineures uniquement. |
| 5-6 | Fonctionnel mais avec des trous clairs. Une passe de plus est nécessaire. |
| 3-4 | Problèmes importants. Révision majeure nécessaire. |
| 1-2 | Fondamentalement cassé. Revoir l'approche. |

### Quand l'utiliser

- **Toujours** pour le copy de lancement, les pages de pricing et les landing pages à fort trafic
- **Recommandé** pour les séquences email, les pages de vente et le copy d'annonces
- **Optionnel** pour les articles de blog, le contenu social et la doc interne
- **À sauter** pour les mises à jour rapides, les éditions mineures et le contenu à faible enjeu

---

## Vérifications d'édition en passe rapide

À utiliser pour des relectures plus rapides quand un processus complet à sept passes n'est pas nécessaire.

### Vérifications au niveau du mot

**Couper ces mots :**
- Très, vraiment, extrêmement, incroyablement (intensificateurs faibles)
- Juste, en fait, fondamentalement (remplissage)
- Afin de (utiliser « pour »)
- Que (souvent inutile)
- Choses, trucs (vagues)

**Remplacer ceux-ci :**

| Faible | Fort |
|------|--------|
| Utiliser (utilize) | Utiliser/Servir |
| Mettre en œuvre | Mettre en place |
| Capitaliser sur (leverage) | Utiliser |
| Faciliter | Aider |
| Innovant | Nouveau |
| Robuste | Solide |
| Sans couture (seamless) | Fluide |
| À la pointe (cutting-edge) | Nouveau/Moderne |

**Surveiller :**
- Les adverbes (généralement inutiles)
- La voix passive (basculer en active)
- Les nominalisations (verbe → nom : « prendre une décision » → « décider »)

### Vérifications au niveau de la phrase

- Une idée par phrase
- Varier la longueur des phrases (mélanger courtes et longues)
- Mettre l'information importante en tête
- Max 3 conjonctions par phrase
- Pas plus de 25 mots (en général)

### Vérifications au niveau du paragraphe

- Un sujet par paragraphe
- Paragraphes courts (2-4 phrases pour le web)
- Phrases d'ouverture fortes
- Enchaînement logique entre paragraphes
- Du blanc pour la scannabilité

---

## Checklist d'édition de copy

Pour une dernière passe de QA avant de livrer les modifications, parcourez la checklist complète dans [references/checklist.md](references/checklist.md) — couvrant les sept passes plus les éléments de pré-démarrage et de vérification finale.

---

## Problèmes de copy courants & correctifs

### Problème : Mur de fonctionnalités
**Symptôme :** Liste de ce que fait le produit sans dire pourquoi c'est important
**Correctif :** Ajouter « ce qui veut dire... » après chaque fonctionnalité pour faire le pont vers les bénéfices

### Problème : Langue de bois corporate
**Symptôme :** « Capitaliser sur les synergies pour optimiser les résultats »
**Correctif :** Demander « Comment un humain dirait-il ça ? » et utiliser ces mots-là

### Problème : Ouverture faible
**Symptôme :** Commencer par l'historique de l'entreprise ou des phrases vagues
**Correctif :** Attaquer par le problème du lecteur ou le résultat désiré

### Problème : CTA enterré
**Symptôme :** La demande arrive après trop de mise en bouche, ou n'est pas claire
**Correctif :** Rendre le CTA évident, tôt et répété

### Problème : Aucune preuve
**Symptôme :** « Nos clients nous adorent » sans aucune preuve
**Correctif :** Ajouter des témoignages précis, des chiffres ou des références de cas

### Problème : Affirmations génériques
**Symptôme :** « Nous aidons les entreprises à croître »
**Correctif :** Préciser qui, comment et de combien

### Problème : Audiences mélangées
**Symptôme :** Le copy essaie de parler à tout le monde, ne résonne avec personne
**Correctif :** Choisir une audience et s'adresser directement à elle

### Problème : Surcharge de fonctionnalités
**Symptôme :** Lister chaque capacité, submerger le lecteur
**Correctif :** Se concentrer sur 3-5 bénéfices clés qui comptent le plus pour l'audience

---

## Travailler avec les passes de copy

Quand l'édition est collaborative :

1. **Faire une passe et présenter les constats** — Montrer ce que vous avez trouvé, pourquoi c'est un problème
2. **Recommander des modifications précises** — Ne pas seulement identifier les problèmes ; proposer des solutions
3. **Demander le copy mis à jour** — Laisser l'auteur prendre les décisions finales
4. **Vérifier les passes précédentes** — Après chaque round de modifications, revérifier les passes antérieures
5. **Répéter jusqu'à ce que ce soit propre** — Continuer jusqu'à ce qu'une passe complète ne trouve plus aucun nouveau problème

Ce processus itératif garantit que chaque modification ne crée pas de nouveau problème, tout en respectant la propriété de l'auteur sur son copy.

---

## Références

- [Alternatives en anglais simple](references/plain-english-alternatives.md) : remplacer des mots complexes par des alternatives plus simples
- [Rafraîchissement de contenu](references/content-refresh.md) : checklist complète, matrice rafraîchir vs. réécrire, et guide de cadence
- [Checklist d'édition de copy](references/checklist.md) : checklist QA complète sur les sept passes

---

## Édition par rafraîchissement de contenu

L'édition de copy n'est pas réservée au nouveau contenu. Les pages existantes se dégradent avec le temps — stats obsolètes, exemples périmés, voix de marque qui a dérivé. Utilisez le cadre de rafraîchissement de contenu quand le trafic décline, que les données sont périmées ou que le produit a changé.

**Pour la checklist de rafraîchissement complète, la matrice de décision rafraîchir vs. réécrire et le guide de cadence** : voir [references/content-refresh.md](references/content-refresh.md)

---

## Questions spécifiques à la tâche

1. Quel est l'objectif de ce copy ? (Notoriété, conversion, rétention)
2. Quelle action les lecteurs devraient-ils faire ?
3. Y a-t-il des préoccupations spécifiques ou des problèmes connus ?
4. Quelles preuves/éléments avez-vous à disposition ?
5. S'agit-il de nouveau copy ou du rafraîchissement d'un contenu existant ?

---

## Skills associés

- **copywriting** : pour écrire du nouveau copy de zéro (utilisez ce skill pour éditer une fois votre premier jet terminé)
- **cro** : pour une optimisation de page plus large au-delà du copy
- **marketing-psychology** : pour comprendre pourquoi certaines modifications améliorent la conversion
- **ab-testing** : pour tester des variantes de copy

---

## Quand utiliser chaque skill

| Tâche | Skill à utiliser |
|------|--------------|
| Écrire le copy d'une nouvelle page de zéro | copywriting |
| Relire et améliorer du copy existant | copy-editing (ce skill) |
| Éditer du copy que vous venez d'écrire | copy-editing (ce skill) |
| Changements structurels ou stratégiques de page | cro |
