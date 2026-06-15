# Configuration du tracking de conversion

Comment configurer les pixels de tracking de conversion sur les différentes régies publicitaires. Ce guide couvre l'installation, la configuration des événements et la validation — tout ce dont un marketeur a besoin pour s'assurer que le budget pub est correctement attribué.

---

## Pourquoi c'est important

Sans tracking de conversion :
- Les régies ne peuvent pas optimiser sur vos vrais objectifs
- Vous naviguez à l'aveugle sur le ROAS et le CPA
- Les audiences de retargeting ne peuvent pas être construites
- Vous gaspillez du budget sur des impressions qui ne convertissent pas

Mettez le tracking au point avant de dépenser le moindre euro en pub.

---

## Aperçu des pixels par plateforme

| Plateforme | Nom du pixel/tag | API d'événements | Événements clés |
|----------|---------------|:----------:|------------|
| **Google Ads** | Google tag (gtag.js) | Enhanced Conversions | purchase, sign_up, generate_lead |
| **Meta** | Meta Pixel + CAPI | Conversions API | Purchase, Lead, ViewContent, AddToCart |
| **LinkedIn** | Insight Tag | Conversions API | conversion (URL ou par événement) |
| **TikTok** | TikTok Pixel | Events API | Purchase, ViewContent, AddToCart, CompleteRegistration |
| **Twitter/X** | Twitter Pixel | - | Purchase, SignUp, Download |

---

## Google Ads

### Installer le Google tag

Ajouter sur chaque page, dans `<head>` :

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=AW-XXXXXXXXX"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'AW-XXXXXXXXX');
</script>
```

Remplacer `AW-XXXXXXXXX` par votre Conversion ID depuis Google Ads > Outils > Conversions.

### Configurer les actions de conversion

Dans Google Ads > Objectifs > Conversions > Nouvelle action de conversion :

| Conversion | Catégorie | Valeur | Comptage |
|-----------|----------|-------|-------|
| Achat | Purchase | Dynamique (valeur de commande) | Chaque |
| Inscription / Lead | Sign-up | Fixe (valeur estimée de X €) | Un |
| Demande de démo | Lead | Fixe (valeur estimée de X €) | Un |
| Démarrage de free trial | Sign-up | Fixe (valeur estimée de X €) | Un |

### Déclencher les événements de conversion

```javascript
// Purchase
gtag('event', 'conversion', {
  'send_to': 'AW-XXXXXXXXX/CONVERSION_LABEL',
  'value': 99.00,
  'currency': 'USD',
  'transaction_id': 'ORDER-123'
});

// Lead / Sign up
gtag('event', 'conversion', {
  'send_to': 'AW-XXXXXXXXX/CONVERSION_LABEL',
  'value': 50.00,
  'currency': 'USD'
});
```

### Enhanced Conversions

Envoie des données first-party hashées (email, téléphone) pour améliorer l'attribution après les restrictions sur les cookies. Activer dans Google Ads > Objectifs > Paramètres > Enhanced conversions.

```javascript
gtag('set', 'user_data', {
  'email': 'user@example.com',      // auto-hashed by gtag
  'phone_number': '+11234567890'
});
```

### Alternative Google Tag Manager

Si vous utilisez GTM au lieu du gtag.js inline :
1. Installer le conteneur GTM sur toutes les pages
2. Créer les tags de conversion Google Ads dans GTM
3. Définir des déclencheurs pour les événements de conversion (soumissions de formulaire, achats)
4. Utiliser le Data Layer pour passer des valeurs dynamiques (montant de commande, transaction ID)
5. Tester avec le mode Preview de GTM avant de publier

---

## Meta (Facebook/Instagram)

### Installer le Meta Pixel

Ajouter sur chaque page, dans `<head>` :

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

Remplacer `YOUR_PIXEL_ID` depuis Meta Events Manager.

### Événements standard

```javascript
// View a product or key page
fbq('track', 'ViewContent', {
  content_name: 'Pro Plan',
  content_category: 'Pricing',
  value: 29.00,
  currency: 'USD'
});

// Lead capture (form submit, demo request)
fbq('track', 'Lead', {
  content_name: 'Demo Request',
  value: 50.00,
  currency: 'USD'
});

// Purchase
fbq('track', 'Purchase', {
  value: 99.00,
  currency: 'USD',
  content_type: 'product',
  contents: [{ id: 'pro-plan', quantity: 1 }]
});

// Add to cart (e-commerce)
fbq('track', 'AddToCart', {
  content_ids: ['SKU-123'],
  content_type: 'product',
  value: 49.00,
  currency: 'USD'
});
```

### Conversions API (CAPI)

Tracking côté serveur qui fonctionne en parallèle du pixel. Requis pour un tracking précis après iOS 14+ et les restrictions sur les cookies.

Mise en place via :
- **Intégration directe** — envoyer les événements de votre serveur vers l'API de Meta
- **Intégrations partenaires** — Shopify, WooCommerce, Segment, etc. ont un support CAPI intégré
- **Conversions API Gateway** — la solution managée de Meta via AWS

Clé : envoyer les mêmes événements à la fois depuis le pixel (navigateur) ET le CAPI (serveur), avec un `event_id` partagé pour la déduplication.

### Aggregated Event Measurement

Requis pour le tracking iOS 14+. Dans Events Manager > Aggregated Event Measurement :
1. Vérifier votre domaine
2. Configurer et prioriser vos 8 principaux événements par ordre d'importance business
3. Purchase devrait généralement être n°1, Lead n°2

---

## LinkedIn

### Installer l'Insight Tag

Ajouter sur chaque page, avant `</body>` :

```html
<script type="text/javascript">
  _linkedin_partner_id = "YOUR_PARTNER_ID";
  window._linkedin_data_partner_ids = window._linkedin_data_partner_ids || [];
  window._linkedin_data_partner_ids.push(_linkedin_partner_id);
  (function(l) {
    if (!l){window.lintrk = function(a,b){window.lintrk.q.push([a,b])};
    window.lintrk.q=[]}
    var s = document.getElementsByTagName("script")[0];
    var b = document.createElement("script");
    b.type = "text/javascript";b.async = true;
    b.src = "https://snap.licdn.com/li.lms-analytics/insight.min.js";
    s.parentNode.insertBefore(b, s);})(window.lintrk);
</script>
```

### Tracking de conversion

LinkedIn prend en charge deux méthodes :

**Basé URL** : Se déclenche quand quelqu'un visite une URL spécifique (ex. `/thank-you`).
Configurer dans Campaign Manager > Analyze > Conversion Tracking > Create Conversion.

**Basé événement** : Déclencher manuellement sur des actions spécifiques :

```javascript
window.lintrk('track', { conversion_id: YOUR_CONVERSION_ID });
```

### LinkedIn CAPI

Pour le tracking côté serveur, LinkedIn propose une Conversions API. Mise en place via des intégrations partenaires (Segment, Tealium) ou des appels API directs. Déduplique automatiquement avec l'Insight Tag quand c'est configuré correctement.

---

## TikTok

### Installer le TikTok Pixel

Ajouter sur chaque page, dans `<head>` :

```html
<script>
  !function (w, d, t) {
    w.TiktokAnalyticsObject=t;var ttq=w[t]=w[t]||[];
    ttq.methods=["page","track","identify","instances","debug","on","off",
    "once","ready","alias","group","enableCookie","disableCookie","holdConsent",
    "revokeConsent","grantConsent"],ttq.setAndDefer=function(t,e)
    {t[e]=function(){t.push([e].concat(Array.prototype.slice.call(arguments,0)))}};
    for(var i=0;i<ttq.methods.length;i++)ttq.setAndDefer(ttq,ttq.methods[i]);
    ttq.instance=function(t){for(var e=ttq._i[t]||[],n=0;
    n<ttq.methods.length;n++)ttq.setAndDefer(e,ttq.methods[n]);return e};
    ttq.load=function(e,n){var r="https://analytics.tiktok.com/i18n/pixel/events.js",
    o=n&&n.partner;ttq._i=ttq._i||{},ttq._i[e]=[],ttq._i[e]._u=r,
    ttq._t=ttq._t||{},ttq._t[e]=+new Date,ttq._o=ttq._o||{},
    ttq._o[e]=n||{};var s=document.createElement("script");
    s.type="text/javascript",s.async=!0,s.src=r+"?sdkid="+e+"&lib="+t;
    var a=document.getElementsByTagName("script")[0];
    a.parentNode.insertBefore(s,a)};
    ttq.load('YOUR_PIXEL_ID');
    ttq.page();
  }(window, document, 'ttq');
</script>
```

### Événements standard

```javascript
// View content
ttq.track('ViewContent', {
  content_id: 'pro-plan',
  content_type: 'product',
  content_name: 'Pro Plan',
  value: 29.00,
  currency: 'USD'
});

// Complete registration / sign up
ttq.track('CompleteRegistration', {
  content_name: 'Free Trial'
});

// Purchase
ttq.track('Purchase', {
  content_id: 'pro-plan',
  content_type: 'product',
  value: 99.00,
  currency: 'USD',
  quantity: 1
});

// Add to cart
ttq.track('AddToCart', {
  content_id: 'SKU-123',
  content_type: 'product',
  value: 49.00,
  currency: 'USD'
});
```

### Events API (côté serveur)

L'Events API de TikTok fonctionne comme le CAPI de Meta — envoyer les mêmes événements depuis votre serveur pour une meilleure attribution. Utiliser `event_id` pour la déduplication avec les événements du pixel navigateur.

### Advanced Matching

Passer des données utilisateur hashées pour une meilleure attribution :

```javascript
ttq.identify({
  email: 'user@example.com',       // auto-hashed
  phone_number: '+11234567890'
});
```

---

## Checklist de validation

Après l'installation de n'importe quel pixel, vérifier avant la mise en ligne :

### Vérifications côté navigateur

- [ ] Le pixel se déclenche sur chaque page (vérifier via une extension de navigateur)
- [ ] Les événements de conversion se déclenchent au bon moment (après l'action confirmée, pas au clic du bouton)
- [ ] Les paramètres d'événement contiennent les bonnes valeurs (devise, montant, content IDs)
- [ ] Aucun événement en double ne se déclenche sur la même action
- [ ] Les événements se déclenchent sur desktop et mobile

### Vérifications côté plateforme

- [ ] Les événements apparaissent dans l'event manager/les diagnostics de la plateforme
- [ ] Les conversions de test affichent les bonnes valeurs
- [ ] La qualité de correspondance des événements est acceptable (Meta : score > 6)
- [ ] Les événements côté serveur dédupliquent avec les événements navigateur (pas de double comptage)

### Outils de débogage

| Plateforme | Outil |
|----------|------|
| Google | Google Tag Assistant, onglet Network des Chrome DevTools |
| Meta | Meta Pixel Helper (extension Chrome), Test Events de l'Events Manager |
| LinkedIn | Insight Tag Validator dans Campaign Manager |
| TikTok | TikTok Pixel Helper (extension Chrome), Events Manager |
| Tous | Mode Preview de GTM (si vous utilisez Google Tag Manager) |

---

## Erreurs courantes

- **Déclencher les événements d'achat au clic du bouton au lieu du paiement confirmé** — toujours déclencher sur la page de succès/remerciement ou après confirmation serveur
- **Déduplication manquante entre les événements pixel et serveur** — sans `event_id` partagé, vous compterez les conversions en double
- **Ne pas tester sur mobile** — beaucoup de pixels cassent sur les navigateurs mobiles ou les webviews in-app
- **Valeurs de test codées en dur** — retirer les montants de transaction de test avant la mise en ligne
- **Oublier d'exclure le trafic interne** — les visites de votre équipe gonflent les données de conversion
- **Installer des pixels sans gestion du consentement** — le RGPD/CCPA exige le consentement de l'utilisateur avant de déclencher des pixels de tracking dans les régions applicables
- **Pixel installé mais aucune action de conversion créée** — le pixel collecte des données, mais la régie n'optimisera pas sans actions de conversion définies

---

## Quand utiliser le tracking côté serveur

Le tracking navigateur uniquement est de plus en plus peu fiable à cause de :
- L'App Tracking Transparency d'iOS 14+
- La dépréciation des cookies tiers
- Les ad blockers (30 %+ des audiences tech)

**Utiliser le côté serveur (CAPI/Events API) quand :**
- Vous lancez des pubs Meta ou TikTok (fortement recommandé)
- Votre audience est tech-savvy (usage plus élevé d'ad blockers)
- Vous avez besoin d'une attribution précise des achats/revenus
- Vous dépensez plus de 5 000 €/mois sur une plateforme

**Le côté serveur est optionnel quand :**
- Vous lancez Google Ads uniquement (Enhanced Conversions couvre la plupart des manques)
- Faible budget pub / phase de test
- B2B avec LinkedIn uniquement (l'Insight Tag reste fiable)
