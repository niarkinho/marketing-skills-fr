# Sources de données prospection

Guide de sélection des outils pour la prospection, toutes branches confondues.

---

## Sélection d'outils par objectif

| Objectif | Outils principaux | Notes |
|------|--------------|-------|
| **Constituer la liste firmographique initiale (B2B / SaaS)** | Apollo, ZoomInfo, Clay | Apollo pour la couverture, ZoomInfo pour les grands comptes + l'intention, Clay pour les workflows custom |
| **Cartographie des décideurs** | LinkedIn Sales Navigator (manuel), Apollo, ZoomInfo | Sales Nav est la référence. Ne jamais le scraper en masse. |
| **Qualification de stack technique (SaaS)** | BuiltWith, Wappalyzer | BuiltWith a une couverture plus large + des offres payantes pour le bulk ; Wappalyzer est plus léger + gratuit pour un petit usage |
| **Signaux de levée de fonds (SaaS)** | Crunchbase, Pitchbook | L'offre gratuite Crunchbase suffit pour les signaux précoces ; Pitchbook pour des données investisseurs plus poussées |
| **Découverte de patterns d'email** | Hunter, Snov, Apollo | Devinette de pattern — suivie de vérification |
| **Vérification de délivrabilité email** | Truelist, Hunter, NeverBounce, ZeroBounce | Toujours vérifier avant d'ajouter aux listes d'outreach |
| **Identification de visiteurs (intention chaude)** | RB2B, Clearbit Reveal | Trafic anonyme → identification de l'entreprise |
| **Données d'intention** | ZoomInfo Intent, 6sense, Bombora | Signaux pré-chauffés ; tarifs mid-market et plus |
| **Veille des trigger events** | Google Alerts, Feedly, alertes LinkedIn Sales Nav | Les options gratuites suffisent dans la plupart des cas |
| **Découverte de commerces locaux** | Google Maps (manuel), Yelp, Pages Facebook | Assisté par navigateur, pas extrait en masse |

---

## Apollo

**À utiliser pour** : Données firmographiques + contacts B2B / SaaS généralistes. Meilleur point de départ si vous n'avez pas déjà une liste.

**Points forts** :
- Grande base de données (>200M de contacts, >60M d'entreprises)
- UI de filtrage puissante (secteur, taille, technologies, signaux)
- Recherche d'email + LinkedIn intégrée
- Offres au prepaid (pay-as-you-go) et par paliers

**Points de vigilance** :
- La fraîcheur des données varie — revérifier avant de scorer « Chaud »
- Précision des emails ~60–80 % — toujours valider
- Des limites d'export en masse s'appliquent

**Intégration** : voir [apollo.md](../../../tools/integrations/apollo.md)

---

## Clay

**À utiliser pour** : Enrichissement multi-sources, lookups en waterfall, logique de scoring custom. Quand la qualité de la liste compte plus que sa taille.

**Points forts** :
- Logique waterfall : essayer Apollo d'abord → fallback ZoomInfo → fallback Clearbit
- 100+ intégrations de fournisseurs de données
- Enrichissement piloté par IA (extraction LLM depuis des URL)
- Colonnes custom + formules de scoring
- Serveur MCP natif

**Points de vigilance** :
- La tarification au crédit peut flamber sur de grandes listes
- Surcharge de complexité — facile de sur-ingénierer les workflows

**Intégration** : voir [clay.md](../../../tools/integrations/clay.md)

---

## ZoomInfo

**À utiliser pour** : Données B2B grands comptes + intention. Profils acheteurs mid-market et plus.

**Points forts** :
- Profondeur firmographique de niveau entreprise
- Signaux d'intention (entreprises cherchant des sujets pertinents pour votre offre)
- Le meilleur de sa catégorie pour les ventes B2B à plus de 50 K€ d'ACV
- Serveur MCP natif

**Points de vigilance** :
- Cher (15 K€+/an en entrée de gamme)
- Surdimensionné pour la prospection PME
- Engagement sur des contrats pluriannuels en général

**Intégration** : voir [zoominfo.md](../../../tools/integrations/zoominfo.md)

---

## Clearbit

**À utiliser pour** : Enrichissement email → entreprise, identification de visiteurs anonymes (Clearbit Reveal).

**Points forts** :
- Fort enrichissement d'entreprise (secteur, taille, levées, stack technique)
- Recherche d'email par domaine
- Reveal : identifier les visiteurs anonymes du site au niveau de l'entreprise
- Approche API-first

**Points de vigilance** :
- Acquisition par HubSpot (2023) — désormais intégré à HubSpot Breeze Intelligence
- L'API autonome reste disponible mais le prix/l'accès dépend de l'offre

**Intégration** : voir [clearbit.md](../../../tools/integrations/clearbit.md)

---

## Hunter / Snov

**À utiliser pour** : Découverte de patterns d'email + vérification légère sur de petites listes.

**Points forts de Hunter** :
- Découverte d'email par domaine
- Vérification de délivrabilité intégrée
- Offre gratuite raisonnable pour un usage occasionnel

**Points forts de Snov** :
- Recherche d'email + drip campaigns (recoupe l'outillage d'outreach)
- Vérification en masse
- Moins cher que Hunter à l'échelle

**Points de vigilance** :
- Les deux sont des outils de devinette de pattern — la précision dépend de la capacité à inférer le pattern d'email de l'entreprise cible
- Toujours passer les résultats dans un validateur dédié (Truelist ou similaire) avant l'outreach

**Intégrations** : voir [hunter.md](../../../tools/integrations/hunter.md), [snov.md](../../../tools/integrations/snov.md)

---

## Truelist

**À utiliser pour** : Validation de délivrabilité email avant d'ajouter des contacts aux listes d'outreach. Étape de sécurité critique.

**Points forts** :
- Vérification d'un email en synchrone (`/api/v1/verify_inline`) + en masse asynchrone (`/api/v1/verify`)
- Retourne `email_state` (ok / email_invalid / risky / unknown / accept_all) + `email_sub_state` (email_ok / is_disposable / is_role / unknown_error / failed_smtp_check) + suggestions de correction de fautes (did-you-mean)
- Détecte les domaines catch-all, les comptes par fonction, les spam traps, les fournisseurs jetables
- Serveur MCP officiel pour les workflows pilotés par agent (Claude, Cursor, VS Code)
- SDK officiels en 7 langages + intégrations de frameworks (Django, Laravel, Next.js, Rails, React, Svelte, Vue, WordPress)
- Intégrations natives avec Mailchimp, Klaviyo, HubSpot, Zapier, Make, n8n, Clay, Salesforce, et plus
- Tarification à l'email

**Pourquoi c'est important** : la réputation du cold email s'effondre quand les taux de bounce dépassent 2 %. Valider avant d'envoyer n'est pas négociable. Les données Apollo/ZoomInfo/Hunter sont souvent fiables à 60–80 % — Truelist rattrape le reste.

**Intégration** : voir [truelist.md](../../../tools/integrations/truelist.md)

---

## LinkedIn Sales Navigator

**À utiliser pour** : Découverte manuelle des décideurs. La référence pour la prospection B2B / SaaS, mais uniquement utilisé comme outil de recherche.

**Points forts** :
- Les données décideurs les plus précises du marché
- Changements de poste, posts, signaux en temps réel
- Listes de leads, alertes, recherches enregistrées
- Crédits InMail (canal distinct du cold email)

**Règles strictes** :
- **Ne jamais scraper en masse.** LinkedIn bannit agressivement les scrapers. Le risque de bannissement de compte est réel et définitif.
- Utiliser Sales Nav comme interface de recherche — ouvrir des profils, lire, prendre des notes, capturer les données clés manuellement.
- Apollo et d'autres outils revendiquent des données LinkedIn via des partenariats / un miroir public — vérifier la légitimité de la source avant de présumer la conformité.

**Intégration** : pas d'accès MCP ni API au niveau grand public. Recherche manuelle uniquement.

---

## BuiltWith / Wappalyzer

**À utiliser pour** : Qualification de stack technique (branche SaaS).

**BuiltWith** :
- ~50K+ technologies suivies
- API + lookups en masse (payant)
- Données historiques (quand la stack a changé)

**Wappalyzer** :
- Extension navigateur gratuite ; API payante
- Couverture plus légère que BuiltWith
- Plus rapide pour des lookups ponctuels

Recouper les deux pour des signaux de stack technique à haute confiance.

---

## Crunchbase

**À utiliser pour** : Signaux de levée de fonds (branche SaaS).

**Points forts** :
- L'offre gratuite affiche les levées de fonds récentes
- L'offre payante (Pro / Enterprise) débloque les alertes et l'historique approfondi
- Accès API pour les utilisateurs payants

**Points de vigilance** :
- La couverture est meilleure pour les entreprises financées par du VC ; les bootstrappées + petites entreprises sont sous-représentées
- Données auto-déclarées — vérifier les montants de levée de manière indépendante

---

## GitHub (stargazers / forks / watchers)

**À utiliser pour** : Prospection sur l'intention développeur. Particulièrement puissant pour les SaaS outils dev — les stargazers de repos concurrents ou structurants pour la catégorie sont un signal in-market.

**Points forts** :
- API publique, pas de souci de scraping
- Haute qualité de signal (un repo étoilé = intérêt explicite)
- Les forks sont un signal encore plus fort (intention de modifier, pas juste de marquer)
- Le CLI fourni `github-prospects.js` gère la pagination + l'enrichissement + la sortie CSV
- Gratuit avec une limite de 5 000 req/h en authentifié

**Points de vigilance** :
- Seuls ~5–20 % des utilisateurs publient un email — coupler avec Apollo/Clay/Hunter pour l'enrichissement
- Les repos très populaires (100K+ étoiles) sont surtout du bruit ; les repos ciblés plus petits (5K–25K) offrent une meilleure densité de signal
- La plupart des prospects sont des individus, pas directement des contacts d'entreprise — il faut retrouver leur entreprise via le champ `company` ou LinkedIn

**Intégration** : voir [github.md](../../../tools/integrations/github.md)

---

## Firecrawl / Browserbase (recherche de site unique)

**À utiliser pour** : Extraire programmatiquement le contenu du **propre site web d'un prospect** que vous avez déjà trouvé par découverte sur des plateformes comme Google Maps, Yelp ou LinkedIn. Pas pour scraper ces plateformes elles-mêmes.

### Firecrawl

- **Idéal pour** : « Donne-moi juste la page en markdown » — vérifications du statut de site PME locale, extraction des pages à propos/équipe d'entreprises B2B, extraction de champs structurés
- **Points forts** : faible surcharge, retourne un markdown propre prêt pour LLM, gère la plupart des sites rendus en JS, dispose d'un serveur MCP
- **API + MCP + SDK** : Node, Python, Go, Rust

### Browserbase

- **Idéal pour** : quand il faut un vrai Chromium — pages lourdes en JS, dialogues de consentement aux cookies, soumission de formulaire pour atteindre une page contact, état de session
- **Points forts** : contrôle complet du navigateur via Playwright/Puppeteer ; Stagehand fournit une extraction en langage naturel adaptée à l'IA ; enregistrements de session pour le debug
- **API + MCP (Stagehand) + SDK** : Node, Python

### Ligne rouge de conformité

Les deux outils peuvent techniquement pointer vers n'importe quelle URL. La règle stricte :

- ✓ **OK** : extraire le contenu du propre site web d'une seule entreprise (`joescoffeeshop.com`) que vous avez trouvé par découverte manuelle
- ✗ **PAS OK** : les pointer vers `google.com/maps`, des résultats de recherche LinkedIn, des fiches Yelp, ou toute plateforme dont les ToS interdisent l'extraction en masse

La découverte se fait sur les plateformes (recherche manuelle assistée par navigateur). L'extraction se fait sur les sites publics d'entreprises individuelles.

**Intégrations** : voir [firecrawl.md](../../../tools/integrations/firecrawl.md), [browserbase.md](../../../tools/integrations/browserbase.md)

---

## RB2B / Clearbit Reveal

**À utiliser pour** : Identifier les visiteurs anonymes du site comme signaux d'intention chaude.

**Points forts** :
- Identification visiteur → entreprise basée sur un pixel
- Haute intention : ils sont venus sur votre site, ils sont déjà en mode recherche
- Alertes Slack / email sur les visites clés

**Points de vigilance** :
- Considérations vie privée/RGPD — vérifier les mentions de votre politique de confidentialité
- L'identification au niveau de la personne soulève des préoccupations plus fortes qu'au niveau de l'entreprise

**Intégration** : voir [rb2b.md](../../../tools/integrations/rb2b.md)

---

## Solutions de repli gratuites / navigateur uniquement

Quand l'utilisateur n'a aucun outil payant, s'appuyer sur :

- **Google Search** — recherches nom exact de l'entreprise + ville + fonction
- **LinkedIn** (manuel, sans scraping) — pages entreprise, recherches d'employés
- **Offre gratuite Crunchbase** — levées de fonds
- **Extension navigateur Wappalyzer** — stack technique en un coup d'œil
- **Offre gratuite Hunter.io** — 25 lookups/mois
- **Google Maps** — pour la découverte PME locale
- **Sites web d'entreprises + pages À propos** — source primaire pour toute affirmation
- **Sites d'actualité + communiqués de presse** — veille des trigger events via Google Alerts

Plus lent que les workflows outillés, mais produit de petites listes de haute qualité si l'utilisateur est prêt à faire le travail.

---

## Recommandations d'enchaînement

Un workflow de prospection full-stack typique :

1. **Définir l'ICP** depuis le contexte product marketing (aucun outil nécessaire)
2. **Liste initiale** depuis Apollo ou ZoomInfo (filtre firmographique)
3. **Enrichir** avec Clay (waterfall : stack technique, levées, trigger events)
4. **Cartographie des décideurs** dans LinkedIn Sales Nav (manuel)
5. **Découverte de patterns d'email** avec Hunter ou l'outil intégré d'Apollo
6. **Validation des emails** avec Truelist avant la liste finale
7. **Passage de relais** vers le skill cold-email pour le copy d'outreach

Adapter cet enchaînement selon les outils dont l'utilisateur dispose réellement.
