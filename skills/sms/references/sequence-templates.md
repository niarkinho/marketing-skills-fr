# Templates de séquences SMS

Templates de copy complets avec nombre de caractères, timing et logique de segmentation pour chaque flow SMS majeur.

> Le nombre de caractères indiqué suppose un encodage GSM-7. Les emojis forcent l'UCS-2 (70 car./segment au lieu de 160). Tous les templates utilisent `[Brand]`, `[FirstName]` et `[short.link]` comme tokens de substitution.

---

## Bienvenue / Confirmation d'opt-in

### Envoi 1 — Immédiat (après l'opt-in)

```
From [Brand]: Welcome! Here's your 10% off code: WELCOME10. Shop now: [short.link]
Reply STOP to opt out, HELP for help. Msg & data rates may apply.
```
~155 car. / 1 segment (tout juste). Footer requis sur le premier envoi.

### Envoi 2 — 24 heures plus tard (optionnel)

```
From [Brand]: Don't forget your code WELCOME10 — expires in 48hrs. Top picks: [short.link]
```
~108 car. / 1 segment.

### Envoi 3 — 7 jours plus tard (optionnel, conditionné à l'absence d'achat)

```
From [Brand]: Last chance for 10% off with WELCOME10. Expires tonight at midnight: [short.link]
```
~107 car. / 1 segment.

---

## Panier abandonné (le flow au meilleur ROI pour l'e-commerce)

### Envoi 1 — 30 minutes après l'abandon

```
From [Brand]: Hey [FirstName], you left something behind! Your cart's here: [short.link]
```
~95 car. / 1 segment.

### Envoi 2 — 4 heures après l'abandon (si pas d'achat)

```
From [Brand]: Items in your cart are selling fast. Reserved for you for 24hrs: [short.link]
```
~98 car. / 1 segment.

### Envoi 3 — 24 heures après l'abandon (si pas d'achat, réduction autorisée)

```
From [Brand]: Still thinking? Here's 10% off to seal the deal: SAVE10. Shop: [short.link]
```
~99 car. / 1 segment.

**Notes** :
- Une réduction dès l'Envoi 1 entraîne les clients à abandonner. À réserver à l'Envoi 2 ou 3.
- Exclure les clients qui ont abandonné <X € de valeur de panier ou les abandonneurs répétés (qui jouent avec la réduction).
- Arrêter la séquence en cas d'achat, d'opt-out ou de 48 heures écoulées.

---

## Abandon de navigation

### Envoi 1 — 1 heure après navigation (produit ou catégorie unique)

```
From [Brand]: Still thinking about [product]? Take another look: [short.link]
```
~84 car. / 1 segment.

**Notes** :
- Déclencher seulement après un signal de navigation significatif (3+ vues produit ou 2+ min sur la page produit).
- Exclure si un achat a eu lieu sur un autre produit.

---

## Flow post-achat

### Envoi 1 — Immédiatement après l'achat (transactionnel, consentement distinct)

```
From [Brand]: Order #12345 confirmed! We'll text shipping updates here. Track: [short.link]
```
~95 car. / 1 segment.

### Envoi 2 — Jour de l'expédition

```
From [Brand]: Your order's on the way. Estimated delivery: [date]. Track: [short.link]
```
~92 car. / 1 segment.

### Envoi 3 — Jour de la livraison

```
From [Brand]: Your order should arrive today! Questions? Reply or visit [short.link]
```
~88 car. / 1 segment.

### Envoi 4 — 2 jours après la livraison (consentement marketing requis)

```
From [Brand]: How are you liking your [product]? Share a review for 15% off next order: [short.link]
```
~108 car. / 1 segment.

### Envoi 5 — 14 jours après la livraison (cross-sell, consentement marketing)

```
From [Brand]: Goes great with your [product]: [related-item]. 10% off bundle: [short.link]
```
~99 car. / 1 segment.

---

## Win-back (clients inactifs)

### Envoi 1 — 60-90 jours après le dernier achat

```
From [Brand]: [FirstName], we miss you! Picks we think you'll love: [short.link]
```
~84 car. / 1 segment.

### Envoi 2 — 14 jours plus tard (si pas d'achat)

```
From [Brand]: Come back for 15% off your next order: COMEBACK15. Expires in 7 days: [short.link]
```
~106 car. / 1 segment.

### Envoi 3 — 14 jours après l'Envoi 2 (final, si pas d'achat)

```
From [Brand]: Last chance — 20% off ends tonight: COMEBACK20. We'll stop texting if you'd rather: reply STOP. [short.link]
```
~130 car. / 1 segment.

**Notes** :
- Après l'Envoi 3 sans engagement, supprimer pendant 90 jours minimum.
- Après deux cycles de win-back complets sans engagement, mettre en sommeil (retirer de la liste active).

---

## Envois promotionnels / Campagnes

### Vente flash (envoi unique)

```
From [Brand]: 24-HOUR FLASH: 25% off everything with FLASH25. Ends midnight: [short.link]
```
~94 car. / 1 segment.

### Drop / lancement limité

```
From [Brand]: New drop just landed: [product-name]. Limited stock, members get early access: [short.link]
```
~115 car. / 1 segment.

### Fêtes / BFCM (séquence à 2 envois)

Envoi 1 — Jour du lancement :
```
From [Brand]: Black Friday is LIVE — up to 50% off sitewide. Shop now: [short.link]
```
~92 car. / 1 segment.

Envoi 2 — Le jour même (ou en soirée, push d'expiration) :
```
From [Brand]: Last 6 hours of BFCM savings. Don't miss out: [short.link]
```
~73 car. / 1 segment.

---

## Transactionnel / Notifications de compte

### Confirmation de commande

```
[Brand]: Order #12345 confirmed. Total $XX.XX. Track at [short.link]. Reply HELP for help.
```

### Mise à jour d'expédition

```
[Brand]: Your order #12345 shipped! Track: [short.link]. ETA [date].
```

### Confirmation de livraison

```
[Brand]: Order #12345 delivered. Enjoy! Issues? Reply or [support-link].
```

### Code d'authentification (2FA)

```
[Brand] verification code: 123456. Expires in 10 min. Do not share.
```

### Alerte de compte

```
[Brand]: Sign-in from new device in [location]. Wasn't you? Secure: [short.link]
```

---

## Ré-engagement / Réactivation (abonnés devenus froids)

Pour les abonnés SMS qui n'ont interagi avec aucun envoi depuis 60+ jours.

### Envoi 1 — Réactivation douce

```
From [Brand]: We've missed you, [FirstName]! Here's what's new: [short.link]
```
~80 car. / 1 segment.

### Envoi 2 — Confirmer l'intérêt (si pas d'engagement)

```
From [Brand]: Want to keep hearing from us? Reply YES to stay on the list, or STOP to opt out.
```
~98 car. / 1 segment.

Sans réponse : supprimer pendant 60 jours, puis retirer de la liste active. Cela protège les métriques de taux d'opt-out et réduit la dépense gaspillée.

---

## Réapprovisionnement (e-commerce de consommables)

Pour les produits à cycles d'usage prévisibles (skincare, compléments, café, alimentation animale).

### Envoi 1 — À la fenêtre de réassort attendue (ex. 28 jours pour un stock de 30 jours)

```
From [Brand]: Running low on [product]? Reorder in one tap: [short.link]
```
~73 car. / 1 segment.

### Envoi 2 — 7 jours plus tard (si pas d'achat)

```
From [Brand]: Don't run out! 10% off your reorder of [product]: REFILL10 [short.link]
```
~92 car. / 1 segment.

---

## Membres VIP / Fidélité

Fréquence plus élevée, offres exclusives, accès anticipé — des règles de cadence différentes s'appliquent, mais les quiet hours et STOP restent obligatoires.

### Accès anticipé

```
From [Brand]: VIPs get the new drop 24hrs early. Yours now: [short.link]
```
~72 car. / 1 segment.

### Jalon de fidélité

```
From [Brand]: You've reached Gold status! Your perks: 15% off + free shipping. [short.link]
```
~95 car. / 1 segment.

---

## Règles de segmentation à travers tous les flows

- **Supprimer** les clients en séquences actives des envois promotionnels (pas de double-tap)
- **Supprimer** les abonnés ayant fait opt-out de tout (la plateforme gère ça)
- **Frequency cap** : max 4–6 envois marketing/semaine par abonné (plus bas pour les abonnés récents)
- **Quiet hours** : 9h–20h heure locale du destinataire
- **Cool-off** : après un achat déclenché par réduction, supprimer les envois promotionnels pendant 14 jours
