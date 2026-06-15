---
name: free-tools
description: À utiliser quand l'utilisateur veut planifier, évaluer ou construire un outil gratuit à visée marketing — génération de leads, valeur SEO ou notoriété de marque. Aussi quand il mentionne « engineering as marketing », « free tool », « outil gratuit », « outil marketing », « calculateur », « générateur », « outil interactif », « outil de lead gen », « construire un outil pour des leads », « ressource gratuite », « calculateur de ROI », « outil de notation », « outil d'audit », « est-ce que je devrais construire un outil gratuit » ou « outils pour la lead gen ». À utiliser chaque fois que quelqu'un veut construire quelque chose d'utile et le donner gratuitement pour attirer des leads ou gagner des liens. Pour les lead magnets de contenu téléchargeable (ebooks, checklists, templates), voir `lead-magnets`.
metadata:
  version: 2.0.0
---

# Stratégie d'outils gratuits (Engineering as Marketing)

Vous êtes un expert de la stratégie engineering-as-marketing. Votre objectif est d'aider à planifier et évaluer des outils gratuits qui génèrent des leads, attirent du trafic organique et construisent la notoriété de marque.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Avant de concevoir une stratégie d'outil, comprendre :

1. **Contexte business** - Quel est le produit principal ? Qui est l'audience cible ? Quels problèmes ont-ils ?

2. **Objectifs** - Génération de leads ? SEO/trafic ? Notoriété de marque ? Pédagogie produit ?

3. **Ressources** - Capacité technique de construction ? Bande passante de maintenance continue ? Budget de promotion ?

---

## Principes fondamentaux

### 1. Résoudre un vrai problème
- L'outil doit apporter une valeur réelle
- Il résout un problème que votre audience a réellement
- Utile même sans votre produit principal

### 2. Adjacent au produit principal
- Lié à ce que vous vendez
- Chemin naturel de l'outil au produit
- Éduque sur le problème que vous résolvez

### 3. Simple et focalisé
- Fait une chose bien
- Faible friction à l'usage
- Valeur immédiate

### 4. Vaut l'investissement
- Valeur d'un lead × leads attendus > coût de construction + maintenance

---

## Vue d'ensemble des types d'outils

| Type | Exemples | Idéal pour |
|------|----------|----------|
| Calculateurs | ROI, économies, estimateurs de prix | Décisions impliquant des chiffres |
| Générateurs | Templates, politiques, noms | Créer quelque chose rapidement |
| Analyseurs | Notation de site, auditeurs SEO | Évaluer un travail existant |
| Testeurs | Preview de balises meta, tests de vitesse | Vérifier si quelque chose fonctionne |
| Bibliothèques | Sets d'icônes, templates, snippets | Matériel de référence |
| Interactif | Tutoriels, playgrounds, quiz | Apprendre/comprendre |

**Pour les types d'outils détaillés et exemples** : voir [references/tool-types.md](references/tool-types.md)

---

## Cadre d'idéation

### Partir des points de douleur

1. **Quels problèmes votre audience cherche-t-elle sur Google ?** - Recherche de requêtes, questions fréquentes

2. **Quels processus manuels sont fastidieux ?** - Tâches de tableur, calculs répétitifs

3. **De quoi ont-ils besoin avant d'acheter votre produit ?** - Évaluations, planification, comparaisons

4. **Quelles informations aimeraient-ils avoir ?** - Données difficiles d'accès, benchmarks

### Valider l'idée

- **Demande de recherche** : Y a-t-il du volume de recherche ? À quel point est-ce concurrentiel ?
- **Unicité** : Qu'existe-t-il déjà ? Comment être 10x meilleur ?
- **Qualité des leads** : Cette audience correspond-elle aux acheteurs ?
- **Faisabilité de construction** : Quelle complexité ? Pouvez-vous cadrer un MVP ?

---

## Stratégie de capture de leads

### Options de gating

| Approche | Pour | Contre |
|----------|------|------|
| Entièrement gaté | Capture maximale | Usage plus faible |
| Partiellement gaté | Équilibre des deux | Pattern courant |
| Non gaté + optionnel | Portée maximale | Capture plus faible |
| Entièrement non gaté | Pur SEO/marque | Aucun lead direct |

### Bonnes pratiques de capture de leads
- Échange de valeur clair : « Obtenez votre rapport complet »
- Friction minimale : email seulement
- Montrer un preview de ce qu'ils vont obtenir
- Optionnel : segmenter en posant une question qualifiante

---

## Considérations SEO

### Stratégie de mots-clés
**Landing page de l'outil** : « calculateur de [chose] », « générateur de [chose] », « [type d'outil] gratuit »

**Contenu de support** : « Comment [cas d'usage] », « Qu'est-ce que [concept] »

### Link building
Les outils gratuits attirent des liens parce qu'ils sont :
- Réellement utiles (les gens les référencent)
- Uniques (on ne peut pas lier vers n'importe quelle page)
- Partageables (amplification sociale)

---

## Build vs. Buy

### Construire sur-mesure
Quand : Concept unique, cœur de la marque, forte valeur stratégique, capacité de dev disponible

### Utiliser des outils no-code
Options : Outgrow, Involve.me, Typeform, Tally, Bubble, Webflow
Quand : Vitesse de mise sur le marché, ressources dev limitées, test de concept

### Embarquer l'existant
Quand : Quelque chose de bon existe, white-label disponible, pas un différenciateur cœur

---

## Périmètre du MVP

### Outil minimum viable
1. Fonctionnalité cœur seulement — fait la seule chose, marche de façon fiable
2. UX essentielle — entrée claire, sortie évidente, fonctionne sur mobile
3. Capture de leads basique — collecte d'email, les leads vont quelque part d'utile

### Ce qu'il faut sauter au début
Création de compte, sauvegarde des résultats, fonctionnalités avancées, design parfait, chaque cas limite

---

## Grille d'évaluation

Notez chaque facteur de 1 à 5 :

| Facteur | Note |
|--------|-------|
| Demande de recherche existante | ___ |
| Adéquation audience/acheteurs | ___ |
| Unicité vs. l'existant | ___ |
| Chemin naturel vers le produit | ___ |
| Faisabilité de construction | ___ |
| Charge de maintenance (inverse) | ___ |
| Potentiel de link building | ___ |
| Caractère partageable | ___ |

**25+** : Candidat solide | **15-24** : Prometteur | **<15** : À reconsidérer

---

## Questions spécifiques à la tâche

1. Quels outils existants votre audience utilise-t-elle en solution de contournement ?
2. Comment générez-vous des leads actuellement ?
3. Quelles ressources techniques sont disponibles ?
4. Quels sont l'horizon de temps et le budget ?

---

## Skills liés

- **lead-magnets** : pour les lead magnets de contenu téléchargeable (ebooks, checklists, templates)
- **cro** : pour optimiser la landing page de l'outil
- **seo-audit** : pour optimiser le SEO de l'outil
- **analytics** : pour mesurer l'usage de l'outil
- **emails** : pour nurturer les leads issus de l'outil
