# Référence prospection PME locale

Pour quand l'utilisateur vend à de petites entreprises locales — boutiques, salles de sport, restaurants, salons, cliniques, services professionnels, artisans, immobilier, studios de fitness, cabinets dentaires.

Adapté et généralisé à partir du pattern local-client-prospector (découverte assistée par navigateur + classification du statut de site web + scoring de proximité).

---

## Signaux ICP qui comptent (branche PME locale)

### Signaux opérationnels

- **Entreprise active** — fiche Google Business Profile à jour, avis récents, mises à jour récentes des horaires
- **Activité récente** — ouvert en ce moment, horaires réguliers affichés, photos récentes mises en ligne par le gérant
- **Engagement client** — gérant répondant aux avis, posts sur les réseaux, calendrier actif (pour les entreprises de service)

### Signaux de présence en ligne (l'axe de qualification central des PME)

Le skill de référence local-client-prospector utilise le **statut du site web** comme qualification principale — à reprendre tel quel. Quatre classifications :

| Statut | Définition | Résultat typique |
|--------|-----------|-----------------|
| **Aucun site trouvé** | Aucun site web autonome crédible après recherche recoupée | **Prospect chaud** pour service web/marketing |
| **Réseaux uniquement** | Facebook, Instagram, WhatsApp, Linktree, portail de réservation, page de marketplace uniquement — pas de site autonome | **Prospect chaud** pour service web/marketing |
| **Site faible** | Un site autonome existe mais obsolète, cassé, très pauvre, non mobile-friendly, ou sans flux clair de contact/conversion | **Prospect tiède** pour service de refonte / reconstruction |
| **A un site** | Un site autonome crédible et moderne existe | **Prospect faible** sauf si d'autres signaux s'appliquent (ex : SEO médiocre, design de conversion faible) |

### Signaux de proximité

- **Distance** par rapport à la localisation ou la zone de service de l'utilisateur
- **Densité** — des grappes d'entreprises similaires dans une même zone = opportunité de ciblage par quartier
- **Temps de trajet** — utile quand une découverte, une installation ou une prestation en personne est nécessaire

### Signaux de déclin

- Fermé définitivement (bandeau Google Maps)
- Avis suspendus ou fiche d'entreprise signalée comme fermée
- Dernière activité (avis, post) il y a plus de 12 mois

---

## Sources de découverte (branche PME locale)

### Principales

- **Google Maps** (navigateur, manuel) — chercher « catégorie près de [localisation] » et parcourir les résultats visibles. Recouper les détails. Ne pas extraire en masse.
- **Yelp** — vérification secondaire ; catégories complémentaires
- **Bing Local / Apple Maps** — couverture différente sur les petites entreprises
- **Recherche de Pages Facebook** — beaucoup de PME sont uniquement sur Facebook

### Recoupement

- **Le propre site web de l'entreprise** (s'il existe)
- **Annuaires sectoriels** (ex : Healthgrades pour le médical, OpenTable pour la restauration, Avvo pour le juridique)
- **Listes de la chambre de commerce locale**
- **Registres d'entreprises nationaux** pour le statut d'immatriculation
- **Résultats de recherche pour « [nom de l'entreprise] [ville] »** pour découvrir une présence hors Maps

---

## Workflow de recherche au navigateur

1. Ouvrir un navigateur et chercher sur Google Maps la catégorie près de `base_location`
2. Constituer une liste de candidats à partir des résultats locaux visibles, des résultats de recherche et des annuaires publics
3. Pour chaque candidat, inspecter les sources publiques pour remplir les champs requis
4. Chercher le nom exact de l'entreprise plus la ville/commune pour vérifier l'existence d'un site web autonome
5. Classer le statut du site web selon le tableau ci-dessus
6. Indiquer la confiance : Élevée (2+ sources), Moyenne (1 source + preuve cohérente), Faible (incomplet/ambigu)

Quand l'utilisateur demande explicitement des sous-agents ET que des sous-agents sont disponibles, répartir les candidats en lots non chevauchants et demander à chaque sous-agent de vérifier uniquement le statut site/réseaux/contact. Ne pas utiliser de sous-agents pour la recherche principale si cela ralentit la progression.

### Optionnel : vérification programmatique avec Firecrawl ou Browserbase

Une fois que vous avez l'URL du site d'un candidat (trouvée par découverte manuelle Maps/Yelp), vous pouvez accélérer la classification du statut du site en interrogeant l'URL programmatiquement :

- **Firecrawl** pour des lectures simples « ce site est-il en ligne, moderne, mobile-friendly, équipé d'un flux de conversion » — retourne un markdown propre que vous pouvez inspecter
- **Browserbase** quand le site candidat nécessite un rendu JS, a un dialogue de consentement aux cookies, ou que vous avez besoin de l'état de session

**Ligne stricte** : utiliser ces outils sur l'URL de l'entreprise individuelle. **Ne pas** les pointer vers Google Maps, Yelp ou toute plateforme dont les ToS interdisent l'extraction en masse — la découverte reste manuelle.

Voir [data-sources.md](data-sources.md) pour les détails de configuration.

---

## Checklist de qualification (branche PME locale)

- [ ] L'entreprise est active (avis ou activité récents dans les 6 derniers mois)
- [ ] La catégorie correspond à l'offre de service de l'utilisateur
- [ ] Distance / proximité dans le rayon cible
- [ ] Statut du site web classé
- [ ] Téléphone ou canal de contact vérifié
- [ ] Au moins une source recoupée confirme que l'entreprise opère à l'adresse indiquée
- [ ] Pas un doublon / un point de chaîne / une catégorie hors périmètre
- [ ] Pas fermé définitivement

---

## Scoring des leads (PME locale)

Utiliser ce barème simple (cohérent avec le pattern local-client-prospector) :

| Score | Critères |
|-------|----------|
| **Chaud** | Aucun site trouvé OU réseaux uniquement + téléphone présent + entreprise active + dans le rayon cible |
| **Tiède** | Site faible, présentation en ligne médiocre, ou page de marketplace/réservation uniquement |
| **Froid** | Bon site web déjà présent OU faible confiance |
| **À écarter** | Fermé, doublon, hors rayon, catégorie hors sujet, ou pas un prospect d'entreprise |

---

## Colonnes de sortie (branche PME locale)

Tableau de chat (≤15 lignes) :

```
| Score | Commerce | Catégorie | Zone | Distance | Statut site web | Site/Réseaux | Téléphone | Pourquoi c'est un prospect | Confiance |
```

CSV :

```csv
score,business,category,area,distance_km,website_status,website_url,social_urls,phone,email,source_urls,why_prospect,confidence,verified_date,notes
```

Règles :
- Garder « Pourquoi c'est un prospect » court et actionnable
- Utiliser `Non trouvé` plutôt que de laisser des champs vides
- Inclure les liens sources avec parcimonie, pas tous
- Après le tableau, ajouter **Meilleures cibles de premier outreach** avec les 3 meilleurs leads et une raison pratique chacun
- Si la confiance est faible, indiquer précisément ce qui reste incertain

---

## Sélection des cibles d'outreach prioritaires (PME locale)

Prioriser, pour les 3 meilleurs leads chauds :

1. **Aucun site / réseaux uniquement + téléphone présent** = opportunité de service la plus nette
2. **Nombre d'avis élevé** = entreprise active, établie, avec de vrais clients
3. **Avis avec réponse du gérant** = gérant engagé = plus susceptible d'évaluer un prestataire
4. **Alignement sectoriel avec votre spécialité de service** bat un match de catégorie générique

La justification de chaque cible prioritaire doit tenir en une phrase nommant le manque et le signal : « Pas de site web autonome (recoupé) ; 80+ avis Google avec réponses du gérant ; à 2 km de la zone cible. »

---

## Notes de conformité (spécifiques PME locale)

La branche locale est la plus sensible au scraping des trois motions. Concrètement :

- **Les conditions d'utilisation de Google Maps** interdisent l'extraction en masse. Traiter les visites au navigateur comme de la recherche, pas comme de l'acquisition de données.
- **Ne pas stocker les Place IDs complets de Google Maps dans votre CRM** — les ToS limitent le stockage des données Maps.
- **Canaux de contact professionnels publics uniquement** : téléphone publié, formulaire de contact, email info@. Ne pas joindre des employés individuels via leurs canaux personnels.
- **Le nom du gérant/exploitant quand il est publié sur le propre site de l'entreprise** est OK à utiliser. Si vous ne l'avez obtenu que via LinkedIn, indiquer la source.

---

## Erreurs fréquentes (PME locale)

1. **Scraper Google Maps en masse** — le moyen le plus rapide de violer les ToS et de perdre le canal de recherche.
2. **Traiter les données Google Maps comme une vérité** — les fiches se périment. Recouper horaires, statut et avis.
3. **Sauter le recoupement du statut du site** — trouver « pas de site » sur Maps ne veut pas dire qu'aucun site n'existe ; faire une recherche web sur le nom exact avant de classer.
4. **Ne cibler que les plus grosses entreprises** — elles sont déjà couvertes par d'autres prestataires. Les PME de 2–5 salariés sont l'opportunité sous-servie.
5. **Outreach générique vers tous les leads chauds** — les PME locales répondent mieux à un outreach qui nomme leur manque précis (« j'ai remarqué que votre menu n'est pas visible sur mobile ») qu'à des pitchs génériques.
6. **Écarter d'office chaînes et franchises** — parfois le franchisé est l'acheteur et il a une autorité marketing locale. Vérifier avant d'écarter.
