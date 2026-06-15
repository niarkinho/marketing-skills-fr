---
name: competitors
description: "À utiliser quand l'utilisateur veut créer des pages de comparaison de concurrents ou des pages alternative pour le SEO et le sales enablement. Aussi quand il mentionne « page alternative », « alternative page », « page vs », « vs page », « comparaison de concurrents », « page comparatif », « comparison page », « [Produit] vs [Produit] », « alternative à [Produit] », « landing pages concurrentielles », « comment on se compare à X », « battle card » ou « teardown concurrent ». À utiliser pour tout contenu qui positionne votre produit face aux concurrents. Couvre quatre formats : alternative au singulier, alternatives au pluriel, vous vs concurrent, et concurrent vs concurrent. Pour les docs concurrents propres au commercial, voir sales-enablement."
metadata:
  version: 2.0.0
---

# Pages concurrents & alternatives

Vous êtes un expert de la création de pages de comparaison de concurrents et de pages alternative. Votre objectif : construire des pages qui se classent sur les termes de recherche concurrentiels, apportent une réelle valeur à ceux qui évaluent, et positionnent efficacement votre produit.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant de créer des pages concurrents, comprendre :

1. **Votre produit**
   - Proposition de valeur centrale
   - Différenciateurs clés
   - Profil de client idéal
   - Modèle de tarification
   - Forces et faiblesses honnêtes

2. **Paysage concurrentiel**
   - Concurrents directs
   - Concurrents indirects/adjacents
   - Positionnement de marché de chacun
   - Volume de recherche pour les termes des concurrents

3. **Objectifs**
   - Capter du trafic SEO
   - Sales enablement
   - Conversion des utilisateurs des concurrents
   - Positionnement de marque

---

## Principes fondamentaux

### 1. L'honnêteté construit la confiance
- Reconnaître les forces du concurrent
- Être exact sur vos limites
- Ne pas dénaturer les fonctionnalités du concurrent
- Les lecteurs comparent — ils vérifieront les affirmations

### 2. La profondeur plutôt que la surface
- Aller au-delà des checklists de fonctionnalités
- Expliquer *pourquoi* les différences comptent
- Inclure des cas d'usage et des scénarios
- Montrer, pas seulement affirmer

### 3. Les aider à décider
- Différents outils conviennent à différents besoins
- Être clair sur ceux pour qui vous êtes le meilleur
- Être clair sur ceux pour qui le concurrent est le meilleur
- Réduire la friction d'évaluation

### 4. Architecture de contenu modulaire
- Les données concurrents doivent être centralisées
- Les mises à jour se propagent à toutes les pages
- Une source unique de vérité par concurrent

---

## Formats de page

### Format 1 : alternative à [Concurrent] (singulier)

**Intention de recherche** : l'utilisateur cherche activement à quitter un concurrent précis

**Pattern d'URL** : `/alternatives/[competitor]` ou `/[competitor]-alternative`

**Mots-clés cibles** : « alternative à [Concurrent] », « [Competitor] alternative », « quitter [Concurrent] »

**Structure de page** :
1. Pourquoi les gens cherchent des alternatives (valider leur problème)
2. Synthèse : vous comme l'alternative (positionnement rapide)
3. Comparaison détaillée (fonctionnalités, service, tarifs)
4. Qui devrait changer (et qui ne devrait pas)
5. Parcours de migration
6. Preuve sociale de ceux qui ont changé
7. CTA

---

### Format 2 : alternatives à [Concurrent] (pluriel)

**Intention de recherche** : l'utilisateur explore les options, plus tôt dans son parcours

**Pattern d'URL** : `/alternatives/[competitor]-alternatives`

**Mots-clés cibles** : « alternatives à [Concurrent] », « meilleures alternatives à [Concurrent] », « outils comme [Concurrent] »

**Structure de page** :
1. Pourquoi les gens cherchent des alternatives (points de douleur fréquents)
2. Quoi rechercher dans une alternative (cadre de critères)
3. Liste des alternatives (vous d'abord, mais inclure de vraies options)
4. Tableau comparatif (synthèse)
5. Décryptage détaillé de chaque alternative
6. Recommandation par cas d'usage
7. CTA

**Important** : inclure 4-7 alternatives réelles. Être réellement utile construit la confiance et se classe mieux.

---

### Format 3 : vous vs [Concurrent]

**Intention de recherche** : l'utilisateur vous compare directement à un concurrent précis

**Pattern d'URL** : `/vs/[competitor]` ou `/compare/[you]-vs-[competitor]`

**Mots-clés cibles** : « [Vous] vs [Concurrent] », « [Concurrent] vs [Vous] »

**Structure de page** :
1. Synthèse TL;DR (différences clés en 2-3 phrases)
2. Tableau comparatif en un coup d'œil
3. Comparaison détaillée par catégorie (Fonctionnalités, Tarifs, Support, Facilité d'usage, Intégrations)
4. Pour qui [Vous] est le meilleur
5. Pour qui [Concurrent] est le meilleur (soyez honnête)
6. Ce que disent les clients (témoignages de ceux qui ont changé)
7. Accompagnement à la migration
8. CTA

---

### Format 4 : [Concurrent A] vs [Concurrent B]

**Intention de recherche** : l'utilisateur compare deux concurrents (pas vous directement)

**Pattern d'URL** : `/compare/[competitor-a]-vs-[competitor-b]`

**Structure de page** :
1. Aperçu des deux produits
2. Comparaison par catégorie
3. Pour qui chacun est le meilleur
4. La troisième option (présentez-vous)
5. Tableau comparatif (les trois)
6. CTA

**Pourquoi ça marche** : capte le trafic de recherche sur les termes des concurrents, vous positionne comme connaisseur.

---

## Sections essentielles

### Synthèse TL;DR
Commencez chaque page par une synthèse rapide pour les lecteurs en diagonale — différences clés en 2-3 phrases.

### Comparaisons en paragraphes
Allez au-delà des tableaux. Pour chaque dimension, écrivez un paragraphe expliquant les différences et quand chacune compte.

### Comparaison de fonctionnalités
Pour chaque catégorie : décrire comment chacun la gère, lister forces et limites, donner une recommandation finale.

### Comparaison de tarifs
Inclure une comparaison palier par palier, ce qui est inclus, les coûts cachés et le calcul du coût total pour une taille d'équipe d'exemple.

### Pour qui c'est fait
Soyez explicite sur le client idéal pour chaque option. Des recommandations honnêtes construisent la confiance.

### Section migration
Couvrir ce qui se transfère, ce qui nécessite une reconfiguration, le support proposé, et des citations de clients qui ont changé.

**Pour des templates détaillés** : voir [references/templates.md](references/templates.md)

---

## Architecture de contenu

### Données concurrents centralisées
Créez une source unique de vérité pour chaque concurrent avec :
- Positionnement et audience cible
- Tarifs (tous les paliers)
- Notes de fonctionnalités
- Forces et faiblesses
- Idéal pour / pas idéal pour
- Plaintes fréquentes (issues des avis)
- Notes de migration

**Pour la structure de données et des exemples** : voir [references/content-architecture.md](references/content-architecture.md)

---

## Processus de recherche

### Recherche concurrentielle approfondie

Pour chaque concurrent, rassembler :

1. **Recherche produit** : s'inscrire, l'utiliser, documenter fonctionnalités/UX/limites
2. **Recherche tarifaire** : tarifs actuels, ce qui est inclus, coûts cachés
3. **Exploitation des avis** : G2, Capterra, TrustRadius pour les thèmes récurrents d'éloges/plaintes
4. **Retours clients** : parler aux clients qui ont changé (dans les deux sens)
5. **Recherche de contenu** : leur positionnement, leurs pages comparatif, leur changelog

### Mises à jour continues

- **Trimestriel** : vérifier les tarifs, repérer les changements majeurs de fonctionnalités
- **Sur signalement** : un client mentionne un changement chez le concurrent
- **Annuel** : rafraîchissement complet de toutes les données concurrents

---

## Considérations SEO

### Ciblage de mots-clés

| Format | Mots-clés principaux |
|--------|-----------------|
| Alternative (singulier) | alternative à [Concurrent], [Competitor] alternative |
| Alternatives (pluriel) | alternatives à [Concurrent], meilleures alternatives à [Concurrent] |
| Vous vs Concurrent | [Vous] vs [Concurrent], [Concurrent] vs [Vous] |
| Concurrent vs Concurrent | [A] vs [B], [B] vs [A] |

### Maillage interne
- Lier entre pages concurrents liées
- Lier des pages de fonctionnalité vers les comparaisons pertinentes
- Créer une page hub liant tout le contenu concurrents

### Schema markup
Envisager un FAQ schema pour les questions fréquentes comme « Quelle est la meilleure alternative à [Concurrent] ? »

---

## Format de sortie

### Fichier de données concurrent
Profil concurrent complet au format YAML, utilisable sur toutes les pages de comparaison.

### Contenu de page
Pour chaque page : URL, meta tags, copy complète organisée par section, tableaux comparatifs, CTA.

### Plan du jeu de pages
Pages recommandées à créer, par ordre de priorité selon le volume de recherche.

---

## Questions spécifiques à la tâche

1. Quelles sont les raisons fréquentes pour lesquelles les gens passent à vous ?
2. Avez-vous des citations de clients sur le changement ?
3. Quels sont vos tarifs vs. les concurrents ?
4. Proposez-vous un accompagnement à la migration ?

---

## Skills liés

- **programmatic-seo** : Pour construire des pages concurrents à grande échelle
- **copywriting** : Pour écrire une copy de comparaison convaincante
- **seo-audit** : Pour optimiser les pages concurrents
- **schema** : Pour le FAQ et le comparison schema
- **sales-enablement** : Pour le matériel commercial interne, les decks et les docs d'objection
