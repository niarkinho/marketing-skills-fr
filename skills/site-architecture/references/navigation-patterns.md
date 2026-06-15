# Patterns de navigation

Patterns de navigation détaillés pour différents types de sites et contextes.

---

## Navigation header

### Header simple (4-6 items)

Idéal pour : petites entreprises, SaaS simples, portfolios.

```
[Logo]   Features   Pricing   Blog   About   [CTA Button]
```

Règles :
- Le logo renvoie toujours vers la page d'accueil
- Le bouton CTA est tout à droite, visuellement distinct (bouton plein, couleur contrastée)
- Items ordonnés par priorité (les plus visités en premier)
- La page active reçoit un indicateur visuel (soulignement, gras, couleur)

### Header avec méga-menu

Idéal pour : SaaS avec beaucoup de fonctionnalités, e-commerce avec catégories, gros sites de contenu.

```
[Logo]   Product ▾   Solutions ▾   Resources ▾   Pricing   Docs   [CTA]
```

Quand « Product » est survolé/cliqué :

```
┌─────────────────────────────────────────────────┐
│  Features           Platform        Integrations │
│  ─────────          ─────────       ──────────── │
│  Analytics           Security       Slack         │
│  Automation          API            HubSpot       │
│  Reporting           Compliance     Salesforce    │
│  Dashboards                         Zapier        │
│                                                   │
│  [See all features →]                             │
└─────────────────────────────────────────────────┘
```

Règles du méga-menu :
- 2-4 colonnes max
- Grouper les items logiquement (par domaine de fonctionnalité, cas d'usage ou audience)
- Inclure un lien « See all » en bas
- Ne pas imbriquer de menus déroulants dans les méga-menus
- Afficher des descriptions pour les items quand les libellés seuls ne sont pas clairs

### Navigation scindée

Idéal pour : apps ayant à la fois une nav marketing et une nav produit.

```
[Logo]   Features   Pricing   Blog        [Login]   [Sign Up]
├── Marketing nav (left) ──────┘          └── Auth nav (right) ──┤
```

Le côté droit gère les actions d'authentification. Le côté gauche gère la navigation entre pages.

---

## Navigation footer

### Footer en colonnes (standard)

Idéal pour : la plupart des sites. Organiser les liens en 3-5 colonnes thématiques.

```
┌──────────────────────────────────────────────────────────┐
│                                                          │
│  Product          Resources        Company       Legal   │
│  ─────────        ──────────       ─────────     ─────   │
│  Features         Blog             About         Privacy │
│  Pricing          Guides           Careers       Terms   │
│  Integrations     Templates        Contact       GDPR    │
│  Changelog        Case Studies     Press                 │
│  Security         Webinars         Partners              │
│                                                          │
│  [Logo]  © 2026 Company Name                             │
│  Social: [Twitter] [LinkedIn] [GitHub]                   │
│                                                          │
└──────────────────────────────────────────────────────────┘
```

### Footer minimal

Idéal pour : sites simples, landing pages.

```
┌──────────────────────────────────────────────────────────┐
│  [Logo]                                                  │
│  © 2026 Company  ·  Privacy  ·  Terms  ·  Contact        │
└──────────────────────────────────────────────────────────┘
```

### Footer étendu

Idéal pour : sites utilisant le footer pour le SEO (pages comparatives, pages de localité, liens de ressources).

```
┌──────────────────────────────────────────────────────────┐
│  Product     Resources    Compare         Use Cases      │
│  Features    Blog         vs Competitor A  For Startups  │
│  Pricing     Guides       vs Competitor B  For Enterprise│
│  API         Templates    vs Competitor C  For Agencies  │
│                                                          │
│  Integrations             Popular Posts                  │
│  Slack       Zapier       How to Do X                    │
│  HubSpot     Salesforce   Guide to Y                     │
│                           Template: Z                    │
│                                                          │
│  [Logo]  © 2026  ·  Privacy  ·  Terms  ·  Security      │
└──────────────────────────────────────────────────────────┘
```

---

## Navigation sidebar

### Sidebar de documentation

Sidebar gauche persistante avec sections repliables.

```
Getting Started
  ├── Installation
  ├── Quick Start
  └── Configuration

Guides
  ├── Authentication
  ├── Data Models
  └── Deployment

API Reference
  ├── REST API
  │   ├── Users
  │   ├── Projects
  │   └── Webhooks
  └── GraphQL

Examples
  ├── Next.js
  ├── Rails
  └── Python

Changelog
```

Règles :
- Page courante mise en évidence
- Sections repliables (déployées par défaut pour la section active)
- Recherche en haut de la sidebar
- Navigation « Précédent / Suivant » en bas de la zone de contenu
- Collante au scroll (ne défile pas hors champ)

### Sidebar de catégories de blog

```
Categories
  ├── SEO (24)
  ├── CRO (18)
  ├── Content (15)
  ├── Paid Ads (12)
  └── Analytics (9)

Popular Posts
  ├── How to Improve SEO
  ├── Landing Page Guide
  └── Analytics Setup

Newsletter
  └── [Email signup form]
```

---

## Fils d'Ariane

### Format standard

```
Home > Features > Analytics
Home > Blog > SEO Category > How to Do Keyword Research
Home > Docs > API Reference > Authentication
```

Règles :
- Séparateur : `>` ou `/` (rester cohérent)
- Chaque segment est un lien, sauf la page courante
- La page courante est en texte simple (non liée)
- Ne pas inclure la page courante si le titre est déjà visible en H1

### Avec données structurées (schema)

```html
<nav aria-label="Breadcrumb">
  <ol itemscope itemtype="https://schema.org/BreadcrumbList">
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a itemprop="item" href="/"><span itemprop="name">Home</span></a>
      <meta itemprop="position" content="1" />
    </li>
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a itemprop="item" href="/features"><span itemprop="name">Features</span></a>
      <meta itemprop="position" content="2" />
    </li>
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <span itemprop="name">Analytics</span>
      <meta itemprop="position" content="3" />
    </li>
  </ol>
</nav>
```

Ou utiliser JSON-LD (recommandé) :

```json
{
  "@context": "https://schema.org",
  "@type": "BreadcrumbList",
  "itemListElement": [
    { "@type": "ListItem", "position": 1, "name": "Home", "item": "https://example.com/" },
    { "@type": "ListItem", "position": 2, "name": "Features", "item": "https://example.com/features" },
    { "@type": "ListItem", "position": 3, "name": "Analytics" }
  ]
}
```

---

## Navigation mobile

### Menu hamburger

Standard sur mobile. Tous les items de nav se replient dans une icône de menu.

Règles :
- Icône hamburger (trois lignes) en haut à droite ou en haut à gauche
- Panneau plein écran ou en slide-out
- Bouton CTA visible sans ouvrir le menu (header collant)
- Recherche accessible depuis le menu mobile
- Pattern accordéon pour les items imbriqués

### Barre d'onglets en bas

Idéal pour : web apps, PWA, produits mobile-first.

```
┌──────────────────────────────────────┐
│                                      │
│           [Page Content]             │
│                                      │
├──────────────────────────────────────┤
│  Home    Search    Create    Profile │
│   🏠       🔍        ➕       👤    │
└──────────────────────────────────────┘
```

Règles :
- 3-5 items max
- Icônes + libellés (pas seulement des icônes)
- État actif clairement indiqué
- Action la plus importante au centre

---

## Anti-patterns

### Choses à éviter

- **Trop d'items dans le header** (8+) : provoque la paralysie décisionnelle, la nav devient illisible sur petits écrans
- **Inception de menus déroulants** : des déroulants dans des déroulants dans des déroulants
- **Icônes mystères** : des icônes sans libellés — les utilisateurs ne savent pas ce qu'elles signifient
- **Nav principale cachée** : enterrer des pages importantes dans des menus hamburger sur desktop
- **Nav incohérente entre les pages** : la nav doit être identique sur tout le site (sauf app vs marketing)
- **Aucune considération mobile** : une nav desktop qui ne se transpose pas en mobile
- **Footer en décharge de sitemap** : 50+ liens dans le footer sans organisation
- **Fils d'Ariane qui ne correspondent pas aux URLs** : le fil d'Ariane dit « Products > Widget » mais l'URL est `/shop/widget-pro`

### Correctifs fréquents

| Problème | Correctif |
|---------|-----|
| Trop d'items de nav | Grouper en déroulants ou méga-menus |
| Les utilisateurs ne trouvent pas les pages | Ajouter une recherche, améliorer le labelling |
| Fort taux de rebond depuis la nav | Simplifier les choix, utiliser des libellés plus clairs |
| Pages SEO non liées | Ajouter au footer ou aux sections ressources |
| La nav mobile est cassée | Tester sur de vrais appareils, utiliser le pattern hamburger |

---

## Navigation pour le SEO

Les liens internes dans la navigation transmettent du PageRank. À utiliser stratégiquement :

- **Les liens de nav header sont les plus forts** — placez-y vos pages les plus importantes
- **Les liens de footer transmettent moins de valeur** mais comptent quand même — bons pour les pages comparatives, les pages de localité
- **Les liens de sidebar** aident à l'autorité au niveau section — bons pour les catégories de blog, les sections de doc
- **Les fils d'Ariane** fournissent des signaux structurels aux moteurs de recherche — à implémenter avec des données structurées (schema markup)
- **Ne pas utiliser une nav JavaScript-only** — les moteurs de recherche ont besoin de liens HTML crawlables
- **Utiliser une ancre descriptive** — « Analytics Features » et pas juste « Features »
