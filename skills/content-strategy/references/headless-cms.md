# Guide Headless CMS

Référence pour choisir, modéliser et implémenter un CMS headless pour le contenu marketing.

## Quand utiliser cette référence

À utiliser pour choisir un CMS sur un nouveau projet, concevoir des modèles de contenu pour des sites marketing, mettre en place des workflows éditoriaux ou connecter le contenu d'un CMS à des pages programmatiques.

---

## Headless vs CMS traditionnel

Un CMS headless sépare la gestion de contenu de la présentation. Le contenu est stocké dans un backend structuré et délivré via API à n'importe quel frontend.

### Quand le headless a du sens

- Plusieurs frontends consomment le même contenu (web, mobile, email)
- Les développeurs veulent un contrôle total sur la stack frontend
- Le contenu doit être réutilisé à travers les canaux
- Vous construisez avec un framework moderne (Next.js, Remix, Astro)
- Le marketing a besoin de blocs de contenu structurés et réutilisables

### Quand le traditionnel marche mieux

- Petite équipe sans développeurs dédiés
- Blog simple ou site vitrine
- L'édition WYSIWYG est une exigence forte
- Le budget est serré et WordPress/Webflow fait le travail

### Checklist de décision

| Facteur | Headless | Traditionnel |
|--------|----------|-------------|
| Diffusion multi-canal | Oui | Limitée |
| Contrôle développeur | Total | Contraint |
| Édition non technique | Nécessite un setup | Intégrée |
| Délai de lancement | Plus long | Plus rapide |
| Réutilisation de contenu | Native | Manuelle |
| Flexibilité d'hébergement | N'importe quel frontend | Dépendante de la plateforme |

---

## Modélisation de contenu pour le marketing

### Principes fondamentaux

1. **Pensez en types, pas en pages.** Une « Landing Page » est un type de contenu avec des champs — pas un fichier HTML. Cela vous permet de réutiliser des composants à travers les pages.
2. **Séparez le contenu de la présentation.** Stockez le texte du titre, pas le titre stylé. La présentation appartient au frontend.
3. **Concevez pour la réutilisation.** Si les témoignages apparaissent sur 5 pages, créez un type Testimonial et référencez-le — ne dupliquez pas.
4. **Gardez les modèles plats.** Les structures profondément imbriquées sont difficiles à requêter et maintenir. Préférez les références à l'imbrication.

### Types de contenu marketing courants

| Type | Champs clés | Notes |
|------|-----------|-------|
| **Landing Page** | title, slug, hero, sections[], seo | Sections modulaires pour la flexibilité |
| **Blog Post** | title, slug, body, author, category, tags, publishedAt, seo | Corps en rich text ou Portable Text |
| **Case Study** | title, customer, challenge, solution, results, metrics[], logo | Lier aux produits/fonctionnalités liés |
| **Testimonial** | quote, author, role, company, avatar, rating | Référencé depuis les landing pages |
| **FAQ** | question, answer, category | Grouper par catégorie pour les pages programmatiques |
| **Author** | name, bio, avatar, social links | Référencé depuis les blog posts |
| **CTA Block** | heading, body, buttonText, buttonUrl, variant | Réutilisable à travers les pages |

### Checklist des champs SEO

Chaque type de contenu de niveau page a besoin de :

- `metaTitle` — 50-60 caractères
- `metaDescription` — 150-160 caractères
- `ogImage` — aperçu social 1200x630px
- `slug` — segment de chemin d'URL
- `canonicalUrl` — override optionnel
- `noIndex` — booléen pour exclure de la recherche
- `structuredData` — override JSON-LD optionnel

---

## Workflows éditoriaux

### Cycle Brouillon → Revue → Publication

1. **Brouillon** — l'auteur crée ou édite le contenu
2. **Revue** — l'éditeur relit pour l'exactitude, la voix de marque, le SEO
3. **Approbation** — la partie prenante valide
4. **Programmation** — fixer la date/heure de publication
5. **Publication** — le contenu passe en ligne via API

### API de preview

Toutes les grandes plateformes de CMS headless supportent les previews de brouillon :

- **Sanity** : preview en temps réel avec `useLiveQuery` ou l'outil Presentation
- **Contentful** : Preview API (`preview.contentful.com`) avec token d'accès distinct
- **Strapi** : système Draft & Publish avec le paramètre de requête `status=draft` (v5 ; remplace le `publicationState` de la v4)

Mettre en place une route de preview dans votre frontend (ex. `/api/preview`) qui authentifie et rend le contenu en brouillon.

### Rôles et permissions

| Rôle | Peut créer | Peut éditer | Peut publier | Peut supprimer |
|------|:----------:|:--------:|:-----------:|:----------:|
| Auteur | Oui | Les siens | Non | Ses brouillons |
| Éditeur | Oui | Tous | Oui | Brouillons |
| Admin | Oui | Tous | Oui | Tous |

Les modèles de permission exacts varient selon la plateforme. Sanity utilise un accès basé sur les rôles. Contentful a des rôles au niveau espace. Strapi a un RBAC granulaire.

---

## Comparatif de plateformes

| Fonctionnalité | Sanity | Contentful | Strapi |
|---------|--------|------------|--------|
| Hébergement | Cloud (managé) | Cloud (managé) | Auto-hébergé ou Cloud |
| Langage de requête | GROQ | REST / GraphQL | REST / GraphQL |
| Tier gratuit | Généreux | Limité | Open source (gratuit) |
| Collab temps réel | Oui (intégrée) | Limitée | Non |
| Idéal pour | Flexibilité développeur | Multi-locale entreprise | Budget / auto-hébergé |
| Modélisation de contenu | Schema-as-code | UI web | UI web ou code |
| Gestion des médias | DAM intégré | Intégrée | Basée sur des plugins |

### Sanity

**Forces** : le langage de requête GROQ est puissant et flexible. Schéma défini en code (versionné). Édition collaborative en temps réel. Portable Text pour le contenu riche. Tier gratuit généreux.

**À considérer** : courbe d'apprentissage plus raide pour les non-développeurs. La personnalisation du Studio nécessite des connaissances React. Vendor lock-in sur les requêtes GROQ.

**Fit marketing** : idéal quand développeurs et marketeurs collaborent étroitement. Fort pour les sites à fort contenu avec des modèles complexes.

### Contentful

**Forces** : plateforme entreprise mature. Excellent support multi-locale. Fort écosystème d'intégrations. Contenu composable avec Studio. API bien documentées.

**À considérer** : le pricing scale avec les types de contenu et les locales. Deux API distinctes (Delivery et Management). Les rate limits peuvent être serrés sur les plans inférieurs.

**Fit marketing** : idéal pour les entreprises avec des besoins de contenu multi-marchés. Bon quand vous avez besoin de la fiabilité d'un vendor établi.

### Strapi

**Forces** : open source, option auto-hébergée. Contrôle total sur les données. Pas de pricing par siège. Panneau d'admin personnalisable. Écosystème de plugins. REST par défaut, GraphQL via plugin.

**À considérer** : l'auto-hébergement signifie que vous gérez l'infrastructure. Écosystème plus petit que Sanity/Contentful. La migration V5 peut être conséquente depuis la V4.

**Fit marketing** : idéal pour les équipes avec une capacité DevOps qui veulent un contrôle total et pas de vendor lock-in. Bon pour les projets sensibles au budget.

### Autres à connaître

- **Hygraph** — GraphQL-natif, fort pour la fédération et le contenu multi-source
- **Keystatic** — basé sur Git, bon pour les workflows hybrides développeur-contenu
- **Payload** — TypeScript-first, auto-hébergé, configuré en code comme Sanity
- **Builder.io** — éditeur visuel avec backend headless, bon pour les marketeurs non techniques
- **Prismic** — modélisation de contenu basée sur les slices, forte intégration Next.js

---

## Intégration avec les skills marketing

### Programmatic SEO

Utiliser le CMS comme source de données pour les pages programmatiques. Stocker les données structurées (FAQ, comparatifs, pages de villes) comme types de contenu et générer les pages à partir de requêtes. Voir le skill **programmatic-seo**.

### Copywriting

Les modèles de contenu du CMS imposent une structure cohérente. Définir des champs qui correspondent à vos frameworks de copy (titre, sous-titre, preuve sociale, CTA). Voir le skill **copywriting**.

### Architecture de site

La structure d'URL, la hiérarchie de navigation et le maillage interne dépendent tous de la façon dont le contenu est organisé dans le CMS. Planifiez votre modèle de contenu et votre architecture de site ensemble. Voir le skill **site-architecture**.

### Séquences email

Tirer le contenu du CMS dans les templates email pour un messaging cohérent entre web et email. Les études de cas, témoignages et articles de blog peuvent alimenter les séquences de nurturing par email. Voir le skill **emails**.

---

## Checklist d'implémentation

- [ ] Définir les types de contenu d'après les types de pages et les blocs réutilisables
- [ ] Ajouter les champs SEO à chaque type de contenu de niveau page
- [ ] Mettre en place le mode preview/brouillon dans votre frontend
- [ ] Configurer les rôles et permissions de votre équipe
- [ ] Créer du contenu d'exemple pour chaque type avant de construire le frontend
- [ ] Mettre en place des notifications par webhook pour les changements de contenu (déclencheurs de rebuild)
- [ ] Documenter les guidelines de contenu pour les éditeurs (descriptions de champs, limites de caractères)
- [ ] Tester la performance de diffusion du contenu (CDN, caching, ISR)
- [ ] Planifier la stratégie de migration si vous quittez un CMS existant

---

## Guides d'intégration pertinents

- [Sanity](../../../tools/integrations/sanity.md) — requêtes GROQ, mutations, CLI
- [Contentful](../../../tools/integrations/contentful.md) — API Delivery/Management, publication
- [Strapi](../../../tools/integrations/strapi.md) — CRUD REST, filtres, document API
