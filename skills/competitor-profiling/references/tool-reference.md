# Référence des outils MCP pour le competitor profiling

Référence rapide des outils MCP Firecrawl et DataForSEO utilisés dans le competitor profiling.

## Sommaire
- Outils Firecrawl (scraping de site)
- Outils DataForSEO (données SEO & marché)
- Ordre d'exécution recommandé
- Gestion des erreurs

---

## Outils Firecrawl

### firecrawl_map
**Objectif** : Découvrir toutes les URL du site d'un concurrent pour identifier les pages clés.
**Quand l'utiliser** : Première étape pour chaque concurrent — avant de scraper les pages individuelles.
**Sortie clé** : Liste d'URL avec leurs types/chemins de page.
**Astuce** : Cherchez les chemins contenant `/pricing`, `/features`, `/about`, `/customers`, `/integrations`, `/blog`, `/changelog`.

### firecrawl_scrape
**Objectif** : Extraire le contenu d'une seule page sous forme de markdown propre.
**Quand l'utiliser** : Après le mapping, scraper chaque page clé individuellement.
**Sortie clé** : Contenu de la page au format markdown — accroches, corps de texte, données structurées.
**Astuce** : Scrapez la page d'accueil en premier — elle révèle positionnement, audience et preuve sociale d'un coup.

### firecrawl_search
**Objectif** : Chercher sur le web du contenu précis sur un concurrent.
**Quand l'utiliser** : Trouver des pages d'avis, de la couverture presse, ou des mentions du concurrent absentes de son propre site.
**Exemples de requêtes** :
- `"[Competitor Name]" site:g2.com`
- `"[Competitor Name]" review`
- `"[Competitor Name]" funding OR raised`

### firecrawl_crawl
**Objectif** : Crawler plusieurs pages d'un site en une seule opération.
**Quand l'utiliser** : Profils approfondis où vous voulez analyser beaucoup de pages (ex : toutes les pages fonctionnalités, tous les articles de blog). Plus coûteux — à utiliser avec parcimonie.
**Astuce** : Définissez des limites de pages pour éviter de crawler des sites entiers. Ciblez des patterns d'URL spécifiques.

### firecrawl_extract
**Objectif** : Extraire des données structurées d'une page à l'aide d'un schema.
**Quand l'utiliser** : Quand vous avez besoin de points de données précis dans un format cohérent (ex : détails des paliers de tarif, listes de fonctionnalités).
**Astuce** : Définissez un schema clair de ce que vous voulez extraire — plus fiable que de parser du markdown brut.

---

## Outils MCP DataForSEO

### Veille au niveau du domaine

#### backlinks_summary
**Objectif** : Obtenir l'autorité de domaine, le total de backlinks, les domaines référents, le score de spam.
**Entrée** : Domaine cible (ex : `competitor.com`)
**Métriques clés** : `domain_rank`, `total_backlinks`, `referring_domains`, `backlinks_spam_score`

#### backlinks_referring_domains
**Objectif** : Lister les principaux domaines référents — montre d'où vient leur link equity.
**Entrée** : Domaine cible + limite
**Métriques clés** : Par domaine : `rank`, `backlinks`, nom de `domain`

#### dataforseo_labs_google_domain_rank_overview
**Objectif** : Aperçu de la recherche organique — trafic, mots-clés, valeur du trafic.
**Entrée** : Domaine cible
**Métriques clés** : `organic_count` (mots-clés), `organic_traffic` (estimé mensuel), `organic_cost` (valeur du trafic en €)

#### dataforseo_labs_google_ranked_keywords
**Objectif** : Sur quels mots-clés un domaine se positionne, avec les positions.
**Entrée** : Domaine cible
**Métriques clés** : Par mot-clé : `keyword`, `position`, `search_volume`, `url` (page positionnée)
**Astuce** : Triez par trafic pour trouver leurs mots-clés à plus forte valeur.

#### dataforseo_labs_google_keywords_for_site
**Objectif** : Mots-clés pertinents pour un domaine — plus large que les mots-clés positionnés, inclut les opportunités.
**Entrée** : Domaine cible
**Métriques clés** : `keyword`, `search_volume`, `competition`, `cpc`

### Analyse concurrentielle

#### dataforseo_labs_google_competitors_domain
**Objectif** : Trouver les concurrents organiques les plus proches d'un domaine par recouvrement de mots-clés.
**Entrée** : Domaine cible
**Métriques clés** : `domain`, `avg_position`, `intersections` (mots-clés partagés), `full_domain_rank`
**Astuce** : Peut révéler des concurrents que l'utilisateur n'avait pas envisagés.

#### dataforseo_labs_google_domain_intersection
**Objectif** : Trouver les mots-clés sur lesquels deux domaines se positionnent tous deux — montre la concurrence directe.
**Entrée** : Deux domaines cibles
**Métriques clés** : `keyword`, position pour chaque domaine, `search_volume`
**Astuce** : Utilisez ceci pour comparer le domaine de l'utilisateur vs. chaque concurrent.

#### dataforseo_labs_google_relevant_pages
**Objectif** : Trouver les pages les plus importantes d'un domaine par trafic organique.
**Entrée** : Domaine cible
**Métriques clés** : `page`, `metrics` (trafic, mots-clés par page)
**Astuce** : Révèle leur stratégie de contenu — quelles pages génèrent le plus de valeur.

### Détection technologique

#### domain_analytics_technologies_domain_technologies
**Objectif** : Détecter la stack technologique qu'un domaine utilise.
**Entrée** : Domaine cible
**Métriques clés** : Technologies regroupées par catégorie (CMS, analytics, marketing, paiements, etc.)

### Analyse approfondie des backlinks

#### backlinks_backlinks
**Objectif** : Lister les backlinks individuels vers un domaine.
**Entrée** : Domaine cible + limite
**Métriques clés** : `url_from`, `url_to`, `anchor`, `domain_from_rank`, `is_new`

#### backlinks_bulk_ranks
**Objectif** : Comparer les domain ranks de plusieurs domaines d'un coup.
**Entrée** : Tableau de domaines cibles
**Métriques clés** : `domain_rank` par domaine
**Astuce** : Utilisez ceci pour le tableau comparatif de synthèse.

---

## Ordre d'exécution recommandé

### Scan rapide (par concurrent)

```
1. firecrawl_map → récupérer les URL du site
2. En parallèle :
   a. firecrawl_scrape → page d'accueil
   b. firecrawl_scrape → page de tarifs
   c. dataforseo_labs_google_domain_rank_overview → métriques organiques
   d. backlinks_summary → autorité de domaine
3. Synthétiser en profil abrégé
```

### Profil approfondi (par concurrent)

```
1. firecrawl_map → récupérer les URL du site
2. En parallèle (batch 1 — scraping) :
   a. firecrawl_scrape → page d'accueil
   b. firecrawl_scrape → page de tarifs
   c. firecrawl_scrape → page(s) fonctionnalités
   d. firecrawl_scrape → page à propos
   e. firecrawl_scrape → page clients/études de cas
   f. firecrawl_scrape → page intégrations
3. En parallèle (batch 2 — données SEO) :
   a. dataforseo_labs_google_domain_rank_overview
   b. dataforseo_labs_google_ranked_keywords
   c. backlinks_summary
   d. backlinks_referring_domains
   e. dataforseo_labs_google_relevant_pages
   f. dataforseo_labs_google_competitors_domain
4. En parallèle (batch 3 — extras optionnels) :
   a. domain_analytics_technologies_domain_technologies
   b. firecrawl_search → avis G2/Capterra
   c. dataforseo_labs_google_domain_intersection (vs. domaine de l'utilisateur)
5. Synthétiser en profil complet
```

### Multi-concurrents (3+ concurrents)

```
1. Cartographier tous les sites concurrents en parallèle
2. Scraper toutes les pages d'accueil en parallèle, puis les pages de tarifs en parallèle
3. Récupérer domain_rank_overview pour tous en parallèle
4. Récupérer backlinks_bulk_ranks pour tous d'un coup
5. Construire les profils en séquence (la synthèse exige de la concentration)
6. Construire la synthèse comparative en dernier
```

---

## Gestion des erreurs

| Problème | Action |
|-------|--------|
| Le scrape Firecrawl renvoie vide/bloqué | Essayer avec `firecrawl_browser_create` pour les sites lourds en JS |
| Page de tarifs introuvable dans la carte | Chercher `/pricing`, `/plans`, `/packages` — certains sites utilisent d'autres chemins |
| DataForSEO ne renvoie aucune donnée pour le domaine | Le domaine est peut-être trop récent ou trop petit — noter « données insuffisantes » dans le profil |
| Limites de débit atteintes | Espacer les requêtes ; prioriser d'abord les données à plus forte valeur |
| Scraping de la page d'avis bloqué | Utiliser `firecrawl_search` pour trouver des sources d'avis en cache ou alternatives |
```
