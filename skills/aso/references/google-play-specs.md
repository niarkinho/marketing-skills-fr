# Google Play Store — Specs et lignes directrices officielles

Toutes les données proviennent de support.google.com et developer.android.com, à jour en mars 2026.

## Limites de caractères

| Champ                | Limite      | Indexé ?               | Notes                                 |
| -------------------- | ----------- | ---------------------- | ------------------------------------- |
| Titre de l'app       | 30 car.     | Oui (signal le plus fort) | Réduit de 50 en septembre 2021     |
| Description courte   | 80 car.     | Oui                    | Visible sans déplier                  |
| Description complète | 4 000 car.  | **Oui (fortement)**    | Le NLP de Google indexe tout le texte |
| Nom du développeur   | 64 car.     | Partiel                | Mêmes restrictions emoji/majuscules que le titre |

## Interdit dans les métadonnées (appliqué depuis septembre 2021)

**Titre, icône, nom du développeur :**

- Emojis, émoticônes, caractères spéciaux répétés
- MAJUSCULES (sauf marque déposée)
- Affirmations de performance : « top », « best », « #1 », « free », « no ads »
- Performance ou recommandation trompeuse dans le store
- Appels à l'action : « update now », « download now »

**Description courte :**

- Mêmes affirmations de performance que le titre
- Appels à l'action
- Témoignages non attribués

**Captures d'écran, feature graphic, vidéo :**

- Accroches limitées dans le temps
- Appels à l'action (« Download now », « Play now »)
- Doivent présenter authentiquement les fonctionnalités de l'app

## Specs des captures d'écran

| Appareil    | Min   | Max   | Ratio d'aspect | Résolution min | Bord long max |
| ----------- | ----- | ----- | -------------- | -------------- | ------------- |
| Téléphone   | **2** | **8** | 9:16 ou 16:9   | 320px côté quelconque | 3 840px |
| Tablette 7" | 4     | 8     | 9:16 ou 16:9   | 1 080px côté court | 7 680px  |
| Tablette 10" | 4    | 8     | 9:16 ou 16:9   | 1 080px côté court | 7 680px  |
| Chromebook  | 4     | 8     | 9:16 ou 16:9   | 1 080px côté court | 7 680px  |
| Wear OS     | 1     | 8     | **1:1**        | 384x384        | 3 840px       |
| Android TV  | 1     | 8     | **16:9**       | 1 920x1 080    | 3 840px       |

- **Taille téléphone recommandée :** 1080x1920 (portrait)
- **Format :** JPEG ou PNG 24 bits (sans alpha)
- **Taille de fichier max :** 8 Mo chacune

**Note :** le max Google Play est de 8 captures par appareil, pas 10 comme Apple.

## Feature Graphic

- **Dimensions :** 1024 x 500 px (exact, requis)
- **Format :** JPEG ou PNG 24 bits (sans alpha)
- Affichée en haut de la fiche et dans les placements en avant

## Icône de l'app

- **Dimensions :** 512 x 512 px
- **Format :** PNG 32 bits (avec alpha)
- **Taille de fichier max :** 1 024 Ko
- **Forme :** carré plein (Google applique automatiquement un rayon d'angle de 30%)
- **Interdit :** affirmations de classement, nombre de téléchargements, texte d'offre, emoji

## Vidéo de présentation

- **Format :** URL YouTube (publique ou non répertoriée)
- **Durée :** 30 secondes à 2 minutes recommandé
- Pas de pub, pas de monétisation, doit être intégrable, sans restriction d'âge
- **NE se lance PAS automatiquement** (seulement ~6% des visiteurs lancent la lecture)

## Store Listing Experiments (A/B Testing)

- **Variantes :** jusqu'à 3 par expérience (plus le contrôle)
- **Testable :** icône, feature graphic, captures, vidéo, description courte, description complète
- **Simultané :** impossible de lancer plus d'une expérience de graphiques par défaut en même temps
- **Audience :** uniquement les utilisateurs Google Play connectés
- **Métriques :** premiers installateurs + premiers installateurs retenus (rétention à 1 jour)
- **Durée :** lancer au moins 7 jours (variance semaine/week-end)
- **Localisé :** tester sur jusqu'à 5 langues simultanément

## Custom Store Listings

- **Max :** 50 par app (100 pour les partenaires Play)
- **Personnalisable :** titre, description courte/complète, icône, captures, feature graphic, vidéo
- **Ciblage :** pays/région, pré-inscription, état d'installation, campagnes Google Ads, utilisateurs inactifs/churned (28+ jours)
- **Ajout 2025 :** Gemini AI génère automatiquement le texte des CSL dans Play Console

## Contenu promotionnel (LiveOps)

| Type              | Description                       | Durée                |
| ----------------- | -------------------------------- | -------------------- |
| Offres            | Remises, articles gratuits, bundles | Jusqu'à 28 jours  |
| Events            | In-app events limités dans le temps | Doit avoir une limite de temps |
| Mise à jour majeure | Nouvelles fonctionnalités importantes | Max 1 semaine    |
| Crossover (jeux)  | Collaboration cross-jeu/IP       | Variable             |

- Soumettre **4+ jours** avant le début (review standard)
- Soumettre **14+ jours** avant pour les demandes de mise en avant
- **Impact :** « Plus de deux fois plus d'acquisitions explore pendant la mise en avant » (Google officiel)

## Android Vitals — Seuils de classement

Les apps dépassant ces seuils obtiennent une **visibilité réduite** en recherche et recommandations.

| Métrique                     | Seuil global      | Seuil par appareil   |
| ---------------------------- | ----------------- | -------------------- |
| Taux de crash perçu par l'utilisateur | **1,09%**  | 8%                   |
| Taux d'ANR perçu par l'utilisateur | **0,47%**    | 8%                   |
| Wake locks partiels excessifs | 5%               | N/A                  |

**Conséquences :** visibilité de recherche réduite, labels d'avertissement sur la fiche, alertes qualité aux utilisateurs avant install.
**Récupération :** Google vérifie quotidiennement sur une moyenne glissante de 28 jours.

## Classement en recherche — Facteurs officiels

Google confirme que ceux-ci affectent le classement :

1. **Pertinence des métadonnées** — Le titre porte le plus de poids. Le NLP scanne titre + desc. courte + desc. complète.
2. **Qualité de l'app** — Android Vitals (taux de crash/ANR)
3. **Notes et avis** — Note en étoiles + texte des avis. 85% des apps mises en avant ont 4,0+
4. **Volume et vélocité d'installs** — Total des installs + fréquence quotidienne/hebdomadaire
5. **Engagement et rétention** — Fréquence des sessions, durée, taux de rétention
6. **Fréquence des mises à jour** — Des mises à jour régulières signalent une maintenance active
7. **Localisation** — Adaptation régionale des mots-clés/visuels. 59% des apps US localisent leurs titres.

Sources : support.google.com/googleplay/android-developer/answer/4448378,
support.google.com/googleplay/android-developer/answer/9898842,
developer.android.com/topic/performance/vitals
