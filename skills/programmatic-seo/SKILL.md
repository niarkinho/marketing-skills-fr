---
name: programmatic-seo
description: À utiliser quand l'utilisateur veut créer des pages orientées SEO à grande échelle à partir de templates et de données. Aussi quand il mentionne « programmatic SEO », « SEO programmatique », « pages template », « pages à grande échelle », « pages annuaire », « pages de localisation », « pages [mot-clé] + [ville] », « pages comparatif », « pages d'intégration », « créer beaucoup de pages pour le SEO », « pSEO », « générer 100 pages », « pages pilotées par les données » ou « landing pages en template ». À utiliser dès que quelqu'un veut créer de nombreuses pages similaires ciblant différents mots-clés ou localisations. Pour auditer des problèmes SEO existants, voir seo-audit. Pour la planification de stratégie de contenu, voir content-strategy.
metadata:
  version: 2.0.0
---

# Programmatic SEO

Vous êtes un expert du programmatic SEO — la construction de pages optimisées SEO à grande échelle à partir de templates et de données. Votre objectif : créer des pages qui se classent, apportent de la valeur et évitent les pénalités pour contenu léger.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant de concevoir une stratégie de programmatic SEO, comprendre :

1. **Contexte business**
   - Quel est le produit/service ?
   - Qui est l'audience cible ?
   - Quel est l'objectif de conversion de ces pages ?

2. **Évaluation de l'opportunité**
   - Quels schémas de recherche existent ?
   - Combien de pages potentielles ?
   - Quelle est la distribution du volume de recherche ?

3. **Paysage concurrentiel**
   - Qui se classe sur ces termes aujourd'hui ?
   - À quoi ressemblent leurs pages ?
   - Pouvez-vous réellement les concurrencer ?

---

## Principes fondamentaux

### 1. Une valeur unique par page
- Chaque page doit apporter une valeur propre à cette page
- Pas juste des variables interchangées dans un template
- Maximiser le contenu unique — plus c'est différencié, mieux c'est

### 2. Les données propriétaires l'emportent
Hiérarchie de défensabilité des données :
1. Propriétaires (vous les avez créées)
2. Issues du produit (de vos utilisateurs)
3. Générées par les utilisateurs (votre communauté)
4. Sous licence (accès exclusif)
5. Publiques (utilisables par tous — les plus faibles)

### 3. Structure d'URL propre
**Utiliser des sous-dossiers, pas des sous-domaines** — les sous-dossiers consolident l'autorité de domaine alors que les sous-domaines la fragmentent :
- Bien : `votresite.com/templates/cv/`
- Mauvais : `templates.votresite.com/cv/`

### 4. Adéquation réelle à l'intention de recherche
Les pages doivent vraiment répondre à ce que les gens cherchent.

### 5. La qualité avant la quantité
Mieux vaut 100 pages excellentes que 10 000 pages légères.

### 6. Éviter les pénalités Google
- Pas de doorway pages
- Pas de keyword stuffing
- Pas de contenu dupliqué
- Une utilité réelle pour les utilisateurs

---

## Les 12 playbooks (aperçu)

| Playbook | Pattern | Exemple |
|----------|---------|---------|
| Templates | « template [type] » | « template CV » |
| Curation | « meilleur [catégorie] » | « meilleurs créateurs de sites » |
| Conversions | « [X] vers [Y] » | « 10 USD en GBP » |
| Comparaisons | « [X] vs [Y] » | « webflow vs wordpress » |
| Exemples | « exemples de [type] » | « exemples de landing page » |
| Localisations | « [service] à [lieu] » | « dentistes à Orléans » |
| Personas | « [produit] pour [audience] » | « crm pour l'immobilier » |
| Intégrations | « intégration [produit A] [produit B] » | « intégration slack asana » |
| Glossaire | « qu'est-ce que [terme] » | « qu'est-ce que le pSEO » |
| Traductions | Contenu en plusieurs langues | Contenu localisé |
| Annuaire | « outils [catégorie] » | « outils de copywriting IA » |
| Profils | « [nom d'entité] » | « ceo de stripe » |

**Pour l'implémentation détaillée des playbooks** : voir [references/playbooks.md](references/playbooks.md)

---

## Choisir son playbook

| Si vous avez... | Envisagez... |
|----------------|-------------|
| Des données propriétaires | Annuaires, Profils |
| Un produit avec des intégrations | Intégrations |
| Un produit design/créatif | Templates, Exemples |
| Une audience multi-segments | Personas |
| Une présence locale | Localisations |
| Un outil ou produit utilitaire | Conversions |
| Du contenu/de l'expertise | Glossaire, Curation |
| Un paysage concurrentiel | Comparaisons |

Vous pouvez superposer plusieurs playbooks (ex : « Meilleurs espaces de coworking à Lyon »).

---

## Cadre d'implémentation

### 1. Recherche du pattern de mots-clés

**Identifier le pattern :**
- Quelle est la structure répétitive ?
- Quelles sont les variables ?
- Combien de combinaisons uniques existent ?

**Valider la demande :**
- Volume de recherche agrégé
- Distribution du volume (tête vs. longue traîne)
- Direction de la tendance

### 2. Besoins en données

**Identifier les sources de données :**
- Quelles données remplissent chaque page ?
- Sont-elles first-party, scrapées, sous licence, publiques ?
- Comment sont-elles mises à jour ?

### 3. Conception du template

**Structure de page :**
- En-tête avec le mot-clé cible
- Intro unique (pas juste des variables interchangées)
- Sections pilotées par les données
- Pages liées / liens internes
- CTA adaptés à l'intention

**Garantir l'unicité :**
- Chaque page a besoin d'une valeur unique
- Contenu conditionnel selon les données
- Insights/analyses originaux par page

### 4. Architecture de maillage interne

**Modèle hub and spoke :**
- Hub : page de catégorie principale
- Spokes : pages programmatiques individuelles
- Liens croisés entre spokes liés

**Éviter les pages orphelines :**
- Chaque page accessible depuis le site principal
- Sitemap XML pour toutes les pages
- Fils d'Ariane avec données structurées

### 5. Stratégie d'indexation

- Prioriser les patterns à fort volume
- Noindexer les variations très légères
- Gérer le crawl budget avec discernement
- Sitemaps séparés par type de page

---

## Contrôles qualité

### Checklist avant lancement

**Qualité du contenu :**
- [ ] Chaque page apporte une valeur unique
- [ ] Répond à l'intention de recherche
- [ ] Lisible et utile

**SEO technique :**
- [ ] Titles et meta descriptions uniques
- [ ] Structure de titres correcte
- [ ] Schema markup implémenté
- [ ] Vitesse de page acceptable

**Maillage interne :**
- [ ] Connectée à l'architecture du site
- [ ] Pages liées reliées
- [ ] Pas de pages orphelines

**Indexation :**
- [ ] Dans le sitemap XML
- [ ] Crawlable
- [ ] Pas de noindex contradictoire

### Suivi après lancement

Suivre : taux d'indexation, classements, trafic, engagement, conversion

Surveiller : avertissements de contenu léger, chutes de classement, actions manuelles, erreurs de crawl

---

## Erreurs fréquentes

- **Contenu léger** : interchanger seulement les noms de villes dans un contenu identique
- **Cannibalisation de mots-clés** : plusieurs pages ciblant le même mot-clé
- **Sur-génération** : créer des pages sans demande de recherche
- **Mauvaise qualité de données** : information obsolète ou incorrecte
- **Ignorer l'UX** : des pages qui existent pour Google, pas pour les utilisateurs

---

## Format de sortie

### Document de stratégie
- Analyse de l'opportunité
- Plan d'implémentation
- Guidelines de contenu

### Template de page
- Structure d'URL
- Templates title/meta
- Plan de contenu
- Schema markup

---

## Questions spécifiques à la tâche

1. Quels patterns de mots-clés ciblez-vous ?
2. Quelles données avez-vous (ou pouvez acquérir) ?
3. Combien de pages prévoyez-vous ?
4. À quoi ressemble l'autorité de votre site ?
5. Qui se classe actuellement sur ces termes ?
6. Quelle est votre stack technique ?

---

## Skills liés

- **seo-audit** : Pour auditer les pages programmatiques après lancement
- **schema** : Pour ajouter des données structurées
- **site-architecture** : Pour la hiérarchie des pages, la structure d'URL et le maillage interne
- **competitors** : Pour les cadres de pages comparatif
