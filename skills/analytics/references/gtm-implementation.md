# Référence d'implémentation Google Tag Manager

Guide détaillé pour mettre en place le tracking via Google Tag Manager.

## Sommaire
- Structure du conteneur (tags, déclencheurs, variables)
- Conventions de nommage
- Patterns du data layer
- Configurations de tags courantes (tag de configuration GA4, tag d'événement GA4, pixel Facebook)
- Aperçu et débogage
- Espaces de travail et versioning
- Gestion du consentement
- Patterns avancés (séquençage de tags, gestion des exceptions, variables JavaScript personnalisées)

## Structure du conteneur

### Tags

Les tags sont des bouts de code qui s'exécutent quand ils sont déclenchés.

**Types de tags courants :**
- GA4 Configuration (mise en place de base)
- GA4 Event (événements personnalisés)
- Conversion Google Ads
- Pixel Facebook
- Balise LinkedIn Insight
- HTML personnalisé (pour d'autres pixels)

### Déclencheurs (triggers)

Les déclencheurs définissent quand les tags se déclenchent.

**Déclencheurs intégrés :**
- Page vue : Toutes les pages, DOM Ready, Window Loaded
- Clic : Tous les éléments, Liens uniquement
- Soumission de formulaire
- Profondeur de scroll
- Minuteur
- Visibilité d'élément

**Déclencheurs personnalisés :**
- Événement personnalisé (depuis le dataLayer)
- Groupes de déclencheurs (conditions multiples)

### Variables

Les variables capturent des valeurs dynamiques.

**Intégrées (à activer au besoin) :**
- Click Text, Click URL, Click ID, Click Classes
- Page Path, Page URL, Page Hostname
- Referrer
- Form Element, Form ID

**Définies par l'utilisateur :**
- Variables Data Layer
- Variables JavaScript
- Tables de correspondance (lookup tables)
- Tables RegEx
- Constantes

---

## Conventions de nommage

### Format recommandé

```
[Type] - [Description] - [Détail]

Tags :
GA4 - Event - Signup Completed
GA4 - Config - Base Configuration
FB - Pixel - Page View
HTML - LiveChat Widget

Déclencheurs :
Click - CTA Button
Submit - Contact Form
View - Pricing Page
Custom - signup_completed

Variables :
DL - user_id
JS - Current Timestamp
LT - Campaign Source Map
```

---

## Patterns du data layer

### Structure de base

```javascript
// Initialiser (dans <head> avant GTM)
window.dataLayer = window.dataLayer || [];

// Pousser un événement
dataLayer.push({
  'event': 'event_name',
  'property1': 'value1',
  'property2': 'value2'
});
```

### Données au chargement de la page

```javascript
// Définir au chargement de la page (avant le conteneur GTM)
window.dataLayer = window.dataLayer || [];
dataLayer.push({
  'pageType': 'product',
  'contentGroup': 'products',
  'user': {
    'loggedIn': true,
    'userId': '12345',
    'userType': 'premium'
  }
});
```

### Soumission de formulaire

```javascript
document.querySelector('#contact-form').addEventListener('submit', function() {
  dataLayer.push({
    'event': 'form_submitted',
    'formName': 'contact',
    'formLocation': 'footer'
  });
});
```

### Clic sur bouton

```javascript
document.querySelector('.cta-button').addEventListener('click', function() {
  dataLayer.push({
    'event': 'cta_clicked',
    'ctaText': this.innerText,
    'ctaLocation': 'hero'
  });
});
```

### Événements e-commerce

```javascript
// Vue produit
dataLayer.push({ ecommerce: null }); // Vider le précédent
dataLayer.push({
  'event': 'view_item',
  'ecommerce': {
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'item_category': 'Category',
      'quantity': 1
    }]
  }
});

// Ajout au panier
dataLayer.push({ ecommerce: null });
dataLayer.push({
  'event': 'add_to_cart',
  'ecommerce': {
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'quantity': 1
    }]
  }
});

// Achat
dataLayer.push({ ecommerce: null });
dataLayer.push({
  'event': 'purchase',
  'ecommerce': {
    'transaction_id': 'T12345',
    'value': 99.99,
    'currency': 'USD',
    'tax': 5.00,
    'shipping': 10.00,
    'items': [{
      'item_id': 'SKU123',
      'item_name': 'Product Name',
      'price': 99.99,
      'quantity': 1
    }]
  }
});
```

---

## Configurations de tags courantes

### Tag de configuration GA4

**Type de tag :** Google Analytics : GA4 Configuration

**Paramètres :**
- Measurement ID : G-XXXXXXXX
- Envoyer une page vue : Coché (pour les pages vues)
- User Properties : Ajouter toute dimension au niveau utilisateur

**Déclencheur :** Toutes les pages

### Tag d'événement GA4

**Type de tag :** Google Analytics : GA4 Event

**Paramètres :**
- Configuration Tag : Sélectionner votre tag de config
- Event Name : {{DL - event_name}} ou en dur
- Event Parameters : Ajouter les paramètres depuis le dataLayer

**Déclencheur :** Événement personnalisé avec correspondance du nom d'événement

### Pixel Facebook - Base

**Type de tag :** HTML personnalisé

```html
<script>
  !function(f,b,e,v,n,t,s)
  {if(f.fbq)return;n=f.fbq=function(){n.callMethod?
  n.callMethod.apply(n,arguments):n.queue.push(arguments)};
  if(!f._fbq)f._fbq=n;n.push=n;n.loaded=!0;n.version='2.0';
  n.queue=[];t=b.createElement(e);t.async=!0;
  t.src=v;s=b.getElementsByTagName(e)[0];
  s.parentNode.insertBefore(t,s)}(window, document,'script',
  'https://connect.facebook.net/en_US/fbevents.js');
  fbq('init', 'YOUR_PIXEL_ID');
  fbq('track', 'PageView');
</script>
```

**Déclencheur :** Toutes les pages

### Pixel Facebook - Événement

**Type de tag :** HTML personnalisé

```html
<script>
  fbq('track', 'Lead', {
    content_name: '{{DL - form_name}}'
  });
</script>
```

**Déclencheur :** Événement personnalisé - form_submitted

---

## Aperçu et débogage

### Mode aperçu

1. Cliquer sur « Aperçu » dans GTM
2. Saisir l'URL du site
3. Le panneau de débogage GTM s'ouvre en bas

**Quoi vérifier :**
- Tags déclenchés sur cet événement
- Tags non déclenchés (et pourquoi)
- Variables et leurs valeurs
- Contenu du data layer

### Astuces de débogage

**Tag qui ne se déclenche pas :**
- Vérifier les conditions du déclencheur
- Vérifier le push dans le data layer
- Vérifier le séquençage des tags

**Mauvaise valeur de variable :**
- Vérifier la structure du data layer
- Vérifier le chemin de la variable (objets imbriqués)
- Vérifier le timing (la donnée peut ne pas encore exister)

**Déclenchements multiples :**
- Vérifier l'unicité du déclencheur
- Chercher des tags en double
- Vérifier les options de déclenchement du tag

---

## Espaces de travail et versioning

### Espaces de travail

Utiliser les espaces de travail pour la collaboration en équipe :
- Espace de travail par défaut pour la production
- Espaces de travail séparés pour les gros changements
- Fusionner quand c'est prêt

### Gestion des versions

**Bonnes pratiques :**
- Nommer chaque version de façon descriptive
- Ajouter des notes expliquant les changements
- Revoir les changements avant publication
- Bien noter la version en production

**Exemple de notes de version :**
```
v15 : Ajout du tracking de conversion d'achat
- Nouveau tag : GA4 - Event - Purchase
- Nouveau déclencheur : Custom Event - purchase
- Nouvelles variables : DL - transaction_id, DL - value
- Testé : Chrome, Safari, Mobile
```

---

## Gestion du consentement

### Intégration du Consent Mode

```javascript
// État par défaut (avant consentement)
gtag('consent', 'default', {
  'analytics_storage': 'denied',
  'ad_storage': 'denied'
});

// Mise à jour au consentement
function grantConsent() {
  gtag('consent', 'update', {
    'analytics_storage': 'granted',
    'ad_storage': 'granted'
  });
}
```

### Vue d'ensemble du consentement GTM

1. Activer la vue d'ensemble du consentement dans l'Admin
2. Configurer le consentement pour chaque tag
3. Les tags respectent automatiquement l'état du consentement

---

## Patterns avancés

### Séquençage de tags

**Configurer des tags pour se déclencher dans l'ordre :**
Tag Configuration > Advanced Settings > Tag Sequencing

**Cas d'usage :**
- Tag de config avant les tags d'événement
- Initialisation du pixel avant le tracking
- Nettoyage après conversion

### Gestion des exceptions

**Exceptions de déclencheur** — Empêcher un tag de se déclencher :
- Exclure certaines pages
- Exclure le trafic interne
- Exclure pendant les tests

### Variables JavaScript personnalisées

```javascript
// Récupérer un paramètre d'URL
function() {
  var params = new URLSearchParams(window.location.search);
  return params.get('campaign') || '(not set)';
}

// Récupérer la valeur d'un cookie
function() {
  var match = document.cookie.match('(^|;) ?user_id=([^;]*)(;|$)');
  return match ? match[2] : null;
}

// Récupérer une donnée depuis la page
function() {
  var el = document.querySelector('.product-price');
  return el ? parseFloat(el.textContent.replace('$', '')) : 0;
}
```
