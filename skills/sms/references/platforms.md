# Référence des plateformes SMS

Analyse détaillée des principales plateformes de marketing SMS — fonctionnalités, tarifs, support A2P 10DLC et voies d'intégration.

> Les tarifs sont approximatifs et changent régulièrement. Confirmez toujours sur le site du fournisseur avant de vous engager.

---

## Klaviyo SMS

**Idéal pour** : les marques e-commerce DTC qui utilisent déjà Klaviyo pour l'email.

### Fonctionnalités clés
- Intégration native avec l'email et la segmentation Klaviyo
- Profil d'abonné partagé entre email + SMS
- Enregistrement A2P 10DLC intégré
- Flow builder partagé avec les flows email
- SMS conversationnel (bidirectionnel) supporté

### Tarifs
- Inclus dans les plans Klaviyo, facturé par crédit SMS
- US : ~0,0075–0,015 $ par SMS ; MMS ~0,04 $
- Tier gratuit : 150 crédits SMS/mois sur les tiers email inférieurs

### Voies d'intégration
- Intégration directe Shopify, WooCommerce, BigCommerce, Magento
- API pour plateformes custom
- Serveur MCP disponible

### Conformité
- Enregistrement A2P 10DLC géré dans la plateforme
- Provisionnement de numéro vert et de short code disponible (le short code ajoute 1 000 $+/mois)
- Quiet hours appliquées par fuseau horaire du destinataire (configurable)

### Points de vigilance
- La facturation combinée email + SMS peut grimper vite sur les grandes listes
- Les coûts de short code sont un vrai surcoût ; rentables seulement pour 100K+ abonnés SMS actifs

---

## Postscript

**Idéal pour** : les marques DTC nativement Shopify voulant un outillage spécifique SMS et un support d'onboarding.

### Fonctionnalités clés
- Intégration Shopify profonde (la plus profonde de toutes les plateformes SMS)
- Automations puissantes de panier abandonné et d'abandon de navigation
- AI Reply (réponse auto entraînée sur la voix de la marque)
- SMS conversationnel / agent en direct
- Audiences tirées des données client Shopify

### Tarifs
- Plans à paliers : Starter (gratuit, 1K msg/mois), Growth (100 $+/mois), Professional, Enterprise
- Le pay-per-send s'ajoute par-dessus : ~0,015 $ par SMS, ~0,04 $ par MMS

### Voies d'intégration
- Shopify-first ; support limité hors Shopify
- API + webhooks disponibles

### Conformité
- A2P 10DLC géré dans la plateforme
- Outils de conformité d'opt-in solides (popup builder, opt-in par mot-clé)
- Quiet hours appliquées

### Points de vigilance
- Forte hausse de coût au-delà du tier Starter
- Moins utile si vous n'êtes pas sur Shopify

---

## Attentive

**Idéal pour** : les marques DTC mid-market et entreprise voulant un SMS full-service.

### Fonctionnalités clés
- Full-service : CSM dédié, support copy, stratégie
- SMS conversationnel à l'échelle
- Vente par SMS en mode concierge
- Analytics et attribution solides
- Résolution d'identité (matcher les visiteurs anonymes du site à des numéros)

### Tarifs
- Contrats custom ; typiquement 1K–10K $+/mois + frais par envoi
- Contrats annuels standard
- Les tarifs n'ont rarement de sens pour <50K abonnés SMS

### Voies d'intégration
- Shopify, BigCommerce, Salesforce Commerce Cloud, custom
- API robuste

### Conformité
- A2P 10DLC entièrement géré
- Outillage de conformité et support d'audit best-in-class
- Provisionnement de short code inclus sur la plupart des plans

### Points de vigilance
- Les conditions de contrat peuvent vous engager 12+ mois
- Surdimensionné pour les marques en early-stage

---

## Twilio

**Idéal pour** : builds custom, SMS transactionnel, SaaS B2B intégrant du SMS dans des produits, développeurs.

### Fonctionnalités clés
- API SMS brute
- Tarif pay-per-send, pas de frais de plateforme
- Couverture mondiale massive (200+ pays)
- Programmable Voice, WhatsApp Business, RCS disponibles à côté
- Studio (flow builder visuel) pour l'automation sans code

### Tarifs
- SMS US 10DLC : 0,0079 $ par message
- SMS US numéro vert : 0,0079 $ par message
- SMS US short code : 0,0079 $ par message + 1 000 $/mois de location
- MMS : ~0,02 $
- Surcoûts opérateurs ajoutés par-dessus (~0,005 $ par 10DLC US)
- Enregistrement A2P 10DLC : ~15 $ marque + 10 $/mois par campagne

### Voies d'intégration
- API-first (REST + SDK en Node, Python, Ruby, Go, etc.)
- Pas d'intégrations e-commerce natives — vous les construisez

### Conformité
- Enregistrement A2P 10DLC dans la plateforme mais c'est vous qui faites le travail
- TwilioSendGrid (produit séparé) gère la conformité côté email
- Les quiet hours et la gestion STOP/HELP doivent être implémentées par vous

### Points de vigilance
- Vous êtes responsable de la conformité — pas d'accompagnement
- Pas de segmentation native, de dashboards de délivrabilité, ni d'UI marketing
- À coupler de préférence avec Customer.io, Segment ou une couche d'orchestration custom

---

## Brevo (anciennement Sendinblue)

**Idéal pour** : les marques basées en UE, combo email + SMS, adapté PME.

### Fonctionnalités clés
- Email + SMS + WhatsApp combinés sur une seule plateforme
- Siège en UE, RGPD-natif
- Tier gratuit généreux pour l'email ; SMS en pay-per-send
- Flows de marketing automation
- CRM inclus

### Tarifs
- Tier gratuit : 300 emails/jour ; SMS en pay-per-send
- SMS US : ~0,015 $ par message
- SMS UE : varie selon le pays, ~0,04–0,07 €

### Voies d'intégration
- Intégrations directes : Shopify, WooCommerce, WordPress, Magento
- API + Zapier
- Serveur MCP disponible

### Conformité
- RGPD + ePrivacy intégrés
- A2P 10DLC pour les US (moins abouti que les plateformes US dédiées)

### Points de vigilance
- Les fonctionnalités SMS US sont en retard sur Klaviyo/Postscript
- À privilégier si vous êtes UE-first ou déjà sur Brevo pour l'email

---

## SimpleTexting

**Idéal pour** : PME, entreprises de services, blasts de campagne simples, faible volume.

### Fonctionnalités clés
- UI facile à utiliser
- Opt-in par mot-clé pour la construction de liste grassroots
- Landing pages intégrées pour l'opt-in
- Automation simple

### Tarifs
- Plans à partir de ~30 $/mois pour 500 crédits, scalant ensuite
- SMS US uniquement

### Voies d'intégration
- Zapier, Make, natif sur quelques apps
- API disponible mais basique

### Conformité
- A2P 10DLC géré
- Outillage TCPA

### Points de vigilance
- Profondeur d'automation limitée vs Klaviyo/Postscript
- Idéal pour les cas d'usage peu complexes, faible volume (salles de sport, salons, immobilier)

---

## Plivo

**Idéal pour** : les builds SMS custom où le coût par envoi compte ; une API style Twilio à un prix plus bas.

### Fonctionnalités clés
- Concurrent direct de Twilio avec une surface similaire
- Powerpack pour l'envoi en masse avec sticky sender sur des pools de numéros
- A2P 10DLC géré dans la plateforme
- WhatsApp, voix disponibles à côté du SMS
- SDK pour les langages majeurs

### Tarifs
- SMS US 10DLC : ~0,0055 $/msg (typiquement 20–30 % sous Twilio)
- SMS US short code : similaire + location mensuelle
- MMS : ~0,02 $
- Location de numéro : ~0,80 $/mois local, ~1 $/mois numéro vert

### Voies d'intégration
- API-first (REST + SDK)
- Pas d'intégrations e-commerce natives — vous les construisez

### Conformité
- A2P 10DLC géré dans la plateforme
- La plomberie de conformité (STOP/HELP, quiet hours) est de votre responsabilité — même modèle que Twilio

### Points de vigilance
- Écosystème plus petit que Twilio (moins de produits annexes, d'intégrations, de ressources communautaires)
- Outillage WhatsApp moins mature

---

## AudienceTap

**Idéal pour** : les marques DTC voulant un outillage créatif AI-forward ou un opt-in par QR sur packaging comme canal d'acquisition principal.

> Plateforme plus récente — vérifiez les capacités, tarifs et surface d'API actuels avant de vous engager.

### Fonctionnalités clés
- SMS + email sur une seule plateforme (modèle combiné similaire à Klaviyo)
- Génération créative par IA (copy SMS, objets, variantes d'images)
- Opt-in par QR code sur packaging : inserts dans les commandes expédiées qui boostent la croissance de la liste SMS
- Intégrations Shopify, BigCommerce, commerce headless
- A2P 10DLC géré dans la plateforme
- Résolution d'identité et segmentation

### Tarifs
- À paliers selon le nombre d'abonnés + le volume d'envoi
- Tarif par envoi comparable aux autres plateformes SMS DTC

### Voies d'intégration
- Accès API sur les tiers Growth+
- Intégrations e-commerce directes
- Webhooks pour les événements

### Conformité
- A2P 10DLC géré dans la plateforme
- Outillage TCPA — vérifiez la profondeur à l'échelle entreprise avant de vous engager pour de grandes listes

### Points de vigilance
- Nouvel entrant — moins de clients de référence, moins éprouvé à fort volume que les incumbents
- Certaines fonctionnalités déployées récemment — confirmez ce qui est GA vs beta avant de vous y fier

---

## Customer.io

**Idéal pour** : SaaS B2B, automation basée sur le comportement, orchestration multi-canal (email + SMS + push).

### Fonctionnalités clés
- Déclencher des SMS sur des événements produit (inscription, jalon, risque de churn)
- Segmentation d'audience puissante
- Workflow builder
- Sync de données en temps réel via API/webhooks

### Tarifs
- Plans à partir de ~150 $/mois, scalant avec le nombre de profils
- SMS via intégration Twilio ou natif (variable)

### Voies d'intégration
- API-first
- Intégrations directes avec Segment, Heap, Mixpanel, etc.

### Conformité
- A2P 10DLC via Twilio si vous utilisez l'intégration native
- Gestion granulaire des abonnements/consentements

### Points de vigilance
- Moins taillé e-commerce que Klaviyo/Postscript
- Idéal pour le SaaS product-led ou les apps avec un event tracking poussé

---

## Tableau de sélection rapide

| Stack / Objectif | Recommandé | Pourquoi |
|--------------|------------|-----|
| E-commerce Shopify, déjà sur Klaviyo | **Klaviyo SMS** | Une plateforme, un profil d'abonné |
| E-commerce Shopify, focus SMS-first | **Postscript** | Shopify le plus profond + fonctionnalités spécifiques SMS |
| E-commerce mid-market, envie de support concierge | **Attentive** | Équipe full-service + outillage |
| Plateforme custom, SaaS B2B, transactionnel | **Twilio** | API-first, contrôle total |
| Build custom, sensible au coût | **Plivo** | ~20–30 % moins cher que Twilio par envoi |
| DTC voulant de la créa IA ou un opt-in QR sur packaging | **AudienceTap** | AI-forward ; l'opt-in par insert est unique |
| PME basée en UE | **Brevo** | RGPD-natif, tarifs adaptés à l'UE |
| PME de services locaux, campagnes simples | **SimpleTexting** | UI facile, faible surcoût |
| SaaS product-led avec event tracking | **Customer.io** | Déclencheurs basés sur le comportement |

---

## A2P 10DLC : ce que votre plateforme doit gérer

Quoi que vous choisissiez, confirmez que votre plateforme gère :

- [ ] Enregistrement de la marque et de la campagne auprès du TCR
- [ ] Texte des exemples de messages aligné sur ce que vous envoyez réellement
- [ ] Documentation du flow d'opt-in soumise aux opérateurs
- [ ] Visibilité du trust score (et un chemin pour l'améliorer)
- [ ] Débit adapté à la taille de votre liste et à la fréquence d'envoi
- [ ] Gestion des mots-clés STOP/HELP
- [ ] Quiet hours par fuseau horaire du destinataire
- [ ] Gestion de la liste de suppression
- [ ] Conservation des preuves de consentement avec horodatage

Toutes les grandes plateformes ci-dessus gèrent ces points. Twilio fait le travail de plus bas niveau et reporte plus de responsabilité sur vous.
