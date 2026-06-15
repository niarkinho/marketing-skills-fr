# Cadre AARRR — Primer pour le séquençage du plan

AARRR (les « pirate metrics » de Dave McClure) est l'épine dorsale de chaque plan produit par ce skill. Ce doc est le primer + les règles de décision pour savoir quand chaque stade est priorisé.

## Les cinq stades

| Stade | Question | Métriques courantes |
|---|---|---|
| **A**cquisition | Comment des inconnus prennent-ils conscience de nous ? | Visites, MQLs, sessions de la page signup, visites app-store, CAC par canal |
| **A**ctivation | Une fois qu'ils nous essaient, vivent-ils une expérience qui convertit ? | Taux de complétion du signup, time-to-value, % complétant la première action clé, taux essai → payant |
| **R**étention | Restent-ils et approfondissent-ils ? | DAU/WAU/MAU, rétention semaine-1/4/12, churn |
| **R**éférencement (Referral) | Les utilisateurs retenus amènent-ils plus d'utilisateurs ? | Coefficient viral, NPS, attribution ambassadeur |
| **R**evenu | Que paient-ils, qui paie, comment ça se cumule ? | ARPU, LTV, expansion revenue, ARR / MRR |

> **Règle de la frontière signup.** L'*intention* de signup (un inconnu qui atterrit sur la page signup) relève de l'Acquisition. La *complétion* du signup et tout ce qui suit (première action clé, essai-vers-payant) relève de l'Activation. Appliquer cette règle de façon cohérente dans tous les docs et le template de plan.

## Pourquoi AARRR pour le séquençage du plan

Trois raisons.

**1. Tagguer par stade de funnel force la priorisation.** Sans AARRR, les plans marketing deviennent organisés par canal (« voici le plan SEO, voici le plan social, voici le plan paid »). Les canaux peuvent adresser plusieurs stades ; tagguer par stade pose plutôt la question plus utile : *quel stade du funnel est la contrainte limitante en ce moment ?*

**2. Réparer la fuite avant de verser de l'eau.** La question Activation/Rétention (« le funnel convertit-il à des taux acceptables compte tenu de l'exposition ? ») est généralement à plus fort levier que la question Acquisition (« comment obtenir plus d'exposition ? »). Le séquençage AARRR fait remonter ça naturellement.

**3. La conversation Revenu / Recommandation est honnête.** La plupart des plans marketing enterrent la monétisation sous la « croissance » et traitent le recommandation comme un vœu pieux. AARRR force un traitement explicite des deux.

## Marque et contenu — pas un stade, transversaux

Erreur courante : faire de la « Marque » ou du « Contenu » le sixième bucket. Ils n'en sont pas un — ils servent chaque stade.

- **La brand voice** gouverne chaque pièce de copy à travers chaque stade
- **Le contenu** alimente l'Acquisition (SEO, social), l'Activation (copy d'onboarding), la Rétention (email lifecycle), le Recommandation (talking points ambassadeurs), le Revenu (pages de pricing, supports de vente)

Dans le plan, marque/contenu apparaissent comme le cadre stratégique (Section 2) et en transversal dans l'ops stack de la Section 11 — jamais comme leur propre section AARRR.

## Diagnostiquer la contrainte limitante — quel stade AARRR est à plus fort levier ?

Pour chaque client, un ou deux stades AARRR seront la contrainte limitante. Le plan séquence les mouvements là d'abord.

**Règles de décision :**

### Si vous n'avez aucun utilisateur → commencer par l'Acquisition
- Stade pré-lancement / jour-0 / waitlist
- Aucune donnée de funnel n'existe
- Levier = construire les 100 premiers utilisateurs

### Si vous avez des utilisateurs mais ils rebondissent → commencer par l'Activation
- Des signups arrivent mais le taux d'activation est faible
- La conversion App Store est mauvaise
- La complétion de l'onboarding est cassée
- Le taux Jour 1 → payant est bien plus bas que le taux Jour 30 → payant (signifie que le produit convertit avec le temps mais que l'onboarding ne fait pas le pont)
- Levier = faire le pont entre signup et première valeur ressentie

### Si l'activation marche mais les utilisateurs churnent → commencer par la Rétention
- La rétention au mois 1 est en dessous des normes de la catégorie
- Les utilisateurs activés cessent d'utiliser en 7–14 jours
- La LTV est courte
- Levier = lifecycle, approfondissement de l'engagement, prévention du churn

### Si la rétention est forte mais la croissance est lente → commencer par Recommandation / Revenu
- Les utilisateurs retenus adorent le produit mais ne le partagent pas
- Les recommandations entrants arrivent de façon non structurée
- Le pricing n'a pas été pressure-testé
- L'ARPU est faible pour la valeur délivrée
- Levier = mécaniques de bouche-à-oreille + optimisation du pricing (ces deux-là vont souvent ensemble)

### Si tout marche à petite échelle → commencer par l'Acquisition (scaling)
- Le funnel est sain
- La question est juste « plus »
- C'est le problème de scaling « post-fit »

## Patterns stratégiques stade par stade

### Acquisition

**La question diagnostique :** Où est l'écart entre la notoriété au niveau TAM et le volume actuel du funnel ? Quels canaux sont saturés par les concurrents vs. ouverts ?

**Mouvements d'Acquisition courants :**
- Stratégie de contenu SEO (cumul organique)
- Canaux founder-led (LinkedIn, X, Substack pour le B2B ; Instagram/TikTok pour le D2C)
- Acquisition paid (quand le budget se débloque)
- Optimisation de fiche App Store / Play Store / marketplace
- RP et amplification d'ancres de crédibilité
- Événements (live, webinaire, prise de parole en conférence)
- Partenariats (échanges de newsletters, co-marketing d'intégration, partenaires revendeurs / agences)
- Surface hardware / commerce (Shopify SEO + Amazon pour les business hybrides)
- Support de vente B2B (études de cas, pages partenaires, contenu vertical)

**Principe de séquençage :** Construire le cumul organique d'abord (SEO + founder-led + contenu + amplification RP + ambassadeurs). Ne superposer le paid que par-dessus une baseline organique qui marche. Du paid prématuré amplifie ce qui est cassé.

### Activation

**La question diagnostique :** Où, dans la première session de l'utilisateur, décide-t-il « ça marche pour moi » ou « ça ne marche pas » ? Qu'est-ce qui l'empêche d'atteindre ce moment ?

**Mouvements d'Activation courants :**
- Corrections de socle (barrières cassées, étapes de signup cassées, paywall cassé)
- Tests / refonte d'onboarding (souvent le mouvement unique à plus fort levier)
- Réécriture de la fiche App Store (le seuil vers l'essai)
- Ordre de livraison des Lifecycle Flows (quand livrer les emails d'onboarding)
- Structure du paywall + durée d'essai
- Pont free → payant (upsells in-app, soft paywalls)

**Principe de séquençage :** Atteindre la première valeur ressentie le plus vite possible. Tout ce qui ajoute de la friction entre « l'utilisateur ouvre l'app » et « l'utilisateur vit l'expérience qui le convertit » est un candidat à couper.

### Rétention

**La question diagnostique :** Pourquoi les utilisateurs churnent-ils ? Qu'est-ce qui les aurait fait rester ? Quel est le « deuxième moment de valeur » après le premier ?

**Mouvements de Rétention courants :**
- Flows email lifecycle : onboarding, réengagement d'utilisateurs inactifs, post-achat, win-back
- Centres d'abonnement / de préférences
- Réconciliation du churn (souvent les définitions de métriques ne correspondent pas d'une surface à l'autre)
- Chemins d'activation hardware → software (pour les business hybrides)
- Plan annuel par défaut / structure de pricing (transversal au Revenu)
- Support en tant que marketing (moments high-touch qui génèrent des histoires)
- Communauté + réseaux de praticiens

**Principe de séquençage :** Livrer les flows lifecycle dans l'ordre où leur contenu est le plus stable. Les flows post-achat hardware se livrent en premier (ils ne référencent pas des écrans in-app qui pourraient changer). Les emails d'onboarding se livrent en dernier (ils référencent une UI qui pourrait changer). Le win-back est une campagne trimestrielle, pas un flow one-time.

### Recommandation (Referral)

**La question diagnostique :** Existe-t-il un intérêt de recommandation entrant qui n'est pas capturé ? Quel est le moment de partage-après-valeur naturel au produit ?

**Mouvements de Recommandation courants :**
- Programme ambassadeurs / affiliés (commencer avec l'intérêt entrant, pas le recrutement à froid)
- Moments de partage-après-valeur intégrés au produit (prompts de réflexion, célébrations de jalons)
- Amplification par le fondateur (le fondateur comme parrain-zéro)
- Réseaux d'experts / Guides / hôtes-certifiés de long terme (pour les business créateurs de catégorie)
- Flows de gifting (grand public / hardware)
- Recommandations bilatéraux (récompenser à la fois le parrain et le référé)

**Principe de séquençage :** Commencer avec quiconque lève déjà la main. S'il y a 5 ambassadeurs entrants, lancer avec ces 5 — ne pas attendre un « programme complet ». Itérer selon ce qu'ils vous disent.

### Revenu

**La question diagnostique :** L'entreprise sous-tarife-t-elle ? Sous-package-t-elle ? Manque-t-elle un upsell ? Quelle est la « bonne » discipline de prix compte tenu de la LTV et de la brand voice ?

**Mouvements de Revenu courants :**
- Audit de pricing (qu'est-ce qui est réellement facturé aujourd'hui vs. affiché ?)
- Plan annuel par défaut
- Formalisation du bundling hardware → software
- Optimisation de la page storefront / commerce
- Études de cas B2B + supports de vente
- Flags de pools de valeur de long terme (data, expansion, enterprise) — flaggés, pas exécutés

**Principe de séquençage :** Lancer l'audit de pricing avant de tester des changements. Étonnamment souvent, le pricing « implicite » du dashboard ne correspond pas au prix affiché — remises, essais ou mix de plans faussent la lecture. Faire remonter la vérité terrain d'abord.

## Comment assigner un mouvement à un stade

Certains mouvements appartiennent clairement à un stade. D'autres s'étendent. La règle :

**Assigner au stade où atterrit l'impact mesurable principal du mouvement.**

Exemples :
- « Réécrire la fiche App Store dans la voix » — s'étend sur l'Acquisition (découverte organique) et l'Activation (seuil vers l'essai). Impact principal = Activation (taux de conversion d'essai). Assigner à l'Activation, mentionner le crossover.
- « Réécriture de la page Shopify du masque de nuit » — s'étend sur l'Acquisition (recherche organique pour masque de sommeil) et le Revenu (conversion de vente). Impact principal = Revenu (transaction). Assigner au Revenu, mentionner le crossover.
- « Cadence LinkedIn d'Alex » — Acquisition (haut de funnel pour les abonnés D2C).
- « Customer.io Flow 6 (post-achat masque de nuit) » — Rétention (approfondit l'engagement de l'acheteur hardware) avec crossover vers l'Activation (chemin d'activation hardware → app premium).

En cas de doute : où le retrait de ce mouvement ferait-il le plus mal ? Assigner là.

## Quand la répartition AARRR n'est pas égale

Pour la plupart des clients, le plan n'aura pas un volume égal entre stades. C'est normal — et ça vaut la peine de le faire remonter comme diagnostic.

- **Section Acquisition lourde** = le client a un product-market fit mais le haut de funnel est le goulot. Courant pour l'early-stage avec de fortes métriques de rétention.
- **Section Activation lourde** = le client a du trafic mais la conversion est cassée. Souvent des produits en stade beta.
- **Section Rétention lourde** = le client a un problème de churn. Souvent des produits mid-stage qui ont scalé au-delà du PMF sans infrastructure lifecycle.
- **Section Recommandation lourde** = le client a de la loyauté mais pas de mécaniques de bouche-à-oreille. Souvent des produits grand public avec des utilisateurs passionnés.
- **Section Revenu lourde** = le client sous-tarife ou manque des couches de monétisation. Courant pour les outils en transition du gratuit vers le payant.

Si un plan finit réparti uniformément entre les cinq stades, le diagnostic était probablement faible — réexaminer l'intake sur l'état du funnel pour trouver où est la contrainte limitante.

## Une note sur l'ordre de présentation

Toujours présenter AARRR dans l'ordre (Acquisition → Activation → Rétention → Recommandation → Revenu) quel que soit l'ordre de priorité.

C'est pour le modèle mental du lecteur. Les fondateurs s'attendent à ce que le funnel coule de haut en bas. Si la Rétention est le stade à plus fort levier mais que vous commencez par la Rétention, le lecteur doit faire un context-switch.

Pour signaler la priorité, utiliser le résumé exécutif (Section 1) — y nommer les plus grands paris. La répartition AARRR parcourt ensuite le funnel dans l'ordre, la section la plus levier-positive étant la plus longue et la plus détaillée.
