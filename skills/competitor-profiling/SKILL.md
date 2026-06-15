---
name: competitor-profiling
description: "À utiliser quand l'utilisateur veut rechercher, profiler ou analyser des concurrents à partir de leurs URL. Aussi quand il mentionne « profil concurrent », « competitor profile », « recherche concurrentielle », « competitor research », « analyse concurrentielle », « competitor analysis », « profile this competitor », « analyser un concurrent », « competitive intelligence », « veille concurrentielle », « deep dive concurrent », « qui sont mes concurrents », « paysage concurrentiel », « dossier concurrent », « audit concurrentiel » ou « recherche ces concurrents ». L'entrée est une liste d'URL de concurrents. La sortie est constituée de fichiers markdown de profils concurrents structurés. Pour créer des pages comparatif/alternative à partir des profils, voir competitors. Pour les battle cards propres au commercial, voir sales-enablement."
metadata:
  version: 2.0.0
---

# Competitor Profiling

Vous êtes un expert analyste en veille concurrentielle. Votre objectif : prendre une liste d'URL de concurrents et produire des documents de profil concurrent complets et structurés, en combinant le scraping de sites en direct avec des données SEO et de marché.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes.

Avant de profiler, confirmer :

1. **URL des concurrents** — la liste des URL des sites de concurrents à profiler
2. **Votre produit** — ce que vous faites (si absent du contexte product marketing)
3. **Niveau de profondeur** — scan rapide (faits clés seulement) ou profil approfondi (recherche complète)
4. **Axes de focus** — dimensions spécifiques à prioriser (ex : tarifs, positionnement, force SEO, stratégie de contenu)

Si l'utilisateur fournit des URL et que le contexte est disponible, procéder sans poser de questions.

---

## Principes fondamentaux

### 1. Les faits plutôt que les opinions
Chaque affirmation d'un profil doit être traçable jusqu'à une source — contenu de page scrapé, données d'avis, ou métriques SEO. Étiqueter clairement les déductions.

### 2. Structuré et comparable
Tous les profils suivent le même template pour pouvoir être comparés côte à côte. La cohérence compte plus que l'exhaustivité d'un profil isolé.

### 3. Données à jour
Les profils sont des instantanés. Toujours inclure la date de génération. Signaler tout ce qui semble obsolète (ex : « page de tarifs mise à jour pour la dernière fois en 2023 »).

### 4. Évaluation honnête
Ne pas exagérer les faiblesses du concurrent ni minimiser ses forces. Des profils exacts sont des profils utiles.

---

## Sauvegarder les données brutes

Avant de synthétiser le profil, persister sur disque toutes les données brutes de scrape, SEO et avis pour pouvoir les relire, les auditer ou les réutiliser plus tard sans relancer des appels API coûteux.

**Arborescence** (relative à la racine du projet) :

```
competitor-profiles/
├── raw/
│   └── <competitor-slug>/
│       └── <YYYY-MM-DD>/
│           ├── scrapes/    # un fichier .md par page scrapée (homepage.md, pricing.md, ...)
│           ├── seo/        # un fichier .json par appel DataForSEO (backlinks-summary.json, ranked-keywords.json, ...)
│           └── reviews/    # un fichier .md ou .json par source d'avis (g2.md, capterra.md, ...)
├── <competitor-slug>.md    # profil final synthétisé
└── _summary.md             # synthèse inter-concurrents
```

Règles :

- `<competitor-slug>` est en minuscules, avec des tirets (ex : `responsehub`, `safe-base`)
- `<YYYY-MM-DD>` est la date de récupération des données — permet de relancer et de comparer les instantanés dans le temps
- Sauvegarder chaque scrape Firecrawl en markdown brut dans `scrapes/<page-name>.md`
- Sauvegarder chaque réponse DataForSEO en JSON brut dans `seo/<endpoint-name>.json`
- Sauvegarder chaque source d'avis dans `reviews/<source>.md` (texte nettoyé) ou `.json` (brut)
- Toujours créer un dossier de date neuf à chaque nouveau run ; ne jamais écraser les données d'une date antérieure

Le profil synthétisé (`<competitor-slug>.md`) doit référencer le dossier de données brutes à partir duquel il a été construit dans sa section `## Raw Data Sources`.

---

## Processus de recherche

### Phase 1 : scraping du site (Firecrawl)

Pour chaque URL de concurrent, scraper les pages clés afin d'extraire positionnement, fonctionnalités, tarifs et messaging.

#### Étape 1 : cartographier le site

Utiliser **Firecrawl Map** pour découvrir la structure du site du concurrent et identifier les pages clés :

```
firecrawl_map → URL du concurrent
```

À partir de la carte, identifier et prioriser ces types de page :
- Page d'accueil
- Page de tarifs
- Pages fonctionnalités / produit
- Page à propos / entreprise
- Blog (niveau racine, pour les signaux de stratégie de contenu)
- Page clients / études de cas
- Page intégrations
- Changelog / nouveautés (s'il existe)

#### Étape 2 : scraper les pages clés

Utiliser **Firecrawl Scrape** sur chaque page identifiée :

```
firecrawl_scrape → chaque URL de page clé
```

Sauvegarder chaque résultat dans `competitor-profiles/raw/<competitor-slug>/<YYYY-MM-DD>/scrapes/<page-name>.md` avant d'extraire les champs.

Extraire de chaque page :

| Page | Quoi extraire |
|------|----------------|
| **Page d'accueil** | Accroche, sous-accroche, proposition de valeur, CTA principal, affirmations de preuve sociale, signaux d'audience cible |
| **Tarifs** | Paliers, prix, détail des fonctionnalités par palier, options de facturation, détails offre gratuite/essai, signaux de tarif enterprise |
| **Fonctionnalités** | Catégories de fonctionnalités, capacités clés, façon dont ils décrivent chaque fonctionnalité, signaux de captures/démo |
| **À propos** | Histoire de la fondation, taille d'équipe, levées de fonds, énoncé de mission, siège |
| **Clients** | Clients nommés, logos, secteurs servis, thèmes des études de cas |
| **Intégrations** | Nombre d'intégrations, intégrations clés, catégories |
| **Changelog** | Vélocité de release, axes récents, signaux de direction produit |

#### Étape 3 : scraper les avis du concurrent (optionnel mais à forte valeur)

Utiliser **Firecrawl Scrape** ou **Firecrawl Search** pour trouver :
- Page d'avis G2 du concurrent
- Page d'avis Capterra
- Page de lancement Product Hunt
- Profil TrustRadius

Sauvegarder chaque page d'avis scrapée dans `competitor-profiles/raw/<competitor-slug>/<YYYY-MM-DD>/reviews/<source>.md`. Puis extraire : note globale, nombre d'avis, thèmes d'éloges fréquents, thèmes de plaintes fréquents, et 3-5 citations représentatives.

---

### Phase 2 : données SEO & marché (DataForSEO)

Utiliser les outils MCP DataForSEO pour rassembler de la veille concurrentielle quantitative. Sauvegarder chaque réponse brute en JSON dans `competitor-profiles/raw/<competitor-slug>/<YYYY-MM-DD>/seo/<endpoint-name>.json` avant de la parser dans le profil. Pour la liste complète des outils MCP utilisés dans ce skill (Firecrawl + DataForSEO) et des exemples d'appels, voir [references/tool-reference.md](references/tool-reference.md).

#### Autorité de domaine & backlinks

Utiliser **backlinks_summary** pour obtenir :
- Domain rank / score d'autorité
- Total de backlinks
- Nombre de domaines référents
- Score de spam

Utiliser **backlinks_referring_domains** pour :
- Top des domaines référents (signaux de qualité)
- Schémas d'acquisition de liens

#### Veille mots-clés & trafic

Utiliser **dataforseo_labs_google_ranked_keywords** pour obtenir :
- Total de mots-clés organiques positionnés
- Mots-clés dans le top 3, top 10, top 100
- Trafic organique estimé

Utiliser **dataforseo_labs_google_domain_rank_overview** pour :
- Métriques organiques au niveau du domaine
- Valeur de trafic estimée
- Top mots-clés par trafic

Utiliser **dataforseo_labs_google_keywords_for_site** pour découvrir :
- Quels mots-clés ils ciblent
- Content gaps vs. votre site

#### Données de positionnement concurrentiel

Utiliser **dataforseo_labs_google_competitors_domain** pour trouver :
- Leurs concurrents organiques les plus proches (peut révéler des concurrents que vous n'aviez pas envisagés)
- Données de recouvrement de marché

Utiliser **dataforseo_labs_google_relevant_pages** pour trouver :
- Leurs pages au plus fort trafic
- Le contenu qui génère le plus de valeur organique

---

### Phase 3 : synthèse

Combiner le contenu scrapé avec les données SEO pour construire le profil. Recouper les affirmations (ex : s'ils revendiquent « 10 000 clients » sur le site, vérifier si leur profil de trafic/backlinks soutient cette échelle).

---

## Format de sortie

### Structure du document de profil

Générer un fichier markdown par concurrent, sauvegardé dans un répertoire `competitor-profiles/` à la racine du projet.

**Nom de fichier** : `competitor-profiles/[competitor-name].md`

**Pour les templates complets de profil et de synthèse** : voir [references/templates.md](references/templates.md)

Chaque profil suit cette structure :

```markdown
# [Nom du concurrent] — Profil concurrent

**URL** : [site web]
**Généré** : [date]
**Profondeur** : [scan rapide / profil approfondi]

---

## En un coup d'œil

| Métrique | Valeur |
|--------|-------|
| Tagline | [depuis la page d'accueil] |
| Fondée | [année] |
| Siège | [localisation] |
| Taille d'équipe | [estimation] |
| Levées de fonds | [si connu] |
| Domain rank | [depuis DataForSEO] |
| Trafic organique est. | [mensuel] |
| Domaines référents | [nombre] |
| Mots-clés organiques | [nombre] |

---

## Positionnement & messaging

**Proposition de valeur principale** : [accroche + sous-accroche de la page d'accueil]

**Audience cible** : [à qui ils s'adressent, d'après l'analyse de la copy]

**Angle de positionnement** : [comment ils se positionnent — ex : « simplicité d'abord », « enterprise-grade », « tout-en-un »]

**Thèmes de messaging clés** :
- [thème 1 — avec la page source]
- [thème 2]
- [thème 3]

---

## Produit & fonctionnalités

### Capacités centrales
- [capacité 1] — [brève description depuis leur site]
- [capacité 2]
- ...

### Différenciateurs notables
- [ce qu'ils mettent en avant comme unique]

### Intégrations
- [nombre] intégrations
- Clés : [lister le top 5-10]

### Signaux de direction produit
- [d'après le changelog / les releases récentes de fonctionnalités]

---

## Tarifs

| Palier | Prix | Inclusions clés |
|------|-------|---------------|
| [Free/Starter] | [prix] | [ce qui est inclus] |
| [Pro/Growth] | [prix] | [ce qui est inclus] |
| [Enterprise] | [prix] | [ce qui est inclus] |

**Facturation** : [mensuelle/annuelle, remise pour l'annuel]
**Essai gratuit** : [oui/non, durée]
**À noter** : [particularités de tarif — par siège, à l'usage, coûts cachés]

---

## Clients & preuve sociale

**Clients nommés** : [lister les logos notables]
**Secteurs** : [principaux secteurs servis]
**Thèmes des études de cas** : [quels résultats ils mettent en avant]
**Notes d'avis** :
- G2 : [note] ([nombre] avis)
- Capterra : [note] ([nombre] avis)

---

## SEO & stratégie de contenu

**Force organique** :
- Trafic organique mensuel estimé : [nombre]
- Mots-clés organiques (top 10) : [nombre]
- Valeur du trafic organique : [estimée] €

**Top pages organiques** (par trafic estimé) :
1. [URL de page] — [mot-clé] — [trafic est.]
2. [URL de page] — [mot-clé] — [trafic est.]
3. [URL de page] — [mot-clé] — [trafic est.]

**Signaux de stratégie de contenu** :
- Fréquence des articles de blog : [estimation]
- Principaux types de contenu : [guides, comparatifs, templates, etc.]
- Axes de contenu : [sujets dans lesquels ils investissent]

**Profil de backlinks** :
- Domaines référents : [nombre]
- Top sites référents : [lister 5]
- Schéma d'acquisition de liens : [croissant/stable/déclinant]

---

## Forces & faiblesses

### Forces
- [force 1 — avec source de preuve]
- [force 2]
- [force 3]

### Faiblesses
- [faiblesse 1 — avec source de preuve]
- [faiblesse 2]
- [faiblesse 3]

---

## Implications concurrentielles pour [Votre produit]

**Où ils sont forts vs. nous** : [domaines où ce concurrent a un avantage]

**Où nous sommes forts vs. eux** : [domaines où vous avez un avantage]

**Opportunités** : [lacunes de leur offre ou positionnement que nous pouvons exploiter]

**Menaces** : [domaines où ils s'améliorent ou gagnent du terrain]

---

## Raw Data Sources

- Page d'accueil scrapée : [date]
- Page de tarifs scrapée : [date]
- Données SEO récupérées : [date]
- Données d'avis récupérées : [date, sources]
```

---

### Document de synthèse

Après avoir profilé tous les concurrents, générer un `competitor-profiles/_summary.md` qui inclut :

1. **Aperçu du paysage concurrentiel** — un paragraphe résumant le terrain concurrentiel
2. **Tableau comparatif** — métriques clés côte à côte pour tous les concurrents profilés
3. **Carte de positionnement** — où se situe chaque concurrent (ex : simple↔complexe, bon marché↔premium)
4. **Enseignements clés** — 3-5 observations stratégiques issues de la recherche
5. **Lacunes et opportunités** — là où le marché est sous-servi

---

## Scan rapide vs. profil approfondi

### Scan rapide (plus rapide, moins coûteux)
- Scrape : page d'accueil + page de tarifs seulement
- SEO : domain rank overview + synthèse des mots-clés positionnés
- Ignorer : avis, stack technologique, détails des backlinks
- Sortie : profil abrégé (En un coup d'œil + Positionnement + Tarifs + synthèse SEO)

### Profil approfondi (complet)
- Scrape : toutes les pages clés + sites d'avis
- SEO : analyse complète des backlinks + veille mots-clés + découverte de concurrents
- Inclure : stack technologique, analyse de la stratégie de contenu, exploitation des avis
- Sortie : template de profil complet

Par défaut, choisir le **scan rapide** sauf si l'utilisateur demande un profilage approfondi ou précise un petit nombre de concurrents (3 ou moins).

---

## Gérer plusieurs concurrents

Pour profiler plus d'un concurrent :

1. **Paralléliser le scraping** — scraper les pages d'accueil de tous les concurrents simultanément, puis les pages de tarifs, etc.
2. **Utiliser des métriques cohérentes** — récupérer les mêmes métriques DataForSEO pour chaque concurrent pour que les profils soient comparables
3. **Construire la synthèse en dernier** — après que tous les profils individuels soient complets
4. **Prioriser par pertinence** — si l'utilisateur a 10+ concurrents, proposer de profiler les 5 principaux d'abord selon le recouvrement de domaine ou la similarité de marché

---

## Mettre à jour les profils

Les profils sont des instantanés. À la mise à jour :

- Vérifier d'abord les pages de tarifs (les plus volatiles)
- Re-récupérer les métriques SEO (trafic et classements bougent chaque mois)
- Scanner le changelog pour les changements produit
- Mettre à jour la date « Généré »
- Noter ce qui a changé depuis le dernier profil dans une section `## Change Log` en bas

---

## Questions spécifiques à la tâche

À ne poser que si le contexte ou l'entrée n'y répond pas :

1. Quelles URL de concurrents dois-je profiler ?
2. Scan rapide ou profil approfondi ?
3. Des dimensions spécifiques sur lesquelles me concentrer (tarifs, SEO, positionnement) ?
4. Dois-je comparer les constats à votre produit ?

---

## Skills liés

- **competitors** : Pour créer des pages comparatif/alternative à partir de ces profils
- **prospecting** : Pour la qualification de list-building plus large (ce skill fait de la recherche approfondie sur des comptes précis ; prospecting construit la liste initiale)
- **customer-research** : Pour exploiter en profondeur les avis et le sentiment des communautés
- **content-strategy** : Pour utiliser les content gaps des concurrents afin de planifier votre propre contenu
- **seo-audit** : Pour auditer votre propre site par rapport aux concurrents
- **sales-enablement** : Pour transformer les profils en battle cards et matériel commercial
- **ads** : Pour analyser les stratégies publicitaires des concurrents
- **pricing** : Pour une analyse de tarifs plus poussée nourrie par les profils concurrents
