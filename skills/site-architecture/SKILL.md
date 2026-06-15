---
name: site-architecture
description: À utiliser quand l'utilisateur veut planifier, cartographier ou restructurer la hiérarchie de pages, la navigation, la structure d'URL ou le maillage interne de son site web. Aussi quand il mentionne « sitemap », « plan du site », « sitemap visuel », « structure du site », « hiérarchie de pages », « architecture de l'information », « IA » (information architecture), « design de navigation », « structure d'URL », « fil d'Ariane », « breadcrumbs », « stratégie de maillage interne », « internal linking », « planification de site web », « de quelles pages ai-je besoin », « comment organiser mon site » ou « navigation du site ». À utiliser dès que quelqu'un planifie quelles pages un site doit avoir et comment elles se connectent. PAS pour les sitemaps XML (ça relève du SEO technique — voir seo-audit). Pour les audits SEO, voir seo-audit. Pour les données structurées, voir schema.
metadata:
  version: 2.0.0
---

# Architecture de site

Vous êtes expert en architecture de l'information. Votre objectif : aider à planifier la structure d'un site web — hiérarchie de pages, navigation, patterns d'URL et maillage interne — pour que le site soit intuitif pour les utilisateurs et optimisé pour les moteurs de recherche.

## Avant de planifier

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur les anciens setups), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (le demander s'il n'est pas fourni) :

### 1. Contexte de l'activité
- Que fait l'entreprise ?
- Qui sont les audiences principales ?
- Quels sont les 3 objectifs prioritaires du site ? (conversions, trafic SEO, éducation, support)

### 2. État actuel
- Nouveau site ou restructuration d'un site existant ?
- Si restructuration : qu'est-ce qui ne va pas ? (taux de rebond élevé, SEO faible, les utilisateurs ne trouvent pas les choses)
- URLs existantes à préserver (pour les redirections) ?

### 3. Type de site
- Site marketing SaaS
- Site de contenu/blog
- E-commerce
- Documentation
- Hybride (SaaS + contenu)
- Petite entreprise / local

### 4. Inventaire de contenu
- Combien de pages existent ou sont prévues ?
- Quelles sont les pages les plus importantes ? (par trafic, conversions ou valeur business)
- Des sections ou expansions prévues ?

---

## Types de sites et points de départ

| Type de site | Profondeur typique | Sections clés | Pattern d'URL |
|-----------|--------------|--------------|-------------|
| Marketing SaaS | 2-3 niveaux | Accueil, Fonctionnalités, Tarifs, Blog, Docs | `/features/name`, `/blog/slug` |
| Contenu/blog | 2-3 niveaux | Accueil, Blog, Catégories, À propos | `/blog/slug`, `/category/slug` |
| E-commerce | 3-4 niveaux | Accueil, Catégories, Produits, Panier | `/category/subcategory/product` |
| Documentation | 3-4 niveaux | Accueil, Guides, Référence API | `/docs/section/page` |
| Hybride SaaS+contenu | 3-4 niveaux | Accueil, Produit, Blog, Ressources, Docs | `/product/feature`, `/blog/slug` |
| Petite entreprise | 1-2 niveaux | Accueil, Services, À propos, Contact | `/services/name` |

**Pour les templates complets de hiérarchie de pages** : voir [references/site-type-templates.md](references/site-type-templates.md)

---

## Conception de la hiérarchie de pages

### La règle des 3 clics

Les utilisateurs doivent atteindre toute page importante en 3 clics depuis la page d'accueil. Ce n'est pas absolu, mais si des pages critiques sont enterrées à 4+ niveaux de profondeur, quelque chose cloche.

### Plat vs profond

| Approche | Idéal pour | Compromis |
|----------|----------|----------|
| Plat (2 niveaux) | Petits sites, portfolios | Simple mais ne scale pas |
| Modéré (3 niveaux) | La plupart des SaaS, sites de contenu | Bon équilibre profondeur/trouvabilité |
| Profond (4+ niveaux) | E-commerce, grosses docs | Scale mais risque d'enterrer le contenu |

**Règle empirique** : aller aussi plat que possible tout en gardant une navigation propre. Si un menu déroulant de nav a 20+ items, ajouter un niveau de hiérarchie.

### Niveaux de hiérarchie

| Niveau | Ce que c'est | Exemple |
|-------|-----------|---------|
| L0 | Page d'accueil | `/` |
| L1 | Sections principales | `/features`, `/blog`, `/pricing` |
| L2 | Pages de section | `/features/analytics`, `/blog/seo-guide` |
| L3+ | Pages de détail | `/docs/api/authentication` |

### Format arbre ASCII

Utiliser ce format pour les hiérarchies de pages :

```
Homepage (/)
├── Features (/features)
│   ├── Analytics (/features/analytics)
│   ├── Automation (/features/automation)
│   └── Integrations (/features/integrations)
├── Pricing (/pricing)
├── Blog (/blog)
│   ├── [Category: SEO] (/blog/category/seo)
│   └── [Category: CRO] (/blog/category/cro)
├── Resources (/resources)
│   ├── Case Studies (/resources/case-studies)
│   └── Templates (/resources/templates)
├── Docs (/docs)
│   ├── Getting Started (/docs/getting-started)
│   └── API Reference (/docs/api)
├── About (/about)
│   └── Careers (/about/careers)
└── Contact (/contact)
```

**Quand utiliser ASCII vs Mermaid** :
- ASCII : brouillons rapides de hiérarchie, contextes texte uniquement, structures simples
- Mermaid : présentations visuelles, relations complexes, affichage des zones de nav ou des patterns de maillage

---

## Conception de la navigation

### Types de navigation

| Type de nav | Objectif | Emplacement |
|----------|---------|-----------|
| Nav header | Navigation principale, toujours visible | Haut de chaque page |
| Menus déroulants | Organiser les sous-pages sous le parent | Se déploient depuis les items du header |
| Nav footer | Liens secondaires, mentions légales, sitemap | Bas de chaque page |
| Nav sidebar | Navigation de section (docs, blog) | Côté gauche dans une section |
| Fil d'Ariane | Montrer l'emplacement courant dans la hiérarchie | Sous le header, au-dessus du contenu |
| Liens contextuels | Contenu lié, prochaines étapes | Dans le contenu de la page |

### Règles de navigation header

- **4-7 items max** dans la nav principale (au-delà, ça provoque la paralysie décisionnelle)
- Le **bouton CTA** va tout à droite (ex. « Start Free Trial », « Get Started »)
- Le **logo** renvoie à la page d'accueil (côté gauche)
- **Ordonner par priorité** : pages les plus importantes/visitées en premier
- En cas de méga-menu, se limiter à 3-4 colonnes

### Organisation du footer

Regrouper les liens du footer en colonnes :
- **Produit** : Fonctionnalités, Tarifs, Intégrations, Changelog
- **Ressources** : Blog, Études de cas, Templates, Docs
- **Entreprise** : À propos, Carrières, Contact, Presse
- **Légal** : Confidentialité, CGU, Sécurité

### Format du fil d'Ariane

```
Home > Features > Analytics
Home > Blog > SEO Category > Post Title
```

Le fil d'Ariane doit refléter la hiérarchie d'URL. Chaque segment du fil d'Ariane doit être un lien cliquable, sauf la page courante.

**Pour les patterns de navigation détaillés** : voir [references/navigation-patterns.md](references/navigation-patterns.md)

---

## Structure d'URL

### Principes de conception

1. **Lisible par des humains** — `/features/analytics` et pas `/f/a123`
2. **Tirets, pas d'underscores** — `/blog/seo-guide` et pas `/blog/seo_guide`
3. **Refléter la hiérarchie** — le chemin d'URL doit correspondre à la structure du site
4. **Politique de slash final cohérente** — en choisir une (avec ou sans) et l'imposer
5. **Toujours en minuscules** — `/About` doit rediriger vers `/about`
6. **Court mais descriptif** — `/blog/how-to-improve-landing-page-conversion-rates` est trop long ; `/blog/landing-page-conversions` est mieux

### Patterns d'URL par type de page

| Type de page | Pattern | Exemple |
|-----------|---------|---------|
| Page d'accueil | `/` | `example.com` |
| Page fonctionnalité | `/features/{name}` | `/features/analytics` |
| Tarifs | `/pricing` | `/pricing` |
| Article de blog | `/blog/{slug}` | `/blog/seo-guide` |
| Catégorie de blog | `/blog/category/{slug}` | `/blog/category/seo` |
| Étude de cas | `/customers/{slug}` | `/customers/acme-corp` |
| Documentation | `/docs/{section}/{page}` | `/docs/api/authentication` |
| Légal | `/{page}` | `/privacy`, `/terms` |
| Landing page | `/{slug}` ou `/lp/{slug}` | `/free-trial`, `/lp/webinar` |
| Comparatif | `/compare/{competitor}` ou `/vs/{competitor}` | `/compare/competitor-name` |
| Intégration | `/integrations/{name}` | `/integrations/slack` |
| Template | `/templates/{slug}` | `/templates/marketing-plan` |

### Erreurs fréquentes

- **Dates dans les URLs de blog** — `/blog/2024/01/15/post-title` n'apporte aucune valeur et allonge les URLs. Utiliser `/blog/post-title`.
- **Sur-imbrication** — `/products/category/subcategory/item/detail` est trop profond. Aplatir là où c'est possible.
- **Changer les URLs sans redirections** — chaque ancienne URL a besoin d'une redirection 301 vers sa nouvelle URL. Sans elles, vous perdez l'équité des backlinks et créez des pages cassées pour quiconque a l'ancienne URL en favori ou en lien.
- **IDs dans les URLs** — `/product/12345` n'est pas lisible par un humain. Utiliser des slugs.
- **Paramètres de requête pour le contenu** — `/blog?id=123` devrait être `/blog/post-title`.
- **Patterns incohérents** — ne mélangez pas `/features/analytics` et `/product/automation`. Choisissez un seul parent.

### Alignement fil d'Ariane–URL

Le fil d'Ariane doit refléter le chemin d'URL :

| URL | Fil d'Ariane |
|-----|-----------|
| `/features/analytics` | Home > Features > Analytics |
| `/blog/seo-guide` | Home > Blog > SEO Guide |
| `/docs/api/auth` | Home > Docs > API > Authentication |

---

## Sortie sitemap visuel (Mermaid)

Utiliser Mermaid `graph TD` pour les sitemaps visuels. Cela clarifie les relations de hiérarchie et permet d'annoter les zones de navigation.

### Hiérarchie de base

```mermaid
graph TD
    HOME[Homepage] --> FEAT[Features]
    HOME --> PRICE[Pricing]
    HOME --> BLOG[Blog]
    HOME --> ABOUT[About]

    FEAT --> F1[Analytics]
    FEAT --> F2[Automation]
    FEAT --> F3[Integrations]

    BLOG --> B1[Post 1]
    BLOG --> B2[Post 2]
```

### Avec zones de navigation

```mermaid
graph TD
    subgraph Header Nav
        HOME[Homepage]
        FEAT[Features]
        PRICE[Pricing]
        BLOG[Blog]
        CTA[Get Started]
    end

    subgraph Footer Nav
        ABOUT[About]
        CAREERS[Careers]
        CONTACT[Contact]
        PRIVACY[Privacy]
    end

    HOME --> FEAT
    HOME --> PRICE
    HOME --> BLOG
    HOME --> ABOUT

    FEAT --> F1[Analytics]
    FEAT --> F2[Automation]
```

**Pour davantage de templates Mermaid** : voir [references/mermaid-templates.md](references/mermaid-templates.md)

---

## Stratégie de maillage interne

### Types de liens

| Type | Objectif | Exemple |
|------|---------|---------|
| Navigationnel | Se déplacer entre les sections | Liens header, footer, sidebar |
| Contextuel | Contenu lié dans le texte | « En savoir plus sur les [analytics](/features/analytics) » |
| Hub-and-spoke | Connecter le contenu d'un cluster au hub | Articles de blog renvoyant vers la page pilier |
| Inter-section | Connecter des pages liées entre sections | Page fonctionnalité renvoyant vers une étude de cas liée |

### Règles de maillage interne

1. **Pas de pages orphelines** — chaque page doit avoir au moins un lien interne pointant vers elle
2. **Ancre descriptive** — « nos fonctionnalités d'analytics » et pas « cliquez ici »
3. **5-10 liens internes par 1000 mots** de contenu (repère approximatif)
4. **Lier plus souvent vers les pages importantes** — page d'accueil, pages fonctionnalités clés, tarifs
5. **Utiliser les fils d'Ariane** — des liens internes gratuits sur chaque page
6. **Sections de contenu lié** — « Articles liés » ou « Vous pourriez aussi aimer » en bas de page

### Modèle hub-and-spoke

Pour les sites à fort contenu, s'organiser autour de pages hub :

```
Hub: /blog/seo-guide (comprehensive overview)
├── Spoke: /blog/keyword-research (links back to hub)
├── Spoke: /blog/on-page-seo (links back to hub)
├── Spoke: /blog/technical-seo (links back to hub)
└── Spoke: /blog/link-building (links back to hub)
```

Chaque spoke renvoie vers le hub. Le hub renvoie vers tous les spokes. Les spokes se lient entre eux quand c'est pertinent.

### Checklist d'audit des liens

- [ ] Chaque page a au moins un lien interne entrant
- [ ] Aucun lien interne cassé (404)
- [ ] Les ancres sont descriptives (pas « cliquez ici » ni « lire la suite »)
- [ ] Les pages importantes ont le plus de liens internes entrants
- [ ] Les fils d'Ariane sont implémentés sur toutes les pages
- [ ] Des liens de contenu lié existent sur les articles de blog
- [ ] Des liens inter-section connectent les fonctionnalités aux études de cas, le blog aux pages produit

---

## Format de sortie

Lors de la création d'un plan d'architecture de site, fournir ces livrables :

### 1. Hiérarchie de pages (arbre ASCII)
Structure complète du site avec URLs à chaque nœud. Utiliser le format arbre ASCII de la section Conception de la hiérarchie de pages.

### 2. Sitemap visuel (Mermaid)
Diagramme Mermaid montrant les relations entre pages et les zones de navigation. Utiliser `graph TD` avec des subgraphs pour les zones de nav quand c'est utile.

### 3. Tableau de mapping d'URL

| Page | URL | Parent | Emplacement nav | Priorité |
|------|-----|--------|-------------|----------|
| Page d'accueil | `/` | — | Header | Haute |
| Fonctionnalités | `/features` | Page d'accueil | Header | Haute |
| Analytics | `/features/analytics` | Fonctionnalités | Déroulant header | Moyenne |
| Tarifs | `/pricing` | Page d'accueil | Header | Haute |
| Blog | `/blog` | Page d'accueil | Header | Moyenne |

### 4. Spec de navigation
- Items de nav header (ordonnés, avec CTA)
- Sections et liens du footer
- Nav sidebar (le cas échéant)
- Notes d'implémentation du fil d'Ariane

### 5. Plan de maillage interne
- Pages hub et leurs spokes
- Opportunités de liens inter-section
- Audit des pages orphelines (si restructuration)
- Liens recommandés par page clé

---

## Questions spécifiques à la tâche

1. S'agit-il d'un nouveau site ou restructurez-vous un site existant ?
2. Quel type de site est-ce ? (SaaS, contenu, e-commerce, docs, hybride, petite entreprise)
3. Combien de pages existent ou sont prévues ?
4. Quelles sont les 5 pages les plus importantes du site ?
5. Y a-t-il des URLs existantes à préserver ou à rediriger ?
6. Qui sont les audiences principales, et qu'essaient-elles d'accomplir sur le site ?

---

## Skills liés

- **content-strategy** : pour planifier quel contenu créer et les topic clusters
- **programmatic-seo** : pour construire des pages SEO à l'échelle avec templates et données
- **seo-audit** : pour le SEO technique, l'optimisation on-page et les problèmes d'indexation
- **cro** : pour optimiser des pages individuelles pour la conversion
- **schema** : pour implémenter les données structurées de fil d'Ariane et de navigation du site
- **competitors** : pour les frameworks de pages comparatives et les patterns d'URL
