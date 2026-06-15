# Architecture de contenu pour pages concurrents

Comment structurer et maintenir les données concurrents pour des pages de comparaison scalables.

## Sommaire
- Données concurrents centralisées
- Template de données concurrent
- Données de votre produit
- Génération des pages
- Structure des pages d'index (index des alternatives, index des comparaisons vs, bonnes pratiques des pages d'index)
- Navigation en footer

## Données concurrents centralisées

Créez une source unique de vérité pour chaque concurrent :

```
competitor_data/
├── notion.md
├── airtable.md
├── monday.md
└── ...
```

---

## Template de données concurrent

Par concurrent, documenter :

```yaml
name: Notion
website: notion.so
tagline: "The all-in-one workspace"
founded: 2016
headquarters: San Francisco

# Positionnement
primary_use_case: "docs + bases de données légères"
target_audience: "équipes voulant un workspace flexible"
market_position: "premium, riche en fonctionnalités"

# Tarifs
pricing_model: par-siège
free_tier: true
free_tier_limits: "blocs limités, 1 utilisateur"
starter_price: 8 €/utilisateur/mois
business_price: 15 €/utilisateur/mois
enterprise: sur devis

# Fonctionnalités (noter 1-5 ou décrire)
features:
  documents: 5
  databases: 4
  project_management: 3
  collaboration: 4
  integrations: 3
  mobile_app: 3
  offline_mode: 2
  api: 4

# Forces (soyez honnête)
strengths:
  - Extrêmement flexible et personnalisable
  - Interface belle et moderne
  - Écosystème de templates solide
  - Communauté active

# Faiblesses (soyez juste)
weaknesses:
  - Peut être lent avec de grandes bases de données
  - Courbe d'apprentissage pour les fonctionnalités avancées
  - Automatisations limitées vs. les outils dédiés
  - Mode hors-ligne limité

# Idéal pour
best_for:
  - Équipes voulant un workspace tout-en-un
  - Workflows à fort volume de contenu
  - Équipes documentation-first
  - Startups et petites équipes

# Pas idéal pour
not_ideal_for:
  - Besoins complexes de gestion de projet
  - Grandes bases de données (milliers de lignes)
  - Équipes ayant besoin d'un hors-ligne robuste
  - Grands comptes à conformité stricte

# Plaintes fréquentes (issues des avis)
common_complaints:
  - "Devient lent avec beaucoup de contenu"
  - "Difficile de retrouver les choses quand le workspace grandit"
  - "L'app mobile est peu pratique"

# Notes de migration
migration_from:
  difficulty: moyenne
  data_export: "Markdown, CSV, HTML"
  what_transfers: "Pages, bases de données"
  what_doesnt: "Automatisations, configuration des intégrations"
  time_estimate: "1-3 jours pour une petite équipe"
```

---

## Données de votre produit

Même structure pour vous-même — soyez honnête :

```yaml
name: [Votre produit]
# ... mêmes champs

strengths:
  - [Vos vraies forces]

weaknesses:
  - [Vos faiblesses honnêtes]

best_for:
  - [Vos clients idéaux]

not_ideal_for:
  - [Ceux qui devraient utiliser autre chose]
```

---

## Génération des pages

Chaque page tire des données centralisées :

- **Page alternative à [Concurrent]** : tire les données du concurrent + vos données
- **Page alternatives à [Concurrent]** : tire les données du concurrent + vos données + les autres alternatives
- **Page vous vs [Concurrent]** : tire vos données + les données du concurrent
- **Page [A] vs [B]** : tire les données des deux concurrents + vos données

**Bénéfices** :
- Mettre à jour le tarif d'un concurrent une fois, mis à jour partout
- Ajouter une comparaison de fonctionnalité une fois, apparaît sur toutes les pages
- Exactitude cohérente entre les pages
- Plus facile à maintenir à grande échelle

---

## Structure des pages d'index

### Index des alternatives

**URL** : `/alternatives` ou `/alternatives/index`

**Objectif** : liste toutes les pages « alternative à [Concurrent] »

**Structure de page** :
1. Titre : « [Votre produit] comme alternative »
2. Brève intro sur les raisons pour lesquelles les gens passent à vous
3. Liste de toutes les pages alternative avec :
   - Nom/logo du concurrent
   - Résumé en une ligne du différenciateur clé vs. ce concurrent
   - Lien vers la comparaison complète
4. Raisons fréquentes de changement (agrégées)
5. CTA

**Exemple** :
```markdown
## Découvrez [Votre produit] comme alternative

Vous cherchez à changer ? Voyez comment [Votre produit] se compare aux outils que vous évaluez :

- **[Alternative à Notion](/alternatives/notion)** — Mieux pour les équipes qui ont besoin de [X]
- **[Alternative à Airtable](/alternatives/airtable)** — Mieux pour les équipes qui ont besoin de [Y]
- **[Alternative à Monday](/alternatives/monday)** — Mieux pour les équipes qui ont besoin de [Z]
```

---

### Index des comparaisons vs

**URL** : `/vs` ou `/compare`

**Objectif** : liste toutes les pages « vous vs [Concurrent] » et « [A] vs [B] »

**Structure de page** :
1. Titre : « Comparez [Votre produit] »
2. Section : « [Votre produit] vs concurrents » — liste des comparaisons directes
3. Section : « Comparaisons en face-à-face » — liste des pages [A] vs [B]
4. Brève note de méthodologie
5. CTA

---

### Bonnes pratiques des pages d'index

**Tenez-les à jour** : quand vous ajoutez une nouvelle page de comparaison, ajoutez-la à l'index concerné.

**Maillage interne** :
- Lier de l'index → pages individuelles
- Lier des pages individuelles → retour à l'index
- Lier entre comparaisons liées

**Valeur SEO** :
- Les pages d'index peuvent se classer sur des termes larges comme « comparaisons d'outils de gestion de projet »
- Transmettent le link equity aux pages de comparaison individuelles
- Aident les moteurs de recherche à découvrir tout le contenu de comparaison

**Options de tri** :
- Par popularité (volume de recherche)
- Par ordre alphabétique
- Par catégorie/cas d'usage
- Par date d'ajout (montre la fraîcheur)

**À inclure sur les pages d'index** :
- Date de dernière mise à jour pour la crédibilité
- Nombre de pages/comparaisons disponibles
- Filtres rapides si vous avez beaucoup de comparaisons

---

## Navigation en footer

Le footer du site apparaît sur toutes les pages marketing, ce qui en fait une puissante opportunité de maillage interne pour les pages concurrents.

### Option 1 : lier vers les pages d'index (minimum)

Au minimum, ajoutez des liens vers vos pages d'index de comparaison dans le footer :

```
Footer
├── Comparer
│   ├── Alternatives →  /alternatives
│   └── Comparaisons →  /vs
```

Cela garantit que chaque page marketing transmet du link equity à votre hub de contenu de comparaison.

### Option 2 : colonnes de footer par format (recommandé pour le SEO)

Pour un maillage interne plus fort, créez des colonnes de footer dédiées à chaque format que vous avez construit, liant directement vers vos principaux concurrents :

```
Footer
├── [Produit] vs              ├── Alternatives à             ├── Comparer
│   ├── vs Notion             │   ├── Alternative à Notion   │   ├── Notion vs Airtable
│   ├── vs Airtable           │   ├── Alternative à Airtable │   ├── Monday vs Asana
│   ├── vs Monday             │   ├── Alternative à Monday   │   ├── Notion vs Monday
│   ├── vs Asana              │   ├── Alternative à Asana    │   ├── ...
│   ├── vs Clickup            │   ├── Alternative à Clickup  │   └── Voir tout →
│   ├── ...                   │   ├── ...                    │
│   └── Voir tout →           │   └── Voir tout →            │
```

**Guidelines** :
- Inclure jusqu'à 8 liens par colonne (principaux concurrents par volume de recherche)
- Ajouter un lien « Voir tout » vers la page d'index complète
- Ne créer des colonnes que pour les formats pour lesquels vous avez réellement construit des pages
- Prioriser les concurrents au plus fort volume de recherche

### Pourquoi les liens en footer comptent

1. **Distribution sitewide** : les liens en footer apparaissent sur chaque page marketing, transmettant du link equity de tout votre site vers le contenu de comparaison
2. **Efficacité de crawl** : les moteurs de recherche découvrent vite toutes les pages de comparaison
3. **Découverte utilisateur** : les visiteurs qui évaluent votre produit trouvent facilement les comparaisons
4. **Positionnement concurrentiel** : signale aux moteurs de recherche que vous êtes un acteur clé du domaine

### Notes d'implémentation

- Mettre à jour le footer en ajoutant de nouvelles pages de comparaison prioritaires
- Garder le footer propre — ne pas lister toutes les comparaisons, juste les principales
- Faire correspondre les en-têtes de colonnes à votre structure d'URL (ex : colonne « vs » → URL `/vs/`)
- Penser au mobile : les colonnes peuvent s'empiler, donc ordonner par priorité
