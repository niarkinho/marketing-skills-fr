# Stack des opérations marketing — Skills + MCP par étape AARRR

Ce document mappe chaque skill marketing et chaque intégration MCP/API pertinente à l'étape (ou aux étapes) AARRR qu'elle sert principalement. C'est la source de la Section 11 de chaque plan.

> **Note sur le périmètre.** Les skills ci-dessous vivent dans ce repo `marketingskills`. Quelques références pointent vers des outils optionnels de marketplaces Claude Code voisines (ex : `vercel:agent-browser`, `compound-engineering:diagram-maker`) — substituer des équivalents s'ils ne sont pas installés. Quand un plan référence un skill ou un outil indisponible, se rabattre sur la tactique sous-jacente et le signaler dans les décisions ouvertes de la Section 13.

## La thèse

Petite équipe + fCMO + outillage agentique = la production d'une org marketing traditionnelle de 15–20 personnes. Les skills + MCP encodent des workflows qui nécessitaient auparavant un effectif dédié par canal.

La Section 11 du plan rend cette thèse explicite en :
1. Mappant les skills aux étapes pour que le fondateur voie quels skills exécutent quel travail
2. Mappant les MCP/API aux étapes pour que le fondateur voie la couche d'outillage
3. Nommant un exemple opérationnel concret qui prouve que le stack fonctionne
4. Montrant les déblocages de capacités par stade de financement (pre-seed → seed → Série A)

## Skills marketing mappés à AARRR

### Skills d'acquisition

| Skill | Ce qu'il fait | Usage principal en Acquisition |
|---|---|---|
| `seo-audit` | Audite le site pour le SEO technique et on-page | Bilans de santé trimestriels du site |
| `ai-seo` | Optimise le contenu pour les moteurs de recherche IA / la citation par LLM | Stratégie de contenu pérenne |
| `programmatic-seo` | Construit des pages SEO pilotées par template à grande échelle | Systèmes de pages localisation, comparaison, intégration |
| `schema` | Ajoute du balisage de données structurées (schema markup) | Rich snippets, éligibilité à la citation IA |
| `content-strategy` | Planifie les sujets de contenu, piliers, cadence | Mise en place du calendrier éditorial |
| `competitors` | Construit des vs-pages et des pages alternative-to | Capter des SERP à forte intention contre les concurrents |
| `ads` | Planifie et structure les campagnes payantes | Apple Search Ads, Meta, Google, LinkedIn |
| `ad-creative` | Génère des variations d'annonces et de la créa | Itérer la créa pub sur les plateformes |
| `social` | Planifie et rédige le contenu réseaux sociaux | LinkedIn, Twitter/X, Instagram, TikTok |
| `typefully` | Programme/publie tweets, threads, contenu LinkedIn | Opérations de cadence pour les canaux pilotés par le fondateur |
| `cold-email` | Rédige du cold outreach B2B + séquences | Outbound pour SaaS B2B / activités hybrides |
| `analytics` | Met en place le tracking, GA4, événements de conversion | Instrumentation du funnel |
| `free-tools` | Planifie des outils gratuits d'engineering-as-marketing | Construire des outils qui génèrent des liens + leads |
| `marketing-website-design` | Conçoit des sites marketing avec intention | Design de pages pilier / landing |
| `launch` | Planifie et exécute des lancements (Product Hunt, GA, lancements de features) | Moments GTM — stratégie + exécution tactique |

### Skills d'activation

| Skill | Ce qu'il fait | Usage principal en Activation |
|---|---|---|
| `onboarding` | Optimise les flows d'onboarding utilisateur | Refonte d'onboarding, tests de taux d'activation |
| `signup` | Optimise l'inscription/enregistrement | Réduire la friction en haut de l'activation |
| `cro` | Optimise n'importe quelle page ou formulaire marketing | Tests de conversion sur pages, formulaires, landing pages |
| `paywalls` | Optimise les paywalls et écrans d'upgrade | Conversion trial → payant (aussi Revenu) |
| `popups` | Optimise les popups, modales, slide-ins | Capture de leads + prompts d'activation |
| `copywriting` | Rédige le copy marketing | Écrans d'onboarding, copy de paywall, CTA |
| `copy-editing` | Édite et améliore un copy existant | Passe voix / clarté avant expédition |
| `copycraft` | Overlay de variation de copy en temps réel | Itération de copy en direct pendant les revues |
| `website-copy` | Rédige tout le copy d'un site (étape 8 du process CF) | Production complète de copy de site |
| `ab-testing` | Planifie les A/B tests | Structure pour les tests de variantes d'onboarding |
| `marketing-psychology` | Applique les sciences comportementales au copy et au CRO | Principes de persuasion dans les moments d'activation |

### Skills de rétention

| Skill | Ce qu'il fait | Usage principal en Rétention |
|---|---|---|
| `emails` | Conçoit des séquences email | Construction de flows Customer.io / Mailchimp / Resend |
| `churn-prevention` | Construit des flows d'annulation, offres de rétention, win-back | Réduire le churn, récupérer les paiements échoués |
| `copywriting` / `copy-editing` | Production de copy email | Contenu des emails de cycle de vie |
| `paywalls` | (transversal) — prompts d'upgrade dans les emails de rétention | Upsell dans le cycle de vie |
| `ab-testing` | Teste les variantes d'email | Tests d'objet, de CTA, de timing |

### Skills de recommandation (referral)

| Skill | Ce qu'il fait | Usage principal en Referral |
|---|---|---|
| `referrals` | Planifie et lance des programmes de referral / affiliation / ambassadeurs | Skill central pour la Section 7 |
| `social` | Crée du contenu partageable par les ambassadeurs | Éléments de langage, templates de posts |
| `copywriting` | Copy email ambassadeur / affilié | Recrutement, onboarding, communication |
| `marketing-website-design` | Landing pages par ambassadeur | Surface d'attribution |
| `emails` | Emails de cycle de vie ambassadeur | Onboarding, digest mensuel, notifications de paiement |

### Skills de revenu

| Skill | Ce qu'il fait | Usage principal en Revenu |
|---|---|---|
| `pricing` | Audite et optimise le pricing | Structure des paliers de plan, défauts annuels, métriques de valeur |
| `paywalls` | Optimisation des paywalls | Conversion trial → payant, free → payant |
| `sales-enablement` | Construit des decks de vente, one-pagers, démos | Matériel de support des ventes B2B |
| `revops` | Revenue operations, cycle de vie des leads | Passation marketing → ventes |
| `ab-testing` | Expériences de pricing | Tester le défaut annuel, le prix d'intro, la consolidation de paliers |

### Skills transversaux / fondation de marque

| Skill | Ce qu'il fait | Usage principal |
|---|---|---|
| `product-marketing` | Met en place le fichier de contexte `.agents/product-marketing.md` (positionnement, ICP, voix) | Fondamental — à lancer en premier ; chaque section du plan le référence |
| `customer-research` | Mène des entretiens clients + sondages | Section 2 + Section 3 (État des lieux) |
| `marketing-psychology` | Applique les sciences comportementales | Transversal au copy, au CRO, aux paywalls |
| `marketing-ideas` | La bibliothèque de 139 idées | Section 12 du plan (banque d'idées) |

## MCP et API mappés à AARRR

### Outillage d'acquisition

| Outil | Ce qu'il fournit | Vérification de branchement chez le client |
|---|---|---|
| **Ahrefs API** | Données SEO : recherche de mots-clés, backlinks, analyse concurrentielle | `AHREFS_API_KEY` requise dans `.env` |
| **DataForSEO API** | Données SERP, volume de mots-clés, analyse de SERP concurrentielle | Clé API requise |
| **GA4 MCP** | Trafic par canal, événements de conversion, courbes de rétention | Branché via projet gcp + service account |
| **GitHub MCP** | Travail sur repo : site marketing (patterns `site-name-promo`), rédaction de contenu | Auth CLI `gh` standard + serveur MCP |
| **Typefully MCP** | Publication sociale (LinkedIn, X, Threads, Bluesky) | Compte Typefully + clé API |
| **Google Ads MCP** | Gestion de compte pub, création de campagnes, remontées de performance | Branché après déblocage du budget |
| **agent-browser** | Automatisation de navigateur (remplissage de formulaires, captures, scraping) | Install CLI : `npm install -g agent-browser` |
| **dev-browser** | Automatisation de navigateur générique | Install de serveur MCP |
| **defuddle** | Extraction propre en markdown depuis des pages web | Install CLI |
| **Notion** | Accès à l'annuaire de connaissances internes | Clé API Notion |
| **Stripe MCP** | Calculs de LTV, réconciliation du CAC payant (transversal au Revenu) | Compte Stripe + clé restreinte |

### Outillage d'activation

| Outil | Ce qu'il fournit |
|---|---|
| **App Store Connect** | Taux de conversion par variante de fiche, funnel d'install | Généralement manuel + `dev-browser` pour les captures |
| **GitHub MCP** | Repo de l'app mobile pour les éditions de code d'onboarding |
| **Figma / Pencil MCP** | Design + itération des écrans d'onboarding |
| **Customer.io MCP** | Messagerie in-app + coordination des emails de cycle de vie |
| **Stripe MCP** | État d'abonnement pour la logique de paywall |
| **GA4 MCP** | Instrumentation des événements d'activation |

### Outillage de rétention

| Outil | Ce qu'il fournit |
|---|---|
| **Customer.io MCP** | L'infrastructure de rétention — construction de flows, segmentation, envoi |
| **Shopify** | Événements d'achat hardware comme déclencheurs de cycle de vie |
| **Stripe MCP** | État d'abonnement, cohortes de churn, changements de plan |
| **GA4 MCP** | Événements de session, courbes de rétention |
| **Resend / Mailchimp / SendGrid** | Alternatives à Customer.io pour différents stacks |

### Outillage de recommandation (referral)

| Outil | Ce qu'il fournit |
|---|---|
| **Dub.co** | Attribution ambassadeur, liens courts, tracking par ambassadeur |
| **Stripe MCP** | Comptabilité des commissions + paiements via Connect |
| **GitHub MCP** | Landing pages par ambassadeur |
| **Customer.io MCP** | Cycle de vie ambassadeur (recrutement → onboarding → digest mensuel → notifications de paiement) |
| **Rewardful / Tolt / Mention Me** | Alternatives à Dub pour la gestion d'affiliation |

### Outillage de revenu

| Outil | Ce qu'il fournit |
|---|---|
| **Stripe MCP** | Tests de pricing, analytics d'abonnement, analyse de cohortes de churn, calcul du CAC blended |
| **Shopify** | Transactions hardware |
| **GA4 MCP** | Événements de revenu |
| **Customer.io MCP** | Cycle de vie lié au paywall / pricing |
| **Notion** | Annuaire de connaissances commerciales |

### Outillage transversal

| Outil | Ce qu'il fournit |
|---|---|
| **Notion** | Base de connaissances partagée |
| **GitHub MCP** | Repo de contexte partagé (`{client-org}/{client-context}`) |
| **defuddle** | Extraction pour la recherche |
| **obsidian-cli** | Notes de travail pour le fCMO |
| **Pencil MCP** | Fichiers de design |
| **Figma MCP** | Fichiers de design (si Figma) |

## Déblocages de capacités par stade de financement

La Section 11 du plan doit inclure ce tableau (ou un équivalent), spécifique aux stades de financement actuel et projeté du client.

| Stade | Effectif | Outillage | Canaux live |
|---|---|---|---|
| **Pre-seed / bootstrappé** | fCMO + équipe fondatrice | Tout l'outillage actuel + bibliothèque marketing-skills + couche MCP | Organic uniquement (SEO, contenu, App Store, social piloté par le fondateur, événements, bouche-à-oreille, ambassadeurs) |
| **Closing du seed** | + premier recrutement marketing (responsable cycle de vie/contenu) | + comptes pub payants (Apple Search Ads, Meta, LinkedIn) + skill `ads` activé | + pilote d'acquisition payante (5–15 K€/mois — voir `funding-stage-unlocks.md` pour les paliers canoniques) |
| **Déploiement du seed** | + designer (potentiellement fractional) | + extension analytics (Mixpanel / Amplitude si besoin) | + scaling payant (20–50 K€/mois) + premiers lancements (PH, GA) |
| **Série A** | + lead performance marketing + lead contenu | + dépense d'outillage dédiée (2–5 K€/mois de logiciels) + budget événements sponsorisés | + scaling payant (50–150 K€/mois) + considération internationale + expansion verticale B2B |
| **Série B+** | Org marketing full-stack (10+ personnes) | + partenariats d'agence + cabinet RP | + campagnes de marque + acquisitions + sponsorings au niveau de la catégorie |

## Le test de l'exemple concret

La Section 11 du plan doit inclure au moins un exemple opérationnel concret qui prouve la thèse du stack. L'exemple doit être :
- Un événement spécifique (pas une affirmation abstraite)
- Issu de l'historique réel de ce client si possible (le plus crédible)
- Lié à une personne non technique qui exécute via le stack (prouve que ça marche sans engineering dédié)

Exemples issus de missions réelles :
- *« Lors de l'appel de kickoff, Alex a rédigé en direct un flow Customer.io de panier abandonné fonctionnel, en utilisant le MCP Claude de Customer.io. A validé qu'un fondateur non technique peut expédier du travail de cycle de vie en autonomie avec le pattern de skill. »*
- *« En deux semaines, l'équipe est passée de 0 à 14 mots-clés positionnés avec `programmatic-seo` contre l'API Ahrefs + le MCP GitHub — sans recrutement SEO dédié. »*
- *« La première campagne email a généré un taux de réponse de 24 % après que `cold-email` + le MCP GA4 + le MCP Stripe ont donné à l'équipe une liste cible vérifiée d'utilisateurs à fort LTV mais sans activité récente. »*

Si le client n'a pas encore eu un tel moment dans son historique, cadrer l'exemple comme le *premier mouvement* — « Voici la démonstration que l'équipe lancera en semaine un pour valider le stack : »

## Quand le stack ne s'applique pas (encore)

Pour les clients sans connexions MCP en place, cadrer la Section 11 différemment :
- Lister les skills qui S'APPLIQUENT avec l'outillage actuel
- Nommer quels MCP débloqueraient quelles sections du plan
- Traiter la mise en place des MCP comme une priorité du T1 aux côtés des correctifs fondamentaux

Un plan ne peut pas revendiquer la thèse du stack agentique si le stack n'est pas branché. Être honnête sur l'état.
