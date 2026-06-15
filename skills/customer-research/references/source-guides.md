# Customer Research — Guides par source

Playbooks détaillés, source par source, pour collecter de l'intelligence client depuis les watering holes en ligne.

---

## Recherche sur Reddit

### Trouver les bons subreddits

Commencez par identifier où votre ICP passe du temps, pas où votre produit est discuté.

**Méthodes de découverte :**
- Chercher `site:reddit.com "[intitulé de poste] tools"` ou `site:reddit.com "[catégorie de problème] software"`
- Utiliser les [outils de recherche de subreddits](https://www.reddit.com/subreddits/search) avec des mots-clés de l'espace problème
- Regarder quels subreddits remontent dans les résultats Google quand vous cherchez les problèmes de l'ICP
- Vérifier quels subreddits les clients des concurrents mentionnent dans les avis

**Subreddits à forte valeur courants par catégorie :**
- SaaS B2B : r/sales, r/marketing, r/entrepreneur, r/startups, r/smallbusiness
- Dev tools : r/programming, r/devops, r/webdev, r/cscareerquestions
- Analytics/data : r/analytics, r/dataengineering, r/BusinessIntelligence
- Marketing : r/PPC, r/SEO, r/emailmarketing, r/content_marketing
- RH/recrutement : r/recruiting, r/humanresources, r/jobs
- Finance/ops : r/accounting, r/financialplanning, r/projectmanagement

### Opérateurs de recherche

```
site:reddit.com/r/[subreddit] "[keyword]"
site:reddit.com "[problem]" "recommend" OR "suggestion" OR "alternative"
site:reddit.com "[competitor name]" "vs" OR "alternative" OR "switched"
```

### Ce qu'il faut chercher

**Types de posts à fort signal :**
- « What tools do you use for X? » → révèle les alternatives et le vocabulaire
- « Frustrated with [concurrent], looking for alternatives » → révèle la douleur et les déclencheurs de changement
- « How do you handle X? » → révèle le workflow et les contournements
- « Is [votre catégorie] worth it? » → révèle les objections et les critères d'évaluation
- Threads de plaintes sur les concurrents → révèle les lacunes que vous pourriez combler

**Ce qu'il faut extraire :**
- Le problème exact décrit dans le post
- Les solutions les plus upvotées (que recommandent réellement les praticiens ?)
- Les plaintes sur les solutions existantes dans les commentaires
- Le langage utilisé — noter les mots et expressions précis
- Les schémas d'upvotes — consensus vs. controverse

### Outils
- La recherche native de Reddit (limitée mais rapide)
- Google : `site:reddit.com [query]` (meilleurs résultats)
- Pullpush.io — chercher dans les posts Reddit archivés (utile pour les threads anciens)

---

## Mining de G2 et des sites d'avis

### Les avis de votre propre produit

Lire dans cet ordre pour un signal maximum :

1. **Avis 3 étoiles** — ce sont les plus honnêtes. Le client a assez aimé pour rester mais a senti qu'il manquait quelque chose.
2. **Avis 1 étoile** — comprendre les modes d'échec. Séparer les problèmes produit des problèmes de support/onboarding.
3. **Avis 5 étoiles** — extraire le langage du « ce qu'ils adorent ». Ce sont vos preuves.
4. **Avis 4 étoiles** — contiennent souvent un « la seule chose que j'aurais aimé… » noyé dans les éloges.

**Ce qu'il faut extraire :**
- Ce pour quoi ils disent l'utiliser (le job to be done)
- Ce qu'ils disent de plus difficile ou frustrant
- Ce à quoi ils le comparent (« je viens de [X] », « mieux que [Y] »)
- Les signaux de secteur et de rôle dans les profils des rédacteurs

### Avis concurrents sur G2

Les avis 4 étoiles des concurrents sont de l'or — des clients qui aiment le produit mais ont quand même des plaintes.

**Structure G2 à exploiter :**
- « What do you like best? » → leurs forces (votre intel de battlecard)
- « What do you dislike? » → leurs faiblesses (vos opportunités)
- « What problems are you solving? » → le job to be done

**Capterra** a une structure similaire. **Trustpilot** penche B2C. Les avis **AppSumo** sont utiles pour le SaaS PME/prosumer.

### Template de review mining

Pour les avis 4 étoiles de chaque concurrent, extraire :

| Catégorie | Notes |
|----------|-------|
| Job to be done | Pourquoi utilisent-ils le produit ? |
| Top éloge | Qu'adorent-ils (et qui pourrait être dur à égaler pour vous) ? |
| Top plainte | Qu'est-ce qui les frustre ? |
| Contexte de changement | Ont-ils mentionné avoir migré depuis autre chose ? |
| Besoin non satisfait | « J'aurais aimé que ça puisse… » ou « Ce serait mieux si… » |

---

## Indie Hackers et Product Hunt

### Indie Hackers

Fort signal pour l'ICP fondateur/builder/PME.

**Où chercher :**
- Posts « Ask IH » : questions sur les problèmes que votre produit résout
- Posts de milestones : quand les fondateurs décrivent leur stack, ils révèlent leurs préférences d'outils et leur douleur
- Threads de commentaires sur les lancements de produits de votre catégorie

**Recherche :** `site:indiehackers.com "[problem]"` ou utiliser la recherche native d'IH.

### Product Hunt

Les **onglets Discussion** des produits concurrents sont une mine d'or de recherche :
- Questions posées = préoccupations pré-vente = objections
- Commentaires = réactions des early adopters = indicateurs avancés d'accueil
- Les collections « Alternatives to X » révèlent le paysage concurrentiel tel que les utilisateurs le voient

---

## Hacker News

Fort signal pour l'ICP technique/développeur. Penche vers les builders et les sceptiques.

**Recherches à forte valeur :**
- `site:news.ycombinator.com "[concurrent ou catégorie]"`
- Threads HN « Ask HN: best tools for X »
- Posts « Show HN » pour les concurrents — lire les commentaires sceptiques

**Ce qui est différent sur HN :**
- Les utilisateurs sont plus enclins à critiquer l'architecture sous-jacente et le business model
- Opinions tranchées sur les modèles de pricing (surtout tout ce qui est par abonnement)
- Objections de premiers principes que vous n'entendrez peut-être nulle part ailleurs

---

## Recherche sur LinkedIn

### Posts et commentaires

Chercher des posts de praticiens décrivant leurs workflows :
- « [Rôle] chez [taille d'entreprise] » + mot-clé du problème
- Histoires « Avant on faisait [ancienne méthode] mais maintenant on [nouvelle méthode] »
- Les posts demandant des recommandations d'outils reçoivent des commentaires d'acheteurs actifs

### Offres d'emploi

Une offre d'emploi est l'aveu par une entreprise d'un point de douleur.

**Ce qu'il faut chercher :**
- Quels outils sont listés en « nice to have » vs. « requis » ? (révèle la stack et les outils adjacents)
- Quelles métriques et quels résultats sont mentionnés dans la description du poste ?
- À quoi le poste passe-t-il le plus de temps ? (révèle le job to be done)

**Recherche :** `site:linkedin.com/jobs "[intitulé de rôle]" "[outil ou catégorie pertinents]"`

---

## Commentaires YouTube

### Trouver les vidéos à fort signal

- Vidéos tuto pour les problèmes que votre produit résout
- Vidéos comparatives « Best tools for X in [année] »
- Démos et walkthroughs de produits concurrents

**Ce qu'il faut chercher dans les commentaires :**
- « Does this work for [cas d'usage précis]? » → cas limites et besoins non satisfaits
- « I tried this but… » → points d'échec
- « What about [concurrent]? » → évaluation active
- Timestamps avec questions → points de confusion dans le workflow

---

## Recherche sur Twitter / X

### Opérateurs de recherche

```
"[competitor]" -filter:replies min_faves:10
"[problem keyword]" "anyone know" OR "recommend" OR "alternative"
"[category] is broken" OR "frustrated with [category]"
```

### Ce qu'il faut trouver

- Plaintes en temps réel sur les concurrents
- Praticiens discutant de leur stack
- Influenceurs/thought leaders que votre ICP suit (utile pour la distribution)

---

## Recherche sur les articles de blog et forums

### Contenu comparatif

Google : `"[concurrent 1] vs [concurrent 2]"` ou `"best [category] software [année]"`

Lisez les commentaires de ces posts — les gens qui tombent sur du contenu comparatif sont en pleine évaluation. Leurs commentaires sont des questions auxquelles votre processus de vente devrait répondre.

### Communautés de niche

- **Communautés Slack** : beaucoup de secteurs ont des groupes Slack publics ou semi-publics. Chercher « [secteur] Slack community ».
- **Serveurs Discord** : en croissance pour les communautés de développeurs et de créateurs.
- **Groupes Facebook** : toujours forts pour l'ICP PME, e-commerce, agence et coach/consultant.
- **Communautés Circle/Mighty Networks** : vérifier s'il existe des communautés payantes dans l'espace de votre ICP.

---

## Recherche B2C et apps grand public

La recherche B2C requiert des sources différentes du SaaS B2B. Les acheteurs grand public ne se rassemblent pas sur LinkedIn ou G2 — ils laissent des traces dans les app stores, sur les réseaux sociaux et dans les communautés construites autour de l'activité que sert votre produit.

### Avis sur les app stores (App Store iOS / Google Play)

L'une des sources non filtrées les plus riches pour les produits mobiles/grand public.

**Lire dans cet ordre :**
1. **Avis 1-2 étoiles** — modes d'échec, attentes non satisfaites, pics de frustration
2. **Avis 3 étoiles** — arbitrages honnêtes et retours « c'est bien mais… »
3. **Avis 5 étoiles** — ce qu'ils adorent dans leurs propres mots (preuves et positionnement)

**Ce qu'il faut extraire :**
- Le job pour lequel ils ont « embauché » l'app (« I use this to… »)
- Le moment où ça a cessé de fonctionner pour eux
- Ce à quoi ils l'ont comparée ou depuis quoi ils ont migré
- Le langage émotionnel — « I love how… », « I'm so frustrated that… »

**Astuce de recherche :** trier par « Most Recent » pour un signal frais, puis « Most Critical » pour les thèmes de douleur.

### Avis Amazon (pour produits physiques ou logiciels présents sur Amazon)

Même ordre de priorité que les app stores : avis 3 étoiles en premier.

**Équivalent G2 pour le SaaS grand public** : Trustpilot, Sitejabber et les agrégateurs d'avis spécifiques au produit.

### Communautés grand public Reddit

Le Reddit B2C est très vertical — aller dans le subreddit hobby/lifestyle, pas dans les généralistes.

**Exemples par type de produit :**
- Apps fitness : r/running, r/loseit, r/fitness, r/MyFitnessPal
- Finance personnelle : r/personalfinance, r/financialindependence, r/ynab
- Productivité/notes : r/productivity, r/Notion, r/ObsidianMD
- Voyage : r/travel, r/solotravel, r/digitalnomad
- Parentalité : r/Parenting, r/beyondthebump, r/daddit

**Schéma de recherche :** `site:reddit.com/r/[community] "[app name OR problem]"`

### Commentaires TikTok et Instagram

Fort signal pour les produits grand public à fort attrait visuel/lifestyle.

**Comment trouver le signal :**
- Chercher sur TikTok « [nom du produit] review » ou « is [produit] worth it »
- Regarder les 5-10 meilleures vidéos ; lire TOUS les commentaires — pas seulement les likes
- Sur Instagram, vérifier les posts taggés par de vrais utilisateurs (pas les posts de marque)

**Ce qu'il faut extraire :**
- Questions dans les commentaires = besoins non satisfaits ou positionnement flou
- « Does this work for…? » = jobs pour lesquels ils veulent l'embaucher
- Commentaires « I switched from X » = déclencheurs de changement
- Plaintes sur le prix, les fonctionnalités manquantes ou les promesses non tenues

### Commentaires YouTube (grand public)

Même approche qu'en B2B mais des types de vidéos différents :

- « X app honest review » ou « X app after 6 months »
- Vidéos comparatives « Best [category] apps [année] »
- Vidéos d'unboxing ou de « setup » pour les produits hardware/physiques

Les commentaires sur les vidéos d'avis sont particulièrement précieux — ce sont des gens activement en phase de considération.

### Plateformes communautaires grand public

- **Groupes Facebook** : toujours dominants pour de nombreux verticaux grand public (parentalité, fitness, services locaux, hobbies)
- **Serveurs Discord** : en croissance pour le gaming, les outils créateurs, la productivité, la crypto, les communautés lifestyle
- **Nextdoor** : utile pour les entreprises de services locaux
- **Quora** : les questions longues révèlent l'anxiété de décision et les critères d'évaluation

---

## SparkToro (intelligence d'audience)

SparkToro est un outil de recherche d'audience comportementale. Au lieu de miner des posts et commentaires individuels, il agrège les données de clickstream, de recherche et de social pour montrer ce que fait votre audience à grande échelle — ce qu'elle lit, regarde, écoute, suit et recherche.

### Quand utiliser SparkToro vs. la recherche manuelle

- **SparkToro d'abord** quand vous devez comprendre où votre ICP passe son temps, quel contenu il consomme et quels influenceurs il suit — il répond à ces questions en quelques secondes avec des données agrégées
- **Recherche manuelle d'abord** (Reddit, G2, communautés) quand vous avez besoin de langage brut, de citations exactes, de contexte émotionnel et du « pourquoi » derrière le comportement
- **Mieux ensemble** : utiliser SparkToro pour identifier quels podcasts, subreddits et sites web comptent, puis aller miner ces sources manuellement pour le langage voix-du-client

### Requêtes clés à lancer

**Par concurrent :**
- « People who follow @concurrent » — révèle les affinités d'audience partagées
- « People who visit concurrent.com » — montre ce qu'ils consomment d'autre

**Par description d'audience :**
- « People who frequently talk about [sujet] » — trouve les comportements d'audience
- « People whose bio contains [intitulé de poste] » — profile un segment basé sur un rôle

**Par votre propre audience :**
- « People who visit votredomaine.com » — comprendre votre audience réelle
- Comparer aux profils d'audience concurrents pour trouver les lacunes

### Ce qu'il faut extraire

| Type de donnée | Ce qu'elle vous dit | À utiliser pour |
|-----------|------------------|------------|
| Top sites web visités | Où votre audience lit | Partenariats de contenu, cibles de guest posting |
| Top podcasts | Ce qu'elle écoute | Guesting podcast, décisions de sponsoring |
| Top chaînes YouTube | Ce qu'elle regarde | Stratégie de contenu vidéo, placements pub |
| Top subreddits | Où elle discute | Participation communautaire, ciblage pub Reddit |
| Mots-clés de recherche | Ce qu'elle Google | Planification SEO et de sujets de contenu |
| Sujets de prompts IA | Ce qu'elle demande aux outils IA | Opportunités de contenu émergentes |
| Comptes sociaux suivis | Qui l'influence | Partenariats influenceurs, co-marketing |
| Démographie | Qui elle est | Construction de personas, ciblage pub |

### Pondération des sources

Les données SparkToro sont agrégées et anonymisées — elles montrent des schémas, pas des opinions individuelles. À traiter comme :
- **Confiance élevée** pour les données comportementales (ce qu'elle visite, suit, recherche)
- **Confiance moyenne** pour les données démographiques (auto-déclarées, possiblement incomplètes)
- **Pas un substitut** à la recherche qualitative (ne capture pas le langage, les émotions ni le « pourquoi »)

### Limites

- Tier gratuit : 5 rapports/mois, résultats superficiels (top 5–10)
- Pas d'API publique — toute la recherche se fait via l'interface web
- Penche anglophone et centré US
- Montre ce que font les audiences, pas pourquoi — à coupler avec des sources qualitatives

Voir [tools/integrations/sparktoro.md](../../../tools/integrations/sparktoro.md) pour le détail complet de l'outil et le pricing.

---

## Organiser votre recherche

Utilisez un système de tagging simple sur toutes les sources :

| Tag | Signification |
|-----|---------|
| `#pain` | Un problème ou une frustration |
| `#trigger` | Un événement qui a déclenché la recherche |
| `#outcome` | À quoi ressemble le succès |
| `#language` | Expressions exactes à réutiliser dans le copy |
| `#alternative` | Une autre solution considérée ou utilisée |
| `#objection` | Raison d'hésiter ou de ne pas acheter |
| `#competitor` | Tout ce qui concerne un produit concurrent |

Tenez un doc courant avec les colonnes : Source | Date | Citation | Tags | Notes

Après 20-30 entrées, des schémas vont émerger. Cherchez les citations qui apparaissent dans plusieurs sources non liées — ce sont vos insights à plus forte confiance.

---

## Fiabilité des sources et scoring de confiance

Toutes les sources ne pèsent pas le même poids. Utilisez ce guide pour attribuer les étiquettes de confiance.

### Pondération des sources

| Source | Force du signal | Biais à noter |
|--------|----------------|--------------|
| Entretiens clients (spontanés) | Très élevée | Petit échantillon ; biais de sélection vers les clients engagés |
| Entretiens win/loss | Élevée | Mémoire récente seulement ; rationalisation fréquente |
| Avis app store / G2 | Élevée | Penche vers les opinions tranchées (amour ou haine) |
| Posts Reddit / communautés | Moyenne-élevée | Penche technique, sceptique, minorités vocales |
| Tickets support | Moyenne | Penche vers les problèmes ; majorité silencieuse non représentée |
| Enquête (questions ouvertes) | Moyenne | Influencée par la formulation de la question |
| Enquête (choix multiples) | Faible-moyenne | Artefacts des options que vous avez fournies |
| Verbatims NPS | Moyenne | Corrèle avec le score ; sollicité par le moment de l'enquête |
| Commentaires YouTube/TikTok | Moyenne | Penche vers les spectateurs engagés ; performance sociale |
| Données d'audience SparkToro | Moyenne-élevée | Données comportementales agrégées ; fortes pour le « quoi » mais pas le « pourquoi » |
| Offres d'emploi | Faible-moyenne | Aspirationnel, pas forcément reflet de la douleur actuelle |

### Étiquettes de confiance en pratique

Quand vous présentez des insights, commencez par la confiance :

```
[CONFIANCE ÉLEVÉE] Les clients se sentent submergés par le reporting manuel — apparaît dans 12 entretiens sur 20,
4 threads Reddit, et c'est la plainte n°1 dans les avis G2 3 étoiles. Cohérent entre PME et mid-market.

[CONFIANCE MOYENNE] Les clients nous comparent aux tableurs plus qu'aux concurrents directs —
mentionné dans 6 entretiens et 3 threads Reddit, mais pas encore vu dans les données d'avis.

[CONFIANCE FAIBLE] Les acheteurs Enterprise pourraient avoir des préoccupations d'achats (procurement) — mentionné par 2 interviewés
d'entreprises de 500+. Nécessite plus de signal avant d'agir dessus.
```

### Fenêtre de récence

- **À utiliser comme source primaire** : données des 12 derniers mois
- **À utiliser avec précaution** : 12-24 mois (le produit et le marché peuvent avoir bougé)
- **À utiliser seulement comme contexte de référence** : 2+ ans

Quand un thème apparaît de façon cohérente entre données anciennes et récentes, c'est un signal durable sur lequel il vaut la peine d'agir.
