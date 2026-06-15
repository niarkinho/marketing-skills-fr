# Templates de diagrammes Mermaid

Diagrammes Mermaid prêts à copier-coller pour des sitemaps visuels. Personnalisez les libellés de nœuds et les connexions pour votre site.

---

## Hiérarchie de base

Hiérarchie de pages simple de haut en bas.

```mermaid
graph TD
    HOME["Homepage<br/>/"] --> FEAT["Features<br/>/features"]
    HOME --> PRICE["Pricing<br/>/pricing"]
    HOME --> BLOG["Blog<br/>/blog"]
    HOME --> ABOUT["About<br/>/about"]

    FEAT --> F1["Analytics<br/>/features/analytics"]
    FEAT --> F2["Automation<br/>/features/automation"]
    FEAT --> F3["Integrations<br/>/features/integrations"]

    BLOG --> B1["Post: SEO Guide<br/>/blog/seo-guide"]
    BLOG --> B2["Post: CRO Tips<br/>/blog/cro-tips"]
```

---

## Hiérarchie avec zones de navigation

Utilise des subgraphs pour montrer quelles pages apparaissent dans quelle zone de navigation.

```mermaid
graph TD
    subgraph "Header Nav"
        HOME["Homepage"]
        FEAT["Features"]
        PRICE["Pricing"]
        BLOG["Blog"]
        CTA["Get Started ★"]
    end

    subgraph "Feature Pages"
        F1["Analytics"]
        F2["Automation"]
        F3["Integrations"]
    end

    subgraph "Footer Nav"
        ABOUT["About"]
        CAREERS["Careers"]
        CONTACT["Contact"]
        PRIVACY["Privacy"]
        TERMS["Terms"]
    end

    HOME --> FEAT
    HOME --> PRICE
    HOME --> BLOG
    FEAT --> F1
    FEAT --> F2
    FEAT --> F3
    HOME --> ABOUT
    ABOUT --> CAREERS
    HOME --> CONTACT
```

---

## Hiérarchie avec libellés d'URL

Chaque nœud affiche le nom de la page et le chemin d'URL.

```mermaid
graph TD
    HOME["Homepage<br/><small>/</small>"] --> PROD["Product<br/><small>/product</small>"]
    HOME --> PRICE["Pricing<br/><small>/pricing</small>"]
    HOME --> BLOG["Blog<br/><small>/blog</small>"]
    HOME --> DOCS["Docs<br/><small>/docs</small>"]
    HOME --> ABOUT["About<br/><small>/about</small>"]

    PROD --> P1["Analytics<br/><small>/product/analytics</small>"]
    PROD --> P2["Reports<br/><small>/product/reports</small>"]

    DOCS --> D1["Getting Started<br/><small>/docs/getting-started</small>"]
    DOCS --> D2["API Reference<br/><small>/docs/api</small>"]
```

---

## Modèle de contenu hub-and-spoke

Montre une page hub connectée à des articles spokes, avec des spokes se liant entre eux.

```mermaid
graph TD
    HUB["SEO Guide<br/>(Hub Page)"]

    HUB --> S1["Keyword Research"]
    HUB --> S2["On-Page SEO"]
    HUB --> S3["Technical SEO"]
    HUB --> S4["Link Building"]

    S1 -.-> S2
    S2 -.-> S3
    S3 -.-> S4

    style HUB fill:#f9f,stroke:#333,stroke-width:2px
```

Légende :
- Lignes pleines = liens hub-spoke principaux
- Lignes pointillées = liens croisés entre spokes

---

## Flux de maillage interne

Montre comment les différentes sections du site se lient entre elles.

```mermaid
graph LR
    subgraph "Marketing"
        HOME["Homepage"]
        FEAT["Features"]
        PRICE["Pricing"]
    end

    subgraph "Content"
        BLOG["Blog"]
        GUIDE["Guides"]
        CASE["Case Studies"]
    end

    subgraph "Product"
        DOCS["Docs"]
        API["API Ref"]
        CHANGE["Changelog"]
    end

    BLOG --> FEAT
    BLOG --> CASE
    CASE --> FEAT
    CASE --> PRICE
    FEAT --> DOCS
    GUIDE --> BLOG
    GUIDE --> DOCS
    HOME --> FEAT
    HOME --> BLOG
    HOME --> CASE
```

---

## Avant/Après restructuration

Comparez côte à côte la structure actuelle et la structure proposée.

```mermaid
graph TD
    subgraph "Before"
        B_HOME["Homepage"] --> B_P1["Page 1"]
        B_HOME --> B_P2["Page 2"]
        B_HOME --> B_P3["Page 3"]
        B_HOME --> B_P4["Page 4"]
        B_HOME --> B_P5["Page 5"]
        B_HOME --> B_P6["Page 6"]
        B_HOME --> B_P7["Page 7"]
        B_HOME --> B_P8["Page 8"]
    end

    subgraph "After"
        A_HOME["Homepage"] --> A_S1["Features"]
        A_HOME --> A_S2["Resources"]
        A_HOME --> A_S3["Company"]
        A_S1 --> A_P1["Feature A"]
        A_S1 --> A_P2["Feature B"]
        A_S2 --> A_P3["Blog"]
        A_S2 --> A_P4["Guides"]
        A_S3 --> A_P5["About"]
        A_S3 --> A_P6["Contact"]
    end
```

---

## Conventions de code couleur

Utilisez les styles pour mettre en évidence le statut, la priorité ou le type de page.

```mermaid
graph TD
    HOME["Homepage"] --> FEAT["Features"]
    HOME --> PRICE["Pricing"]
    HOME --> BLOG["Blog"]
    HOME --> NEW["New Section"]
    HOME --> REMOVE["Deprecated Page"]

    FEAT --> F1["Existing Feature"]
    FEAT --> F2["New Feature"]

    style HOME fill:#4CAF50,color:#fff
    style PRICE fill:#4CAF50,color:#fff
    style FEAT fill:#4CAF50,color:#fff
    style BLOG fill:#4CAF50,color:#fff
    style F1 fill:#4CAF50,color:#fff
    style NEW fill:#2196F3,color:#fff
    style F2 fill:#2196F3,color:#fff
    style REMOVE fill:#f44336,color:#fff
```

Clé des couleurs :
- **Vert** (`#4CAF50`) : pages existantes (aucun changement)
- **Bleu** (`#2196F3`) : nouvelles pages à créer
- **Rouge** (`#f44336`) : pages à supprimer ou rediriger
- **Jaune** (`#FFC107`) : pages à restructurer ou déplacer
- **Violet** (`#9C27B0`) : pages haute priorité / CTA
