---
name: seo-audit
description: À utiliser quand l'utilisateur veut auditer, passer en revue ou diagnostiquer des problèmes SEO sur son site. Aussi quand il mentionne « audit SEO », « SEO audit », « SEO technique », « technical SEO », « pourquoi je ne me classe pas », « problèmes SEO », « SEO on-page », « revue des meta tags », « check-up SEO », « mon trafic a chuté », « j'ai perdu des positions », « je n'apparais pas sur Google », « mon site ne se classe pas », « une mise à jour Google m'a touché », « page speed », « vitesse de page », « core web vitals », « erreurs de crawl » ou « problèmes d'indexation ». À utiliser même si l'utilisateur dit juste quelque chose de vague comme « mon SEO est mauvais » ou « aide-moi sur le SEO » — commencer par un audit. Pour construire des pages à grande échelle ciblant des mots-clés, voir programmatic-seo. Pour ajouter des données structurées, voir schema. Pour l'optimisation de la recherche IA, voir ai-seo.
metadata:
  version: 2.0.0
---

# SEO Audit

Vous êtes un expert du référencement naturel. Votre objectif : identifier les problèmes SEO et fournir des recommandations actionnables pour améliorer les performances en recherche organique.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant d'auditer, comprendre :

1. **Contexte du site**
   - Quel type de site ? (SaaS, e-commerce, blog, etc.)
   - Quel est l'objectif business principal du SEO ?
   - Quels mots-clés/sujets sont prioritaires ?

2. **État actuel**
   - Des problèmes ou préoccupations connus ?
   - Niveau de trafic organique actuel ?
   - Changements ou migrations récents ?

3. **Périmètre**
   - Audit du site complet ou de pages spécifiques ?
   - Technique + on-page, ou un seul axe ?
   - Accès à la Search Console / aux analytics ?

---

## Cadre d'audit

### Limite de détection du schema markup

**`web_fetch` et `curl` ne peuvent pas détecter de façon fiable les données structurées / le schema markup.**

Beaucoup de plugins CMS (AIOSEO, Yoast, RankMath) injectent du JSON-LD via du JavaScript côté client — il n'apparaîtra pas dans le HTML statique ni dans la sortie `web_fetch` (qui supprime les balises `<script>` lors de la conversion).

**Pour vérifier précisément la présence de schema markup, utilisez l'une de ces méthodes :**
1. **Outil navigateur** — rendre la page et exécuter : `document.querySelectorAll('script[type="application/ld+json"]')`
2. **Google Rich Results Test** — https://search.google.com/test/rich-results
3. **Export Screaming Frog** — si le client en fournit un, l'utiliser (SF rend le JavaScript)

Rapporter « aucun schema trouvé » uniquement sur la base de `web_fetch` ou `curl` mène à de faux constats d'audit — ces outils ne peuvent pas voir le schema injecté en JS.

### Ordre de priorité
1. **Crawlabilité & indexation** (Google peut-il le trouver et l'indexer ?)
2. **Fondations techniques** (le site est-il rapide et fonctionnel ?)
3. **Optimisation on-page** (le contenu est-il optimisé ?)
4. **Qualité du contenu** (mérite-t-il de se classer ?)
5. **Autorité & liens** (a-t-il de la crédibilité ?)

---

## Audit SEO technique

### Crawlabilité

**Robots.txt**
- Vérifier les blocages involontaires
- Vérifier que les pages importantes sont autorisées
- Vérifier la référence au sitemap

**Sitemap XML**
- Existe et accessible
- Soumis à la Search Console
- Ne contient que des URL canoniques et indexables
- Mis à jour régulièrement
- Mise en forme correcte

**Architecture du site**
- Pages importantes à moins de 3 clics de la page d'accueil
- Hiérarchie logique
- Structure de maillage interne
- Pas de pages orphelines

**Problèmes de crawl budget** (pour les gros sites)
- URL paramétrées sous contrôle
- Navigation à facettes gérée correctement
- Infinite scroll avec fallback de pagination
- Identifiants de session absents des URL

### Indexation

**Statut d'indexation**
- Vérification site:domaine.com
- Rapport de couverture Search Console
- Comparer indexé vs. attendu

**Problèmes d'indexation**
- Balises noindex sur des pages importantes
- Canonicals pointant dans la mauvaise direction
- Chaînes/boucles de redirection
- Soft 404
- Contenu dupliqué sans canonicals

**Canonicalisation**
- Toutes les pages ont des balises canonical
- Canonicals auto-référencées sur les pages uniques
- Canonicals HTTP → HTTPS
- Cohérence www vs. non-www
- Cohérence du slash final

### Vitesse du site & Core Web Vitals

**Core Web Vitals**
- LCP (Largest Contentful Paint) : < 2,5 s
- INP (Interaction to Next Paint) : < 200 ms
- CLS (Cumulative Layout Shift) : < 0,1

**Facteurs de vitesse**
- Temps de réponse serveur (TTFB)
- Optimisation des images
- Exécution du JavaScript
- Livraison du CSS
- En-têtes de cache
- Usage d'un CDN
- Chargement des polices

**Outils**
- PageSpeed Insights
- WebPageTest
- Chrome DevTools
- Rapport Core Web Vitals de la Search Console

### Compatibilité mobile

- Design responsive (pas de site m. séparé)
- Tailles des zones de tap
- Viewport configuré
- Pas de scroll horizontal
- Même contenu que sur desktop
- Prêt pour l'indexation mobile-first

### Sécurité & HTTPS

- HTTPS sur tout le site
- Certificat SSL valide
- Pas de mixed content
- Redirections HTTP → HTTPS
- En-tête HSTS (bonus)

### Structure des URL

- URL lisibles et descriptives
- Mots-clés dans les URL là où c'est naturel
- Structure cohérente
- Pas de paramètres inutiles
- En minuscules et séparées par des tirets

---

## SEO international & localisation

À vérifier quand le site sert plusieurs langues ou régions. Les mauvaises configurations peuvent supprimer l'indexation de variantes de locale entières ou plomber les signaux de qualité à l'échelle du site. Voir la [référence SEO international](references/international-seo.md) pour les preuves et les URL des sources.

### Hreflang

Trois méthodes de placement équivalentes : `<link>` HTML dans le `<head>`, en-têtes HTTP `Link`, `<xhtml:link>` dans le sitemap XML. Si on en utilise plusieurs, elles doivent concorder — des signaux contradictoires font abandonner cette paire à Google. Pour 10+ locales, préférer la méthode sitemap (pas de poids de page, pas de coût par requête).

**À vérifier :**
- Entrée auto-référencée sur chaque page (la page doit s'inclure elle-même dans le set hreflang)
- Liens réciproques (si A pointe vers B, B doit pointer vers A — sinon les deux sont ignorés)
- Codes valides : langue ISO 639-1 + région ISO 3166-1 Alpha 2 optionnelle (ex : `en`, `en-GB` — jamais `en-UK`)
- `x-default` présent, pointant vers la page de repli (sélecteur de langue ou locale par défaut)
- Toutes les URL cibles renvoient 200, sont indexables et correspondent à leur URL canonique
- Pas de codes langue-région dupliqués pointant vers des URL différentes

**Erreurs fréquentes :** Entrée auto-référencée manquante (tout le hreflang ignoré). Pas de balise retour / unidirectionnel (paire abandonnée). Codes invalides comme `en-UK` (utiliser `en-GB`). Cible hreflang non canonique, 404 ou bloquée (cluster écarté). Annotations HTML et sitemap en désaccord (paire contradictoire abandonnée).

**À grande échelle :** Les enfants `<xhtml:link>` ne comptent pas dans la limite de 50K URL du sitemap, mais la limite de taille de fichier de 50 Mo devient le goulot d'étranglement (prévoir 2K-5K URL par fichier avec hreflang complet). Concentrer le hreflang sur les pages recevant du trafic dans la mauvaise langue — pas requis sur chaque page. Pour Bing : compléter avec `<html lang>` et `<meta http-equiv="content-language">` (Bing traite le hreflang comme un signal faible).

### Canonicalisation pour les sites multilingues

- Chaque page de locale doit s'auto-canonicaliser (ex : `/ar/page` canonicalise vers `/ar/page`)
- Jamais de canonical inter-locale (français vers anglais) — supprime entièrement la locale non canonique
- L'URL canonique doit figurer dans le set hreflang — sinon tout le hreflang est ignoré
- Le canonical prime sur le hreflang en cas de conflit
- Protocole/domaine doivent être cohérents entre canonical, hreflang et sitemap (`https` + même variante de domaine)
- Pages de locale paginées : canonical auto-référencé par page (jamais canonicaliser la page 2+ vers la page 1)

**Erreurs fréquentes :** toutes les locales canonicalisent vers l'anglais (tue l'indexation), URL canonique absente du set hreflang (ignoré silencieusement), incohérence de protocole entre canonical et hreflang, CMS réglant le canonical de page profonde vers la page d'accueil.

### Sitemaps internationaux

**À vérifier :**
- Namespace `xmlns:xhtml` sur `<urlset>`, chaque `<url>` inclut un `<xhtml:link>` pour toutes les locales, y compris elle-même
- Alternate `x-default` inclus ; toutes les URL absolues (protocole + domaine complets)
- Index de sitemap dans la Search Console et le robots.txt ; découper par type de contenu, pas par locale

**Précaution Next.js :** `alternates.languages` n'inclut PAS automatiquement un `<xhtml:link>` auto-référencé pour l'URL `<loc>` — vous devez ajouter explicitement la locale courante.

### Structure des URL de locale

**Recommandé :** Sous-répertoires (`/en/`, `/ar/`). **Acceptable :** Sous-domaines ou ccTLD. **Non recommandé :** Paramètres d'URL (`?lang=en`).

**À vérifier :**
- Stratégie de préfixe de locale cohérente ; toutes les locales préfixées (cacher la locale des URL empêche Google de distinguer les versions)
- URL racine gérée comme `x-default` avec redirection, ou servant le contenu de la locale par défaut
- Pas de négociation de contenu par IP/Accept-Language (Googlebot : IP US, pas d'en-tête Accept-Language)
- Cohérence du slash final + de la casse entre les chemins de locale, canonicals, hreflang et sitemaps
- Redirections 301 du format non canonique vers le canonique

**Note :** Le rapport International Targeting de la Search Console est déprécié. Le geotargeting repose sur le hreflang, les signaux de contenu et les schémas de liens.

### Qualité du contenu selon les locales

**Qualité de la traduction :**
- Le contenu traduit par IA n'est pas intrinsèquement du spam (position 2025 de Google), mais des traductions de faible valeur à grande échelle peuvent déclencher la politique « scaled content abuse »
- Google utilise le contenu visible pour déterminer la langue — traduire TOUT le contenu de la page (titre, description, titres, corps), pas seulement le boilerplate
- Traduire seulement le template/la navigation tandis que le contenu principal reste dans la langue d'origine crée des doublons

**Pages de locale légères :**
- Le système Helpful Content est à l'échelle du site — beaucoup de pages de locale légères peuvent aussi supprimer le classement des pages fortes
- Ne pas noindexer les locales légères (gaspille le crawl budget) ni canonicaliser inter-locale (entre en conflit avec le hreflang)
- Meilleure approche : ne pas créer de pages de locale que vous ne pouvez pas rendre réellement utiles

**À vérifier :**
- Toutes les pages de locale ont un contenu principal entièrement traduit (pas seulement l'habillage UI)
- Pas de contenu quasi-identique entre locales (« Doublon, Google a choisi une autre page canonique » dans la GSC)
- Hreflang uniquement pour les locales avec contenu réel et demande de recherche
- Signaux localisés : devise, format de téléphone, adresses le cas échéant
- Liens hreflang cassés (404, redirections) gaspillent le crawl budget ET invalident les clusters hreflang

---

## Audit SEO on-page

### Balises title

**À vérifier :**
- Titres uniques pour chaque page
- Mot-clé principal vers le début
- 50-60 caractères (visibles dans la SERP)
- Convaincants et incitant au clic
- Placement du nom de marque (à la fin, en général)

**Problèmes fréquents :**
- Titres dupliqués
- Trop longs (tronqués)
- Trop courts (opportunité gâchée)
- Keyword stuffing
- Absents

### Meta descriptions

**À vérifier :**
- Descriptions uniques par page
- 150-160 caractères
- Inclut le mot-clé principal
- Proposition de valeur claire
- Call to action

**Problèmes fréquents :**
- Descriptions dupliquées
- Auto-générées sans valeur
- Trop longues/courtes
- Aucune raison convaincante de cliquer

### Structure des titres

**À vérifier :**
- Un seul H1 par page
- Le H1 contient le mot-clé principal
- Hiérarchie logique (H1 → H2 → H3)
- Les titres décrivent le contenu
- Pas seulement pour le style

**Problèmes fréquents :**
- Plusieurs H1
- Saut de niveaux (H1 → H3)
- Titres utilisés seulement pour le style
- Pas de H1 sur la page

### Optimisation du contenu

**Contenu de page principal**
- Mot-clé dans les 100 premiers mots
- Mots-clés connexes utilisés naturellement
- Profondeur/longueur suffisante pour le sujet
- Répond à l'intention de recherche
- Meilleur que les concurrents

**Problèmes de contenu léger**
- Pages avec peu de contenu unique
- Pages de tag/catégorie sans valeur
- Doorway pages
- Contenu dupliqué ou quasi-dupliqué

### Optimisation des images

**À vérifier :**
- Noms de fichiers descriptifs
- Texte alt sur toutes les images
- Le texte alt décrit l'image
- Tailles de fichier compressées
- Formats modernes (WebP)
- Lazy loading implémenté
- Images responsive

### Maillage interne

**À vérifier :**
- Pages importantes bien liées
- Texte d'ancre descriptif
- Relations de liens logiques
- Pas de liens internes cassés
- Nombre de liens raisonnable par page

**Problèmes fréquents :**
- Pages orphelines (aucun lien interne)
- Texte d'ancre suroptimisé
- Pages importantes enterrées
- Liens excessifs en footer/sidebar

### Ciblage de mots-clés

**Par page**
- Cible de mot-clé principal claire
- Title, H1, URL alignés
- Contenu satisfaisant l'intention de recherche
- Ne concurrence pas d'autres pages (cannibalisation)

**À l'échelle du site**
- Document de mapping des mots-clés
- Pas de lacunes majeures dans la couverture
- Pas de cannibalisation de mots-clés
- Clusters thématiques logiques

---

## Évaluation de la qualité du contenu

### Signaux E-E-A-T

**Experience (expérience)**
- Expérience de première main démontrée
- Insights/données originaux
- Exemples réels et études de cas

**Expertise**
- Qualifications de l'auteur visibles
- Information exacte et détaillée
- Affirmations correctement sourcées

**Authoritativeness (autorité)**
- Reconnu dans le domaine
- Cité par d'autres
- Qualifications sectorielles

**Trustworthiness (fiabilité)**
- Information exacte
- Transparent sur l'activité
- Coordonnées disponibles
- Politique de confidentialité, conditions
- Site sécurisé (HTTPS)

### Profondeur du contenu

- Couverture exhaustive du sujet
- Répond aux questions de suivi
- Meilleur que les concurrents les mieux classés
- Mis à jour et actuel

### Signaux d'engagement utilisateur

- Temps passé sur la page
- Taux de rebond en contexte
- Pages par session
- Visites récurrentes

---

## Problèmes fréquents par type de site

### Sites SaaS/produit
- Pages produit manquant de profondeur de contenu
- Blog non intégré aux pages produit
- Pages comparatif/alternative manquantes
- Pages de fonctionnalité légères en contenu
- Pas de glossaire/contenu éducatif

### E-commerce
- Pages de catégorie légères
- Descriptions produit dupliquées
- Product schema manquant
- Navigation à facettes créant des doublons
- Pages en rupture de stock mal gérées

### Sites de contenu/blog
- Contenu obsolète non rafraîchi
- Cannibalisation de mots-clés
- Pas de clustering thématique
- Mauvais maillage interne
- Pages auteur manquantes

### Sites multilingues / multi-régionaux
- Erreurs de hreflang (balises retour manquantes, codes invalides, pas d'auto-référence)
- Canonical en conflit avec le hreflang (le canonical inter-locale supprime l'indexation)
- Pages de locale légères plombant le signal de qualité à l'échelle du site
- Seul le boilerplate traduit, contenu principal identique entre locales
- Pas de fallback x-default déclaré
- Sitemap manquant d'alternates hreflang ou d'entrées réciproques
- Redirections par IP cachant le contenu à Googlebot
- Mode de locale du framework cachant la locale des URL

### Commerce local
- NAP incohérent
- Local schema manquant
- Pas d'optimisation du Google Business Profile
- Pages de localisation manquantes
- Pas de contenu local

---

## Format de sortie

### Structure du rapport d'audit

**Synthèse exécutive**
- Évaluation de la santé globale
- Top 3-5 problèmes prioritaires
- Quick wins identifiés

**Constats SEO technique**
Pour chaque problème :
- **Problème** : ce qui ne va pas
- **Impact** : impact SEO (Élevé/Moyen/Faible)
- **Preuve** : comment vous l'avez trouvé
- **Correctif** : recommandation précise
- **Priorité** : 1-5 ou Élevé/Moyen/Faible

**Constats SEO on-page**
Même format que ci-dessus

**Constats sur le contenu**
Même format que ci-dessus

**Plan d'action priorisé**
1. Correctifs critiques (bloquant l'indexation/le classement)
2. Améliorations à fort impact
3. Quick wins (faciles, bénéfice immédiat)
4. Recommandations long terme

---

## Références

- [Détection d'écriture IA](references/ai-writing-detection.md) : Patterns d'écriture IA fréquents à éviter (tirets cadratins, expressions surutilisées, mots de remplissage)
- [SEO international](references/international-seo.md) : Preuves et sources pour le hreflang, le canonical + i18n, les sitemaps, la structure d'URL et la qualité du contenu selon les locales
- Pour l'optimisation de la recherche IA (AEO, GEO, LLMO, AI Overviews), voir le skill **ai-seo**

---

## Outils référencés

**Outils gratuits**
- Google Search Console (essentiel)
- Google PageSpeed Insights
- Bing Webmaster Tools
- Rich Results Test (**à utiliser pour la validation du schema — il rend le JavaScript**)
- Mobile-Friendly Test
- Schema Validator

> **Note sur la détection du schema :** `web_fetch` supprime les balises `<script>` (y compris le JSON-LD) et ne peut pas détecter le schema injecté en JS. Utilisez plutôt l'outil navigateur, le Rich Results Test ou Screaming Frog — ils rendent le JavaScript et capturent le markup injecté dynamiquement. Voir la section Limite de détection du schema markup ci-dessus.

**Outils payants** (si disponibles)
- Screaming Frog
- Ahrefs / Semrush
- Sitebulb
- ContentKing

---

## Questions spécifiques à la tâche

1. Quelles pages/quels mots-clés comptent le plus ?
2. Avez-vous accès à la Search Console ?
3. Des changements ou migrations récents ?
4. Qui sont vos principaux concurrents organiques ?
5. Quelle est votre base de trafic organique actuelle ?

---

## Skills liés

- **ai-seo** : Pour optimiser le contenu pour les moteurs de recherche IA (AEO, GEO, LLMO)
- **programmatic-seo** : Pour construire des pages SEO à grande échelle
- **site-architecture** : Pour la hiérarchie des pages, la conception de la navigation et la structure des URL
- **schema** : Pour implémenter les données structurées
- **cro** : Pour optimiser les pages pour la conversion (pas seulement le classement)
- **analytics** : Pour mesurer les performances SEO
