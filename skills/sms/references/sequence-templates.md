# Templates de séquences SMS

Templates de copy complets avec nombre de caractères, timing et logique de segmentation pour chaque flow SMS majeur.

> Le nombre de caractères indiqué suppose un encodage GSM-7. Les emojis forcent l'UCS-2 (70 car./segment au lieu de 160). Tous les templates utilisent `[Brand]`, `[FirstName]` et `[short.link]` comme tokens de substitution.

---

## Bienvenue / Confirmation d'opt-in

### Envoi 1 — Immédiat (après l'opt-in)

```
De [Brand] : Bienvenue ! Voici votre code -10 % : WELCOME10. J'en profite : [short.link]
Répondez STOP pour vous désinscrire, HELP pour de l'aide. Frais SMS éventuels.
```
~150 car. / 1 segment (tout juste). Footer requis sur le premier envoi.

### Envoi 2 — 24 heures plus tard (optionnel)

```
De [Brand] : N'oubliez pas votre code WELCOME10 — expire dans 48 h. Notre sélection : [short.link]
```
~98 car. / 1 segment.

### Envoi 3 — 7 jours plus tard (optionnel, conditionné à l'absence d'achat)

```
De [Brand] : Dernière chance pour -10 % avec WELCOME10. Expire ce soir à minuit : [short.link]
```
~96 car. / 1 segment.

---

## Panier abandonné (le flow au meilleur ROI pour l'e-commerce)

### Envoi 1 — 30 minutes après l'abandon

```
De [Brand] : [FirstName], vous avez oublié quelque chose ! Votre panier est là : [short.link]
```
~92 car. / 1 segment.

### Envoi 2 — 4 heures après l'abandon (si pas d'achat)

```
De [Brand] : Les articles de votre panier partent vite. Réservés 24 h pour vous : [short.link]
```
~95 car. / 1 segment.

### Envoi 3 — 24 heures après l'abandon (si pas d'achat, réduction autorisée)

```
De [Brand] : Toujours hésitant ? Voici -10 % pour conclure : SAVE10. J'en profite : [short.link]
```
~96 car. / 1 segment.

**Notes** :
- Une réduction dès l'Envoi 1 entraîne les clients à abandonner. À réserver à l'Envoi 2 ou 3.
- Exclure les clients qui ont abandonné <X € de valeur de panier ou les abandonneurs répétés (qui jouent avec la réduction).
- Arrêter la séquence en cas d'achat, d'opt-out ou de 48 heures écoulées.

---

## Abandon de navigation

### Envoi 1 — 1 heure après navigation (produit ou catégorie unique)

```
De [Brand] : Toujours tenté par [product] ? Jetez-y un nouveau coup d'œil : [short.link]
```
~88 car. / 1 segment.

**Notes** :
- Déclencher seulement après un signal de navigation significatif (3+ vues produit ou 2+ min sur la page produit).
- Exclure si un achat a eu lieu sur un autre produit.

---

## Flow post-achat

### Envoi 1 — Immédiatement après l'achat (transactionnel, consentement distinct)

```
De [Brand] : Commande #12345 confirmée ! Suivi d'expédition par SMS ici. Suivre : [short.link]
```
~94 car. / 1 segment.

### Envoi 2 — Jour de l'expédition

```
De [Brand] : Votre commande est en route. Livraison estimée : [date]. Suivre : [short.link]
```
~92 car. / 1 segment.

### Envoi 3 — Jour de la livraison

```
De [Brand] : Votre commande devrait arriver aujourd'hui ! Une question ? Répondez ou [short.link]
```
~96 car. / 1 segment.

### Envoi 4 — 2 jours après la livraison (consentement marketing requis)

```
De [Brand] : Votre [product] vous plaît ? Laissez un avis et obtenez -15 % sur votre prochaine commande : [short.link]
```
~112 car. / 1 segment.

### Envoi 5 — 14 jours après la livraison (cross-sell, consentement marketing)

```
De [Brand] : Parfait avec votre [product] : [related-item]. -10 % sur le duo : [short.link]
```
~90 car. / 1 segment.

---

## Win-back (clients inactifs)

### Envoi 1 — 60-90 jours après le dernier achat

```
De [Brand] : [FirstName], vous nous manquez ! Une sélection qui devrait vous plaire : [short.link]
```
~94 car. / 1 segment.

### Envoi 2 — 14 jours plus tard (si pas d'achat)

```
De [Brand] : Revenez avec -15 % sur votre prochaine commande : COMEBACK15. Expire dans 7 jours : [short.link]
```
~106 car. / 1 segment.

### Envoi 3 — 14 jours après l'Envoi 2 (final, si pas d'achat)

```
De [Brand] : Dernière chance — -20 % se termine ce soir : COMEBACK20. On arrête les SMS si vous préférez : répondez STOP. [short.link]
```
~128 car. / 1 segment.

**Notes** :
- Après l'Envoi 3 sans engagement, supprimer pendant 90 jours minimum.
- Après deux cycles de win-back complets sans engagement, mettre en sommeil (retirer de la liste active).

---

## Envois promotionnels / Campagnes

### Vente flash (envoi unique)

```
De [Brand] : FLASH 24 H : -25 % sur tout avec FLASH25. Se termine à minuit : [short.link]
```
~88 car. / 1 segment.

### Drop / lancement limité

```
De [Brand] : Nouveau drop en ligne : [product-name]. Stock limité, accès anticipé pour les membres : [short.link]
```
~112 car. / 1 segment.

### Fêtes / BFCM (séquence à 2 envois)

Envoi 1 — Jour du lancement :
```
De [Brand] : Le Black Friday est LANCÉ — jusqu'à -50 % sur tout le site. J'en profite : [short.link]
```
~96 car. / 1 segment.

Envoi 2 — Le jour même (ou en soirée, push d'expiration) :
```
De [Brand] : Plus que 6 h pour profiter des offres BFCM. Ne ratez pas ça : [short.link]
```
~84 car. / 1 segment.

---

## Transactionnel / Notifications de compte

### Confirmation de commande

```
[Brand] : Commande #12345 confirmée. Total XX,XX €. Suivi sur [short.link]. Répondez HELP pour de l'aide.
```

### Mise à jour d'expédition

```
[Brand] : Votre commande #12345 est expédiée ! Suivi : [short.link]. Livraison estimée [date].
```

### Confirmation de livraison

```
[Brand] : Commande #12345 livrée. Profitez-en ! Un souci ? Répondez ou [support-link].
```

### Code d'authentification (2FA)

```
[Brand] code de vérification : 123456. Expire dans 10 min. Ne le partagez pas.
```

### Alerte de compte

```
[Brand] : Connexion depuis un nouvel appareil à [location]. Ce n'était pas vous ? Sécurisez : [short.link]
```

---

## Ré-engagement / Réactivation (abonnés devenus froids)

Pour les abonnés SMS qui n'ont interagi avec aucun envoi depuis 60+ jours.

### Envoi 1 — Réactivation douce

```
De [Brand] : Vous nous avez manqué, [FirstName] ! Voici les nouveautés : [short.link]
```
~82 car. / 1 segment.

### Envoi 2 — Confirmer l'intérêt (si pas d'engagement)

```
De [Brand] : Voulez-vous continuer à nous suivre ? Répondez YES pour rester sur la liste, ou STOP pour vous désinscrire.
```
~120 car. / 1 segment.

Sans réponse : supprimer pendant 60 jours, puis retirer de la liste active. Cela protège les métriques de taux d'opt-out et réduit la dépense gaspillée.

---

## Réapprovisionnement (e-commerce de consommables)

Pour les produits à cycles d'usage prévisibles (skincare, compléments, café, alimentation animale).

### Envoi 1 — À la fenêtre de réassort attendue (ex. 28 jours pour un stock de 30 jours)

```
De [Brand] : Bientôt à court de [product] ? Recommandez en un clic : [short.link]
```
~80 car. / 1 segment.

### Envoi 2 — 7 jours plus tard (si pas d'achat)

```
De [Brand] : Ne tombez pas en panne ! -10 % sur votre recommande de [product] : REFILL10 [short.link]
```
~98 car. / 1 segment.

---

## Membres VIP / Fidélité

Fréquence plus élevée, offres exclusives, accès anticipé — des règles de cadence différentes s'appliquent, mais les quiet hours et STOP restent obligatoires.

### Accès anticipé

```
De [Brand] : Les VIP accèdent au nouveau drop 24 h en avance. Le vôtre : [short.link]
```
~84 car. / 1 segment.

### Jalon de fidélité

```
De [Brand] : Vous passez au statut Gold ! Vos avantages : -15 % + livraison offerte. [short.link]
```
~96 car. / 1 segment.

---

## Règles de segmentation à travers tous les flows

- **Supprimer** les clients en séquences actives des envois promotionnels (pas de double-tap)
- **Supprimer** les abonnés ayant fait opt-out de tout (la plateforme gère ça)
- **Frequency cap** : max 4–6 envois marketing/semaine par abonné (plus bas pour les abonnés récents)
- **Quiet hours** : 9h–20h heure locale du destinataire
- **Cool-off** : après un achat déclenché par réduction, supprimer les envois promotionnels pendant 14 jours
