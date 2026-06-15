# Templates par type de site

Templates complets de hiérarchie de pages avec arbres ASCII, mappings d'URL et recommandations de navigation pour les types de sites courants.

---

## Site marketing SaaS

### Hiérarchie de pages

```
Homepage (/)
├── Features (/features)
│   ├── Feature A (/features/feature-a)
│   ├── Feature B (/features/feature-b)
│   └── Feature C (/features/feature-c)
├── Pricing (/pricing)
├── Customers (/customers)
│   ├── Case Study 1 (/customers/company-name)
│   └── Case Study 2 (/customers/company-name-2)
├── Resources (/resources)
│   ├── Blog (/blog)
│   │   └── [Posts] (/blog/post-slug)
│   ├── Templates (/resources/templates)
│   │   └── [Template] (/resources/templates/template-slug)
│   └── Guides (/resources/guides)
│       └── [Guide] (/resources/guides/guide-slug)
├── Integrations (/integrations)
│   └── [Integration] (/integrations/integration-name)
├── Docs (/docs)
│   ├── Getting Started (/docs/getting-started)
│   ├── Guides (/docs/guides)
│   └── API Reference (/docs/api)
├── About (/about)
│   ├── Careers (/about/careers)
│   └── Contact (/contact)
├── Compare (/compare)
│   └── [Competitor] (/compare/competitor-name)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapping d'URL

| Page | URL | Emplacement nav | Priorité |
|------|-----|-------------|----------|
| Page d'accueil | `/` | Header (logo) | Critique |
| Fonctionnalités | `/features` | Header | Haute |
| Pages fonctionnalité | `/features/{slug}` | Déroulant header | Moyenne |
| Tarifs | `/pricing` | Header | Critique |
| Clients | `/customers` | Header | Moyenne |
| Études de cas | `/customers/{slug}` | Déroulant Customers | Moyenne |
| Blog | `/blog` | Header (Ressources) | Haute |
| Articles de blog | `/blog/{slug}` | — | Moyenne |
| Intégrations | `/integrations` | Header | Moyenne |
| Docs | `/docs` | Header | Moyenne |
| Comparatif | `/compare/{slug}` | Footer | Haute (SEO) |
| À propos | `/about` | Footer | Basse |
| CTA Tarifs | `/pricing` | Header (bouton CTA) | Critique |

### Navigation

**Header (6 items + CTA)** : Features | Pricing | Customers | Resources | Integrations | Docs | [Get Started]

**Colonnes du footer** :
- Produit : Features, Pricing, Integrations, Changelog, Security
- Ressources : Blog, Templates, Guides, Case Studies
- Entreprise : About, Careers, Contact, Press
- Légal : Privacy, Terms, Security

---

## Site de contenu / blog

### Hiérarchie de pages

```
Homepage (/)
├── Blog (/blog)
│   ├── [Category: Topic A] (/blog/category/topic-a)
│   ├── [Category: Topic B] (/blog/category/topic-b)
│   ├── [Category: Topic C] (/blog/category/topic-c)
│   └── [Posts] (/blog/post-slug)
├── Newsletter (/newsletter)
├── Resources (/resources)
│   ├── Guides (/resources/guides)
│   │   └── [Guide] (/resources/guides/guide-slug)
│   └── Tools (/resources/tools)
│       └── [Tool] (/resources/tools/tool-slug)
├── About (/about)
├── Contact (/contact)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapping d'URL

| Page | URL | Emplacement nav | Priorité |
|------|-----|-------------|----------|
| Page d'accueil | `/` | Header (logo) | Critique |
| Index blog | `/blog` | Header | Haute |
| Catégories | `/blog/category/{slug}` | Déroulant header | Moyenne |
| Articles | `/blog/{slug}` | — | Moyenne |
| Newsletter | `/newsletter` | Header (CTA) | Haute |
| Guides | `/resources/guides` | Header | Moyenne |
| À propos | `/about` | Header | Basse |

### Navigation

**Header (4 items + CTA)** : Blog | Resources | About | Contact | [Subscribe]

**Sidebar** (sur le blog) : Catégories, Articles populaires, Inscription newsletter

---

## E-commerce

### Hiérarchie de pages

```
Homepage (/)
├── Shop (/shop)
│   ├── Category A (/shop/category-a)
│   │   ├── Subcategory (/shop/category-a/subcategory)
│   │   │   └── [Product] (/shop/category-a/subcategory/product-slug)
│   │   └── [Product] (/shop/category-a/product-slug)
│   ├── Category B (/shop/category-b)
│   │   └── [Product] (/shop/category-b/product-slug)
│   └── Category C (/shop/category-c)
│       └── [Product] (/shop/category-c/product-slug)
├── Collections (/collections)
│   └── [Collection] (/collections/collection-slug)
├── Sale (/sale)
├── Blog (/blog)
│   └── [Posts] (/blog/post-slug)
├── About (/about)
│   └── Our Story (/about/our-story)
├── Help (/help)
│   ├── FAQ (/help/faq)
│   ├── Shipping (/help/shipping)
│   ├── Returns (/help/returns)
│   └── Contact (/contact)
├── Cart (/cart)
├── Account (/account)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapping d'URL

| Page | URL | Emplacement nav | Priorité |
|------|-----|-------------|----------|
| Page d'accueil | `/` | Header (logo) | Critique |
| Boutique | `/shop` | Header | Critique |
| Catégories | `/shop/{category}` | Méga-menu header | Haute |
| Produits | `/shop/{category}/{product}` | — | Haute |
| Collections | `/collections/{slug}` | Header | Moyenne |
| Soldes | `/sale` | Header (mis en avant) | Haute |
| Panier | `/cart` | Header (icône) | Critique |
| Compte | `/account` | Header (icône) | Moyenne |

### Navigation

**Header (5 items + panier/compte)** : Shop (méga-menu) | Collections | Sale | Blog | Help | [Icône panier] [Icône compte]

**Méga-menu sous Shop** : colonnes de catégories avec produits/images mis en avant

---

## Site de documentation

### Hiérarchie de pages

```
Docs Home (/docs)
├── Getting Started (/docs/getting-started)
│   ├── Installation (/docs/getting-started/installation)
│   ├── Quick Start (/docs/getting-started/quick-start)
│   └── Configuration (/docs/getting-started/configuration)
├── Guides (/docs/guides)
│   ├── Guide A (/docs/guides/guide-a)
│   ├── Guide B (/docs/guides/guide-b)
│   └── Guide C (/docs/guides/guide-c)
├── API Reference (/docs/api)
│   ├── Authentication (/docs/api/authentication)
│   ├── Endpoints (/docs/api/endpoints)
│   └── Webhooks (/docs/api/webhooks)
├── Examples (/docs/examples)
│   └── [Example] (/docs/examples/example-slug)
├── Changelog (/docs/changelog)
└── FAQ (/docs/faq)
```

### Mapping d'URL

| Page | URL | Emplacement nav | Priorité |
|------|-----|-------------|----------|
| Accueil docs | `/docs` | Header | Haute |
| Getting Started | `/docs/getting-started` | Sidebar (haut) | Critique |
| Guides | `/docs/guides` | Sidebar | Haute |
| Référence API | `/docs/api` | Sidebar | Haute |
| Changelog | `/docs/changelog` | Sidebar (bas) | Basse |

### Navigation

**Header** : Docs | API | Blog | Community | GitHub | [Dashboard]

**Sidebar** (persistante, à gauche) : Getting Started, Guides, API Reference, Examples, Changelog — avec sous-sections déployables

**Sur la page** : navigation Précédent/Suivant en bas de chaque page de doc

---

## Hybride SaaS + contenu

### Hiérarchie de pages

```
Homepage (/)
├── Product (/product)
│   ├── Feature A (/product/feature-a)
│   ├── Feature B (/product/feature-b)
│   └── Feature C (/product/feature-c)
├── Solutions (/solutions)
│   ├── By Use Case (/solutions/use-case-slug)
│   └── By Industry (/solutions/industry-slug)
├── Pricing (/pricing)
├── Blog (/blog)
│   ├── [Category] (/blog/category/slug)
│   └── [Posts] (/blog/post-slug)
├── Resources (/resources)
│   ├── Guides (/resources/guides)
│   ├── Templates (/resources/templates)
│   ├── Webinars (/resources/webinars)
│   └── Case Studies (/resources/case-studies)
├── Docs (/docs)
│   ├── Getting Started (/docs/getting-started)
│   └── API (/docs/api)
├── Integrations (/integrations)
│   └── [Integration] (/integrations/slug)
├── Compare (/compare)
│   └── [Competitor] (/compare/competitor-slug)
├── About (/about)
│   ├── Careers (/about/careers)
│   └── Contact (/contact)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Navigation

**Header (7 items + CTA)** : Product | Solutions | Pricing | Resources | Blog | Docs | Integrations | [Start Free Trial]

Utiliser des méga-menus pour Product (liste de fonctionnalités), Solutions (cas d'usage + secteurs) et Resources (blog, guides, templates, webinaires, études de cas).

---

## Petite entreprise / local

### Hiérarchie de pages

```
Homepage (/)
├── Services (/services)
│   ├── Service A (/services/service-a)
│   ├── Service B (/services/service-b)
│   └── Service C (/services/service-c)
├── About (/about)
├── Testimonials (/testimonials)
├── Blog (/blog)
│   └── [Posts] (/blog/post-slug)
├── Contact (/contact)
├── Privacy (/privacy)
└── Terms (/terms)
```

### Mapping d'URL

| Page | URL | Emplacement nav | Priorité |
|------|-----|-------------|----------|
| Page d'accueil | `/` | Header (logo) | Critique |
| Services | `/services` | Header | Haute |
| Pages service | `/services/{slug}` | Déroulant header | Haute |
| À propos | `/about` | Header | Moyenne |
| Témoignages | `/testimonials` | Header | Moyenne |
| Blog | `/blog` | Header | Moyenne |
| Contact | `/contact` | Header (CTA) | Haute |

### Navigation

**Header (5 items + CTA)** : Services | About | Testimonials | Blog | [Contact Us]

Restez simple. Les sites de petites entreprises doivent être plats (1-2 niveaux max). Chaque page doit être accessible depuis le header.
