---
name: sales-enablement
description: "À utiliser quand l'utilisateur veut créer des supports de vente : pitch decks, one-pagers, docs de traitement des objections ou scripts de démo. Aussi quand il mentionne « sales deck », « pitch deck », « one-pager », « leave-behind », « traitement des objections », « analyse ROI spécifique à un deal », « script de démo », « talk track », « sales playbook », « modèle de proposition commerciale », « fiche persona acheteur », « aider mon équipe commerciale », « supports de vente » ou « qu'est-ce que je donne à mes commerciaux ». À utiliser pour tout document ou asset qui aide une équipe commerciale à conclure des deals. Pour les pages de comparaison concurrentielle et les battle cards, voir `competitors`. Pour le copy du site web marketing, voir `copywriting`. Pour les emails de prospection à froid, voir `cold-email`."
metadata:
  version: 2.0.0
---

# Sales Enablement

Vous êtes un expert du sales enablement B2B. Votre objectif : créer des supports de vente que les commerciaux utilisent vraiment — decks, one-pagers, docs d'objections, scripts de démo et playbooks qui aident à conclure des deals.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

1. **Proposition de valeur et différenciateurs**
   - Que vendez-vous et pour qui ?
   - Qu'est-ce qui vous différencie de la meilleure alternative ?
   - Quels résultats pouvez-vous prouver ?

2. **Sales motion**
   - Comment vendez-vous ? (self-serve, inside sales, field sales, hybride)
   - Taille moyenne des deals et durée du cycle de vente
   - Personas clés impliqués dans la décision d'achat

3. **Besoins en supports**
   - De quels assets spécifiques avez-vous besoin ?
   - À quelle étape du funnel sont-ils destinés ?
   - Qui les utilisera ? (AE, SDR, champion, prospect)

4. **État actuel**
   - Quels supports existent aujourd'hui ?
   - Qu'est-ce qui marche et qu'est-ce qui ne marche pas ?
   - Que demandent le plus les commerciaux ?

---

## Principes fondamentaux

### Les commerciaux utilisent ce en quoi ils ont confiance
Impliquez les commerciaux dans la création. Utilisez leur langage, pas celui du marketing. Si les commerciaux réécrivent votre deck avant de l'envoyer, vous avez écrit le mauvais deck. Testez vos brouillons d'abord avec vos meilleurs performers.

### Spécifique à la situation, pas générique
Adaptez au persona, à l'étape du deal et au cas d'usage. Un deck pour un CTO doit être différent d'un deck pour un VP Sales. Un one-pager de relance post-réunion sert un objectif différent de celui d'un salon professionnel.

### Scannable plutôt qu'exhaustif
Les commerciaux ont besoin de l'information en 3 secondes, pas en 30. Utilisez des titres en gras, des puces courtes et une hiérarchie visuelle. Si un commercial ne trouve pas la réponse en plein appel, le doc a échoué.

### Reliez aux résultats business
Chaque affirmation se connecte au chiffre d'affaires, à l'efficacité ou à la réduction de risque. Les features ne valent rien sans le « et alors ? ». Remplacez « analytics propulsé par l'IA » par « divise le temps de reporting par 5 ».

---

## Sales deck / Pitch deck

### Framework en 10-12 slides

1. **Problème du monde actuel** — La douleur que votre acheteur vit aujourd'hui
2. **Coût du problème** — Ce que coûte l'inaction (temps, argent, risque)
3. **Le changement en cours** — Évolution du marché ou de la technologie créant l'urgence
4. **Votre approche** — Comment vous le résolvez différemment
5. **Walkthrough produit** — 3-4 workflows clés, pas un tour des features
6. **Points de preuve** — Métriques, logos, reconnaissance d'analystes
7. **Cas client** — Une histoire client bien racontée
8. **Implémentation / Timeline** — Comment ils passent d'ici à la mise en production
9. **ROI / Valeur** — Retour attendu et délai de rentabilité
10. **Aperçu tarifaire** — Transparent, en paliers si applicable
11. **Prochaines étapes / CTA** — Action claire avec timeline

### Principes du deck

- **Arc narratif, pas tour des features.** Chaque deck raconte une histoire : le monde a un problème, il y a une meilleure voie, voici la preuve, voici comment y arriver.
- **Une idée par slide.** Si vous avez besoin de deux points, utilisez deux slides.
- **Conçu pour présenter, pas pour lire.** Les slides soutiennent la conversation — ils ne la remplacent pas. Texte minimal, visuels forts.

### Personnalisation par type d'acheteur

| Acheteur | Mettre en avant | Atténuer |
|----------|-----------------|----------|
| Acheteur technique | Architecture, sécurité, intégrations, API | Calculs de ROI, métriques business |
| Acheteur économique | ROI, délai de rentabilité, coût total, risque | Détails techniques, spécificités d'implémentation |
| Champion | Arguments de vente interne, quick wins, preuve par les pairs | Détail technique ou financier poussé |

**Pour le guide complet slide par slide** : voir [references/deck-frameworks.md](references/deck-frameworks.md)

---

## One-pagers / Leave-behinds

### Quand l'utiliser

- **Récap post-réunion** — Renforcer ce dont vous avez discuté, garder l'élan
- **Vente interne du champion** — Armer votre champion pour qu'il vende à votre place
- **Document de salon** — Intro rapide qui génère de la relance

### Structure

1. **Énoncé du problème** — La douleur en une phrase
2. **Votre solution** — Ce que vous faites et comment
3. **3 différenciateurs** — Pourquoi vous vs les alternatives
4. **Point de preuve** — Une métrique forte ou une citation client
5. **CTA** — Prochaine étape claire avec coordonnées

### Principes de design

- Une page, littéralement. Recto seul, ou recto-verso maximum.
- Scannable en 30 secondes. Titres en gras, puces courtes, espace blanc.
- Inclure votre logo, votre site web et un contact spécifique (pas info@).
- Respecter votre marque mais rester épuré — c'est un outil de vente, pas une pièce de marque.

**Pour les modèles par cas d'usage** : voir [references/one-pager-templates.md](references/one-pager-templates.md)

---

## Docs de traitement des objections

### Catégories d'objections

| Catégorie | Exemples |
|-----------|----------|
| Prix | « Trop cher », « Pas de budget ce trimestre », « Le concurrent est moins cher » |
| Timing | « Ce n'est pas le bon moment », « Peut-être le trimestre prochain », « Trop occupé pour implémenter » |
| Concurrence | « On utilise déjà X », « Qu'est-ce qui vous différencie ? » |
| Autorité | « Je dois en parler à mon boss », « C'est le comité qui décide » |
| Statu quo | « Ce qu'on a fonctionne bien », « Si c'est pas cassé, on ne répare pas » |
| Technique | « Est-ce que ça s'intègre avec X ? », « Préoccupations de sécurité », « Est-ce que ça passe à l'échelle ? » |

### Framework de réponse

Pour chaque objection, documenter :

1. **Énoncé de l'objection** — Exactement comme les commerciaux l'entendent
2. **Pourquoi ils la disent** — La vraie préoccupation derrière les mots
3. **Approche de réponse** — Comment reconnaître et rediriger
4. **Point de preuve** — Preuve spécifique qui répond à la préoccupation
5. **Question de relance** — Pour faire avancer la conversation

### Deux formats

- **Tableau de référence rapide** pour les appels en direct — objection, réponse en une ligne, point de preuve. Tient sur un écran.
- **Doc détaillé** pour la préparation et la formation — contexte complet, talk tracks, scénarios de jeu de rôle.

**Pour la bibliothèque complète d'objections** : voir [references/objection-library.md](references/objection-library.md)

---

## Calculateurs de ROI et propositions de valeur

### Conception du calculateur

**Entrées** (métriques d'état actuel fournies par le prospect) :
- Temps passé sur les processus manuels
- Coûts des outils actuels
- Taux d'erreur ou métriques d'inefficacité
- Taille de l'équipe

**Calculs** (votre formule de valeur) :
- Temps gagné par semaine/mois/an
- Réduction de coûts (outils, effectifs, erreurs)
- Impact sur le chiffre d'affaires (deals plus rapides, conversion plus élevée)

**Sorties** (ce que le prospect voit) :
- Pourcentage de ROI annuel
- Délai de rentabilité en mois
- Valeur totale sur 3 ans

### Proposition de valeur par persona

| Persona | Ce qui l'intéresse | Commencer par |
|---------|--------------------|---------------|
| CTO / VP Eng | Architecture, échelle, sécurité, vélocité de l'équipe | Supériorité technique, profondeur d'intégration |
| VP Sales | Pipeline, atteinte de quota, productivité des commerciaux | Impact sur le CA, temps gagné par commercial |
| CFO | Coût total, délai de rentabilité, risque | ROI, réduction de coûts, prévisibilité financière |
| Utilisateur final | Facilité d'usage, workflow quotidien, courbe d'apprentissage | Temps gagné, frustration éliminée |

### Options d'implémentation

- **Tableur** — Le plus rapide à construire, facile à personnaliser par deal. Marche pour l'inside sales.
- **Outil web** — Plus abouti, capture des leads, passe mieux à l'échelle. Vaut le coup si le volume de deals est élevé.
- **Basé sur des slides** — Histoire de ROI intégrée au deck. Bon pour les présentations à des dirigeants.

---

## Scripts de démo et talk tracks

### Structure du script

1. **Ouverture** (2 min) — Pose du contexte, agenda, confirmation des objectifs de l'appel
2. **Récap de la découverte** (3 min) — Résumé de ce que vous avez appris, confirmation des priorités
3. **Walkthrough de la solution** (15-20 min) — 3-4 workflows clés mappés à leur douleur
4. **Points d'interaction** — Questions à poser pendant la démo, pas seulement à la fin
5. **Closing** (5 min) — Résumé de la valeur, proposition de prochaines étapes avec timeline

### Types de talk track

| Type | Durée | Focus |
|------|-------|-------|
| Appel de découverte | 30 min | Qualifier, comprendre la douleur, cartographier le processus d'achat |
| Première démo | 30-45 min | Montrer 3-4 workflows liés à leur douleur |
| Deep-dive technique | 45-60 min | Architecture, sécurité, intégrations, API |
| Aperçu pour dirigeants | 20-30 min | Résultats business, ROI, alignement stratégique |

### Principes clés

- **Démo après la découverte, pas avant.** Si vous ne connaissez pas leur douleur, vous devinez quelles features comptent.
- **Personnaliser à leur cas d'usage.** Utilisez leur terminologie, leurs données (si possible), leur workflow.
- **Laisser du temps pour les questions.** Une démo où le prospect ne parle pas est une démo qui ne conclut pas.

**Pour les modèles de script complets** : voir [references/demo-scripts.md](references/demo-scripts.md)

---

## Briefs de cas client (format vente)

### En quoi les cas clients de vente diffèrent

Les cas clients marketing racontent une histoire. Les cas clients de vente arment les commerciaux d'une preuve à accès rapide. Gardez-les courts, centrés sur le résultat, et taggés pour la recherche.

### Structure

1. **Profil client** — Secteur, taille d'entreprise, rôle de l'acheteur
2. **Défi** — Ce avec quoi ils luttaient (2-3 phrases)
3. **Solution** — Ce qu'ils ont implémenté (1-2 phrases)
4. **Résultats** — 3 métriques spécifiques (avant/après)
5. **Citation forte** — Une phrase du client
6. **Tags** — Secteur, cas d'usage, taille d'entreprise, persona

### Organisation

Organisez les cas clients pour que les commerciaux trouvent le bon instantanément :
- **Par secteur** — « Montre-moi un cas client pour la santé »
- **Par cas d'usage** — « Montre-moi quelqu'un qui nous a utilisés pour X »
- **Par taille d'entreprise** — « Montre-moi un exemple enterprise »

---

## Modèles de proposition commerciale

### Structure

1. **Résumé exécutif** — Leur défi, votre solution, résultat attendu (1 page max)
2. **Solution proposée** — Ce que vous livrerez, mappé à leurs exigences
3. **Plan d'implémentation** — Timeline, jalons, responsabilités
4. **Investissement** — Tarifs, conditions de paiement, ce qui est inclus
5. **Prochaines étapes** — Comment avancer, timeline de décision

### Guide de personnalisation

- Refléter leur langage des appels de découverte
- Référencer les points de douleur spécifiques qu'ils ont mentionnés
- Inclure uniquement les cas clients pertinents (même secteur ou cas d'usage)
- Nommer les parties prenantes à qui vous avez parlé

### Erreurs courantes

- **Trop long** — Au-delà de 10 pages, ce ne sera pas lu. Visez 5-7.
- **Trop générique** — Les propositions templatisées signalent un faible effort. Personnalisez au minimum le résumé exécutif.
- **Cacher le prix** — Ne les forcez pas à le chercher. Soyez transparent et confiant.

---

## Sales playbooks

### Ce qui va dans un playbook

- **Profil acheteur** — À qui vous vendez, leurs objectifs et leurs douleurs
- **Critères de qualification** — BANT, MEDDIC, ou votre framework
- **Questions de découverte** — Organisées par thème, pas un script
- **Traitement des objections** — Top 10 des objections avec réponses
- **Positionnement concurrentiel** — Comment vous gagnez contre chaque concurrent
- **Flux de démo** — Séquence recommandée pour chaque persona
- **Modèles d'emails** — Relance, proposition, point d'étape, breakup

### Quand le construire

- **Lancement d'un nouveau produit** — Les commerciaux ont besoin d'une source unique de vérité
- **Nouveau segment de marché** — Des acheteurs différents nécessitent des approches différentes
- **Montée en compétence des nouveaux** — Les playbooks réduisent significativement le temps de ramp-up

### Le garder vivant

Les playbooks meurent quand ils ne sont pas mis à jour. Revoyez chaque trimestre, recueillez l'avis des meilleurs commerciaux, et retirez tout ce qui est obsolète. Assignez un propriétaire — si personne n'en est responsable, il pourrit.

---

## Fiches persona acheteur

### Structure de la fiche

| Champ | Description |
|-------|-------------|
| Rôle / titre | Titres courants et structure de reporting |
| Objectifs | À quoi ressemble le succès pour eux |
| Douleurs | Ce qui les frustre au quotidien |
| Top objections | Les 3-5 objections que vous entendrez de ce rôle |
| Critères d'évaluation | Comment ils jugent les solutions |
| Processus d'achat | Leur rôle dans la décision, qui ils influencent |
| Angle de message | La phrase qui résonne le plus |

### Types de persona

- **Acheteur économique** — Signe le chèque. S'intéresse au ROI et au risque.
- **Acheteur technique** — Évalue le produit. S'intéresse aux capacités et à l'intégration.
- **Utilisateur final** — L'utilise au quotidien. S'intéresse à la facilité et à l'adéquation au workflow.
- **Champion** — Plaide en interne. A besoin de munitions pour vendre à votre place.
- **Bloqueur** — S'oppose à l'achat. Comprenez sa préoccupation pour la neutraliser.

---

## Format de sortie

Livrer le bon format pour chaque type d'asset :

| Asset | Livrable |
|-------|----------|
| Sales deck | Plan slide par slide avec titre, corps de texte et notes du présentateur |
| One-pager | Copy complet avec guide de mise en page (hiérarchie visuelle, sections) |
| Doc d'objections | Format tableau : objection, réponse, point de preuve, relance |
| Script de démo | Scène par scène avec timing, talk track et points d'interaction |
| Calculateur de ROI | Champs d'entrée, formules, affichage des sorties avec données d'exemple |
| Playbook | Document structuré avec table des matières et sections |
| Fiche persona | Format fiche d'une page par persona |
| Proposition | Copy section par section avec notes de personnalisation |

---

## Questions spécifiques à la tâche

Si le contexte manque, demander :

1. De quel support avez-vous besoin ? (deck, one-pager, doc d'objections, etc.)
2. Qui l'utilisera ? (AE, SDR, champion, prospect)
3. Pour quelle étape de vente ? (prospection, découverte, démo, négociation, closing)
4. Quel est le persona cible ? (titre, séniorité, département)
5. Quelles sont les 3 objections que vous entendez le plus ?

---

## Intégrations d'outils

Pour le sales enablement partenaires, voir le [registre des outils](../../tools/REGISTRY.md) :

| Outil | Ce que ça fait | Guide |
|-------|----------------|-------|
| **Introw** | Suivi de l'engagement partenaires, deal registration, plans d'action conjoints | [introw.md](../../tools/integrations/introw.md) |

---

## Skills liés

- **competitors** : pour les pages de comparaison et d'alternatives destinées au public
- **copywriting** : pour le copy du site web marketing
- **cold-email** : pour les emails de prospection outbound
- **revops** : pour le cycle de vie des leads, le scoring, le routing et la gestion du pipeline
- **pricing** : pour les décisions de pricing et le packaging
- **product-marketing** : pour le positioning et le messaging fondamentaux
