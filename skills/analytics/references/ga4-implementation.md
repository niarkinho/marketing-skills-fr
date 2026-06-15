# Référence d'implémentation GA4

Guide d'implémentation détaillé pour Google Analytics 4.

## Sommaire
- Configuration (flux de données, événements de mesure améliorée, événements recommandés)
- Événements personnalisés (implémentation gtag.js, Google Tag Manager)
- Mise en place des conversions (création de conversions, valeurs de conversion)
- Dimensions et métriques personnalisées (quand les utiliser, étapes de configuration, exemples)
- Audiences (création d'audiences, exemples d'audiences)
- Débogage (DebugView, rapports temps réel, problèmes courants)
- Qualité des données (filtres, tracking cross-domain, paramètres de session)
- Intégration avec Google Ads (liaison, export d'audiences)

## Configuration

### Flux de données

- Un flux par plateforme (web, iOS, Android)
- Activer la mesure améliorée pour le tracking automatique
- Configurer la conservation des données (2 mois par défaut, 14 mois max)
- Activer Google Signals (pour le cross-device, si consenti)

### Événements de mesure améliorée (automatiques)

| Event | Description | Configuration |
|-------|-------------|---------------|
| page_view | Chargements de page | Automatique |
| scroll | 90 % de profondeur de scroll | Activable/désactivable |
| outbound_click | Clic vers un domaine externe | Automatique |
| site_search | Requête de recherche utilisée | Configurer le paramètre |
| video_engagement | Lectures de vidéos YouTube | Activable/désactivable |
| file_download | PDF, docs, etc. | Extensions configurables |

### Événements recommandés

Utilisez les événements prédéfinis de Google quand c'est possible pour un meilleur reporting :

**Toutes propriétés :**
- login, sign_up
- share
- search

**E-commerce :**
- view_item, view_item_list
- add_to_cart, remove_from_cart
- begin_checkout
- add_payment_info
- purchase, refund

**Jeux :**
- level_up, unlock_achievement
- post_score, spend_virtual_currency

Référence : https://support.google.com/analytics/answer/9267735

---

## Événements personnalisés

### Implémentation gtag.js

```javascript
// Événement de base
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});

// Événement avec valeur
gtag('event', 'purchase', {
  'transaction_id': 'T12345',
  'value': 99.99,
  'currency': 'USD',
  'items': [{
    'item_id': 'SKU123',
    'item_name': 'Product Name',
    'price': 99.99
  }]
});

// Propriétés utilisateur
gtag('set', 'user_properties', {
  'user_type': 'premium',
  'plan_name': 'pro'
});

// User ID (pour les utilisateurs connectés)
gtag('config', 'GA_MEASUREMENT_ID', {
  'user_id': 'USER_ID'
});
```

### Google Tag Manager (dataLayer)

```javascript
// Événement personnalisé
dataLayer.push({
  'event': 'signup_completed',
  'method': 'email',
  'plan': 'free'
});

// Définir les propriétés utilisateur
dataLayer.push({
  'user_id': '12345',
  'user_type': 'premium'
});

// Achat e-commerce
dataLayer.push({
  'event': 'purchase',
  'ecommerce': {
    'transaction_id': 'T12345',
    'value': 99.99,
    'currency': 'USD',
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'quantity': 1
    }]
  }
});

// Vider ecommerce avant l'envoi (bonne pratique)
dataLayer.push({ ecommerce: null });
dataLayer.push({
  'event': 'view_item',
  'ecommerce': {
    // ...
  }
});
```

---

## Mise en place des conversions

### Création de conversions

1. **Collecter l'événement** — S'assurer que l'événement se déclenche dans GA4
2. **Marquer comme conversion** — Admin > Événements > Marquer comme conversion
3. **Définir la méthode de comptage** :
   - Une fois par session (leads, inscriptions)
   - Chaque événement (achats)
4. **Importer dans Google Ads** — Pour des enchères optimisées sur la conversion

### Valeurs de conversion

```javascript
// Événement avec valeur de conversion
gtag('event', 'purchase', {
  'value': 99.99,
  'currency': 'USD'
});
```

Ou définir une valeur par défaut dans l'Admin GA4 au moment de marquer la conversion.

---

## Dimensions et métriques personnalisées

### Quand les utiliser

**Dimensions personnalisées :**
- Propriétés par lesquelles vous voulez segmenter/filtrer
- Attributs utilisateur (type d'offre, secteur)
- Attributs de contenu (auteur, catégorie)

**Métriques personnalisées :**
- Valeurs numériques à agréger
- Scores, comptages, durées

### Étapes de configuration

1. Admin > Affichage des données > Définitions personnalisées
2. Créer une dimension ou une métrique
3. Choisir la portée :
   - **Événement** : par événement (content_type)
   - **Utilisateur** : par utilisateur (account_type)
   - **Article** : par produit (product_category)
4. Saisir le nom du paramètre (doit correspondre au paramètre de l'événement)

### Exemples

| Dimension | Portée | Paramètre | Description |
|-----------|-------|-----------|-------------|
| Type d'utilisateur | Utilisateur | user_type | Free, trial, paid |
| Auteur du contenu | Événement | author | Auteur de l'article de blog |
| Catégorie produit | Article | item_category | Catégorie e-commerce |

---

## Audiences

### Création d'audiences

Admin > Affichage des données > Audiences

**Cas d'usage :**
- Audiences de remarketing (export vers Ads)
- Analyse de segments
- Événements déclenchés

### Exemples d'audiences

**Visiteurs à forte intention :**
- Ont vu la page de pricing
- N'ont pas converti
- Sur les 7 derniers jours

**Utilisateurs engagés :**
- 3+ sessions
- Ou 5+ minutes d'engagement total

**Acheteurs :**
- Événement purchase
- Pour exclusion ou lookalike

---

## Débogage

### DebugView

Activer avec :
- Paramètre d'URL : `?debug_mode=true`
- Extension Chrome : GA Debugger
- gtag : `'debug_mode': true` dans la config

À consulter dans : Rapports > Configurer > DebugView

### Rapports temps réel

Vérifier les événements sous 30 minutes :
Rapports > Temps réel

### Problèmes courants

**Événements qui n'apparaissent pas :**
- Vérifier d'abord DebugView
- Vérifier le déclenchement gtag/GTM
- Vérifier les exclusions de filtres

**Valeurs de paramètres manquantes :**
- Dimension personnalisée non créée
- Nom de paramètre qui ne correspond pas
- Données encore en cours de traitement (24-48 h)

**Conversions non enregistrées :**
- Événement non marqué comme conversion
- Le nom de l'événement ne correspond pas
- Méthode de comptage (une fois vs. chaque)

---

## Qualité des données

### Filtres

Admin > Flux de données > [Flux] > Configurer les paramètres du tag > Définir le trafic interne

**Exclure :**
- Adresses IP internes
- Trafic des développeurs
- Environnements de test

### Tracking cross-domain

Pour plusieurs domaines partageant le même analytics :

1. Admin > Flux de données > [Flux] > Configurer les paramètres du tag
2. Configurer vos domaines
3. Lister tous les domaines qui doivent partager les sessions

### Paramètres de session

Admin > Flux de données > [Flux] > Configurer les paramètres du tag

- Délai d'expiration de session (30 min par défaut)
- Durée d'une session engagée (10 sec par défaut)

---

## Intégration avec Google Ads

### Liaison

1. Admin > Liens entre produits > Liens Google Ads
2. Activer le balisage automatique (auto-tagging) dans Google Ads
3. Importer les conversions dans Google Ads

### Export d'audiences

Les audiences créées dans GA4 peuvent être utilisées dans Google Ads pour :
- Les campagnes de remarketing
- Le Customer Match
- Les audiences similaires
