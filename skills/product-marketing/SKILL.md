---
name: product-marketing
description: "À utiliser quand l'utilisateur veut créer ou mettre à jour son document de contexte product marketing. Aussi quand il mentionne « contexte produit », « contexte marketing », « product context », « marketing context », « mettre en place le contexte », « positionnement », « positioning », « qui est ma cible », « décrire mon produit », « ICP », « ideal customer profile », « profil client idéal », ou veut éviter de répéter des informations fondamentales d'une tâche marketing à l'autre. À utiliser au début de tout nouveau projet avant d'utiliser les autres skills marketing — il crée `.agents/product-marketing.md` que tous les autres skills consultent pour le contexte produit, audience et positionnement."
metadata:
  version: 2.0.0
---

# Contexte Product Marketing

Vous aidez les utilisateurs à créer et maintenir un document de contexte product marketing. Il capture les informations fondamentales de positionnement et de messaging que les autres skills marketing consultent, pour que les utilisateurs ne se répètent pas.

Le document est stocké dans `.agents/product-marketing.md`.

## Workflow

### Étape 1 : vérifier l'existence d'un contexte

D'abord, vérifier si `.agents/product-marketing.md` existe déjà. Vérifier aussi `.claude/product-marketing.md` et l'ancien nom de fichier `product-marketing-context.md` (dans `.agents/` ou `.claude/`) pour les anciens setups — si trouvé ailleurs que `.agents/product-marketing.md`, proposer de le déplacer vers l'emplacement canonique.

**S'il existe :**
- Le lire et résumer ce qui est capturé
- Demander quelles sections l'utilisateur veut mettre à jour
- Ne rassembler les infos que pour ces sections

**S'il n'existe pas, proposer deux options :**

1. **Auto-ébauche depuis la codebase** (recommandé) : vous étudiez le repo — README, landing pages, copy marketing, package.json, etc. — et ébauchez une V1 du document de contexte. L'utilisateur revoit ensuite, corrige et comble les manques. C'est plus rapide que de partir de zéro.

2. **Partir de zéro** : parcourir chaque section de façon conversationnelle, en rassemblant les infos une section à la fois.

La plupart des utilisateurs préfèrent l'option 1. Après avoir présenté l'ébauche, demander : « Qu'est-ce qui doit être corrigé ? Qu'est-ce qui manque ? »

### Étape 2 : rassembler l'information

**Si auto-ébauche :**
1. Lire la codebase : README, landing pages, copy marketing, pages « à propos », méta-descriptions, package.json, toute doc existante
2. Ébaucher toutes les sections d'après ce que vous trouvez
3. Présenter l'ébauche et demander ce qui doit être corrigé ou ce qui manque
4. Itérer jusqu'à satisfaction de l'utilisateur

**Si vous partez de zéro :**
Parcourir chaque section ci-dessous de façon conversationnelle, une à la fois. Ne pas balancer toutes les questions d'un coup.

Pour chaque section :
1. Expliquer brièvement ce que vous capturez
2. Poser les questions pertinentes
3. Confirmer l'exactitude
4. Passer à la suivante

Poussez pour obtenir le langage client mot pour mot — les formulations exactes ont plus de valeur que des descriptions léchées, car elles reflètent la façon dont les clients pensent et parlent réellement, ce qui rend le copy plus résonnant.

---

## Sections à capturer

### 1. Vue d'ensemble du produit
- Description en une ligne
- Ce qu'il fait (2-3 phrases)
- Catégorie de produit (sur quelle « étagère » vous êtes — comment les clients vous cherchent)
- Type de produit (SaaS, marketplace, e-commerce, service, etc.)
- Modèle économique et pricing

### 2. Audience cible
- Type d'entreprise cible (secteur, taille, stade)
- Décideurs cibles (rôles, départements)
- Cas d'usage principal (le problème principal que vous résolvez)
- Jobs to be done (2-3 choses pour lesquelles les clients vous « recrutent »)
- Cas d'usage ou scénarios spécifiques

### 3. Personas (B2B uniquement)
Si plusieurs parties prenantes interviennent dans l'achat, capturer pour chacune :
- User, Champion, Décideur, Acheteur financier, Influenceur technique
- Ce qui compte pour chacun, son défi, et la valeur que vous lui promettez

### 4. Problèmes & points de douleur
- Défi central que les clients rencontrent avant de vous trouver
- Pourquoi les solutions actuelles ne suffisent pas
- Ce que ça leur coûte (temps, argent, opportunités)
- Tension émotionnelle (stress, peur, doute)

### 5. Paysage concurrentiel
- **Concurrents directs** : même solution, même problème (ex. Calendly vs SavvyCal)
- **Concurrents secondaires** : solution différente, même problème (ex. Calendly vs la planification de Superhuman)
- **Concurrents indirects** : approche conflictuelle (ex. Calendly vs un assistant personnel)
- En quoi chacun ne suffit pas pour les clients

### 6. Différenciation
- Différenciateurs clés (capacités qui manquent aux alternatives)
- Comment vous le résolvez différemment
- Pourquoi c'est mieux (bénéfices)
- Pourquoi les clients vous choisissent plutôt que les alternatives

### 7. Objections & anti-personas
- Top 3 des objections entendues en vente et comment les traiter
- Qui n'est PAS un bon fit (anti-persona)

### 8. Dynamiques de bascule (switching)
Les Quatre Forces du JTBD :
- **Push** : quelles frustrations les éloignent de la solution actuelle
- **Pull** : qu'est-ce qui les attire vers vous
- **Habit** : qu'est-ce qui les maintient coincés sur l'approche actuelle
- **Anxiety** : qu'est-ce qui les inquiète à propos du changement

### 9. Langage client
- Comment les clients décrivent le problème (mot pour mot)
- Comment ils décrivent votre solution (mot pour mot)
- Mots/expressions à utiliser
- Mots/expressions à éviter
- Glossaire des termes spécifiques au produit

### 10. Voix de marque
- Ton (professionnel, décontracté, joueur, etc.)
- Style de communication (direct, conversationnel, technique)
- Personnalité de marque (3-5 adjectifs)

### 11. Proof points
- Métriques ou résultats clés à citer
- Clients/logos notables
- Extraits de témoignages
- Thèmes de valeur principaux et preuves à l'appui

### 12. Objectifs
- Objectif business principal
- Action de conversion clé (ce que vous voulez que les gens fassent)
- Métriques actuelles (si connues)

---

## Étape 3 : créer le document

Après avoir rassemblé l'information, créer `.agents/product-marketing.md` avec cette structure :

```markdown
# Product Marketing Context

*Last updated: [date]*

## Product Overview
**One-liner:**
**What it does:**
**Product category:**
**Product type:**
**Business model:**

## Target Audience
**Target companies:**
**Decision-makers:**
**Primary use case:**
**Jobs to be done:**
-
**Use cases:**
-

## Personas
| Persona | Cares about | Challenge | Value we promise |
|---------|-------------|-----------|------------------|
| | | | |

## Problems & Pain Points
**Core problem:**
**Why alternatives fall short:**
-
**What it costs them:**
**Emotional tension:**

## Competitive Landscape
**Direct:** [Competitor] — falls short because...
**Secondary:** [Approach] — falls short because...
**Indirect:** [Alternative] — falls short because...

## Differentiation
**Key differentiators:**
-
**How we do it differently:**
**Why that's better:**
**Why customers choose us:**

## Objections
| Objection | Response |
|-----------|----------|
| | |

**Anti-persona:**

## Switching Dynamics
**Push:**
**Pull:**
**Habit:**
**Anxiety:**

## Customer Language
**How they describe the problem:**
- "[verbatim]"
**How they describe us:**
- "[verbatim]"
**Words to use:**
**Words to avoid:**
**Glossary:**
| Term | Meaning |
|------|---------|
| | |

## Brand Voice
**Tone:**
**Style:**
**Personality:**

## Proof Points
**Metrics:**
**Customers:**
**Testimonials:**
> "[quote]" — [who]
**Value themes:**
| Theme | Proof |
|-------|-------|
| | |

## Goals
**Business goal:**
**Conversion action:**
**Current metrics:**
```

---

## Étape 4 : confirmer et sauvegarder

- Montrer le document complété
- Demander si quelque chose doit être ajusté
- Sauvegarder dans `.agents/product-marketing.md`
- Leur dire : « Les autres skills marketing utiliseront désormais ce contexte automatiquement. Lancez `/product-marketing` à tout moment pour le mettre à jour. »

---

## Astuces

- **Soyez spécifique** : demandez « Quelle est la frustration n°1 qui les amène à vous ? » et pas « Quel problème résolvez-vous ? »
- **Capturez les mots exacts** : le langage client bat les descriptions léchées
- **Demandez des exemples** : « Pouvez-vous me donner un exemple ? » débloque de meilleures réponses
- **Validez au fil de l'eau** : résumez chaque section et confirmez avant de continuer
- **Sautez ce qui ne s'applique pas** : tous les produits n'ont pas besoin de toutes les sections (ex. les Personas pour le B2C)
