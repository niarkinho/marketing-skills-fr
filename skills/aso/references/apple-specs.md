# Apple App Store — Specs et lignes directrices officielles

Toutes les données proviennent de developer.apple.com, à jour en mars 2026.

## Limites de caractères

| Champ                   | Limite           | Indexé pour la recherche ? | Notes                                                    |
| ----------------------- | ---------------- | -------------------------- | -------------------------------------------------------- |
| Nom de l'app            | 30 car. (min 2)  | Oui                        | Doit être unique ; pas de marques déposées, de noms de concurrents, de tarifs |
| Sous-titre              | 30 car.          | Oui                        | Pas d'affirmations invérifiables                         |
| Mots-clés               | 100 octets       | Oui (caché)                | Virgules, sans espaces entre les termes                  |
| Description             | 4 000 car.       | **Non**                    | Texte brut uniquement, pas de HTML                       |
| Texte promotionnel      | 170 car.         | **Non** (confirmé par Apple) | Modifiable sans nouvelle version                       |
| Nouveautés              | 4 000 car.       | Non                        | Requis pour toutes les versions après la première        |
| Nom d'achat intégré     | 35 car.          | Oui                        | Apparaît en recherche                                    |
| Desc. d'achat intégré   | 55 car.          | Non                        |                                                          |
| Nom d'in-app event      | 30 car.          | Oui                        | Title case requis                                        |
| Desc. courte d'in-app event | 50 car.      | Oui                        | Sentence case                                            |
| Desc. longue d'in-app event | 120 car.     | Non                        | Sentence case                                            |

**Le champ mots-clés fait 100 octets, pas 100 caractères.** Les scripts non latins (arabe,
chinois, japonais, coréen) utilisent 2-3 octets par caractère, réduisant significativement le
nombre effectif de mots-clés.

## Specs des captures d'écran

| Appareil         | Requis ?      | Nombre | Dimensions (portrait)      |
| ---------------- | ------------- | ------ | -------------------------- |
| iPhone 6,9"      | **Requis**    | 1-10   | 1260 x 2736                |
| iPad 13"         | **Requis**    | 1-10   | 2064 x 2752                |
| Mac              | Si applicable | 1-10   | Jusqu'à 2880 x 1800 (16:10) |
| Apple Watch      | Si applicable | 1-10   | Varie selon le modèle      |
| Apple TV         | Si applicable | 1-10   | 1920 x 1080 ou 3840 x 2160 |
| Apple Vision Pro | Si applicable | 1-10   | 3840 x 2160                |

- Formats : JPEG, PNG
- Apple redimensionne automatiquement depuis les tailles de base requises vers les appareils plus petits

## Specs de la vidéo de présentation (App Preview)

- **Nombre :** jusqu'à 3 par app
- **Durée :** 15-30 secondes
- **Taille de fichier max :** 500 Mo
- **Codecs :** H.264 (10-12 Mbps, jusqu'à 30 ips) ou ProRes 422 HQ
- **Audio :** stéréo, 256 kbps AAC ou PCM, 44,1/48 kHz
- **Formats :** .mov, .m4v, .mp4
- **Comportement :** lecture auto en muet sur la fiche produit (iOS 11+)

## Custom Product Pages (CPP)

- **Max :** 70 pages additionnelles (plus 1 par défaut)
- **Personnalisable :** captures d'écran, texte promotionnel, app previews, deep links (iOS 18+)
- **Mots-clés :** chaque combinaison de mots-clés doit être unique à une seule CPP
- **Review :** soumise à l'App Review indépendamment des mises à jour de l'app
- **Recherche organique :** les CPP apparaissent dans les résultats de recherche organique depuis juillet 2025
- **Performance :** +2,5 points de pourcentage de conversion en moyenne vs la page par défaut

## Product Page Optimization (A/B Testing)

- **Traitements :** jusqu'à 3 vs l'original
- **Testable :** icônes d'app, captures d'écran, vidéos de présentation
- **NON testable :** titre, sous-titre, description, mots-clés
- **Tests simultanés :** 1 par app
- **Durée max :** 90 jours
- **Contrainte d'icône :** toutes les variantes d'icône doivent être dans le binaire publié de l'app
- **Confiance :** Apple recommande un seuil de 90% (méthode bayésienne)
- **Impossible de modifier** un test une fois lancé

## In-App Events

- **Max approuvés :** 15 dans App Store Connect à la fois
- **Max publiés :** 10 sur l'App Store simultanément
- **Durée max :** 31 jours par event
- **Promotion pré-event :** jusqu'à 14 jours avant le début
- **Types de badge :** Challenge, Compétition, Live Event, Mise à jour majeure, Nouvelle saison, Première, Event spécial

**Image de carte d'event :** 16:9, min 1920x1080, max 3840x2160
**Image de détails d'event :** 9:16, min 1080x1920, max 2160x3840

**Non adapté :** tâches quotidiennes répétitives, promotions de prix sans nouveau contenu, campagnes de notoriété générale.

## Notes et avis

- **SKStoreReviewController :** max 3 invites par période de 365 jours
- Le système contrôle la fréquence d'affichage (peut en montrer moins de 3)
- Ne pas utiliser de boutons personnalisés pour demander des avis
- Les développeurs peuvent répondre à tous les avis dans App Store Connect
- La note de synthèse est spécifique au territoire

## Déclencheurs de rejet des métadonnées (App Review Guidelines)

| Guideline | Déclencheur de rejet                                                      |
| --------- | ------------------------------------------------------------------------- |
| 2.3.1     | Fonctionnalités cachées, marketing trompeur, faux tarifs                  |
| 2.3.2     | Ne pas divulguer les achats intégrés dans la description/captures         |
| 2.3.3     | Captures qui ne montrent pas l'app en usage (uniquement splash/login)     |
| 2.3.4     | Vidéos de présentation utilisant du contenu hors-app                      |
| 2.3.5     | Mauvaise catégorie sélectionnée                                           |
| 2.3.7     | Bourrage de mots-clés : marques déposées, noms de concurrents, tarifs, termes hors-sujet |
| 2.3.8     | Métadonnées inappropriées pour tous les publics (doit être noté 4+)       |
| 2.3.10    | Noms/imagerie d'autres plateformes (Android, etc.) dans les métadonnées   |
| 2.3.12    | Nouveautés génériques pour des changements significatifs                  |
| 2.3.13    | Métadonnées d'in-app event inexactes                                      |

Sources : developer.apple.com/app-store/product-page/,
developer.apple.com/app-store/search/,
developer.apple.com/app-store/review/guidelines/
