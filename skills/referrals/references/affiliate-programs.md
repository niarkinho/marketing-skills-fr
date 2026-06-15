# Conception d'un programme d'affiliation

Guide détaillé pour construire et gérer des programmes d'affiliation.

## Sommaire
- Structures de commission
- Durée du cookie
- Recrutement d'affiliés
- Enablement des affiliés
- Outils & plateformes (outils de programme de referral, outils de programme d'affiliation, choisir un outil)
- Prévention de la fraude (fraudes de referral courantes, mesures de prévention)

## Structures de commission

**Pourcentage de la vente :**
- Standard : 10-30 % de la première vente ou de la première année
- Fonctionne pour : e-commerce, SaaS au pricing clair
- Exemple : « Gagnez 25 % de chaque vente que vous apportez »

**Montant forfaitaire par action :**
- Standard : 5-500 € selon la valeur
- Fonctionne pour : lead gen, free trials, freemium
- Exemple : « 50 € pour chaque démo qualifiée »

**Commission récurrente :**
- Standard : 10-25 % du revenu récurrent
- Fonctionne pour : produits sur abonnement
- Exemple : « 20 % de l'abonnement pendant 12 mois »

**Commission par paliers :**
- Fonctionne pour : motiver les top performers
- Exemple : « 20 % pour 1-10 ventes, 25 % pour 11-25, 30 % pour 26+ »

---

## Durée du cookie

Combien de temps après le clic l'affilié est-il crédité ?

| Durée | Cas d'usage |
|----------|----------|
| 24 heures | Achats à fort volume, faible considération |
| 7-14 jours | E-commerce standard |
| 30 jours | SaaS/B2B standard |
| 60-90 jours | Cycles de vente longs, entreprise |
| À vie | Relations d'affiliation premium |

---

## Recrutement d'affiliés

### Où trouver des affiliés :
- Clients existants qui créent du contenu
- Blogueurs et reviewers du secteur
- YouTubeurs de votre niche
- Auteurs de newsletters
- Entreprises d'outils complémentaires
- Consultants et agences

### Template d'outreach :
```
Objet : Opportunité de partenariat — [Votre produit]

Bonjour [Prénom],

Je suis votre contenu sur [sujet] — en particulier [contenu précis] — et je pense qu'il pourrait y avoir une belle complémentarité pour un partenariat.

[Votre produit] aide [audience] à [atteindre un résultat], et je pense que votre audience le trouverait utile.

Nous proposons [structure de commission] à nos partenaires, plus [avantages supplémentaires : accès anticipé, co-marketing, etc.].

Seriez-vous ouvert à en savoir plus ?

[Votre nom]
```

---

## Enablement des affiliés

Fournir aux affiliés :
- [ ] Liens/codes de tracking uniques
- [ ] Présentation du produit et bénéfices clés
- [ ] Description de l'audience cible
- [ ] Comparaison avec les concurrents
- [ ] Assets créatifs (logos, bannières, images)
- [ ] Exemples de copy et arguments clés
- [ ] Études de cas et témoignages
- [ ] Accès démo ou compte gratuit
- [ ] FAQ et traitement des objections
- [ ] Conditions et calendrier de paiement

---

## Outils & plateformes

### Outils de programme de referral

**Plateformes complètes :**
- ReferralCandy — orientée e-commerce
- Ambassador — programmes de referral entreprise
- Friendbuy — e-commerce et abonnement
- GrowSurf — entreprises SaaS et tech
- Mention Me — marketing de referral piloté par l'IA
- Viral Loops — campagnes basées sur des templates

**Options intégrées :**
- Stripe (suivi de referral basique)
- HubSpot (intégré au CRM)
- Segment (tracking et analytics)

### Outils de programme d'affiliation

**Réseaux d'affiliation :**
- ShareASale — large réseau de marchands
- Impact — partenariats entreprise
- PartnerStack — orienté SaaS
- Tapfiliate — suivi d'affiliation SaaS simple
- FirstPromoter — gestion d'affiliation SaaS

**Partner Relationship Management (PRM) :**
- Introw — PRM complet avec deal registration, commissions, paliers, QBR et suivi de l'engagement des partenaires ([guide d'intégration](../../../tools/integrations/introw.md))

**Auto-hébergé :**
- Rewardful — affiliés intégrés à Stripe
- Refersion — affiliés e-commerce

### Choisir un outil

À considérer :
- Intégration avec votre système de paiement
- Capacités de détection de fraude
- Gestion des paiements
- Reporting et analytics
- Options de personnalisation
- Prix vs. échelle du programme

---

## Prévention de la fraude

### Fraudes de referral courantes
- Auto-referrals (création de faux comptes)
- Cercles de referral (groupes qui se parrainent entre eux)
- Sites de coupons publiant des codes de referral
- Fausses adresses email
- Spoofing VPN/appareil

### Mesures de prévention

**Technique :**
- Vérification email obligatoire
- Device fingerprinting
- Surveillance des adresses IP
- Paiement de la récompense différé (après activation)
- Seuil minimal d'activité

**Politique :**
- Conditions d'utilisation claires
- Maximum de referrals par période
- Récupération de la récompense en cas de remboursement/chargeback
- Revue manuelle des patterns suspects

**Structurel :**
- Exiger une action significative du filleul
- Plafonner les récompenses à vie
- Payer les récompenses en crédit produit (moins attractif pour les fraudeurs)
