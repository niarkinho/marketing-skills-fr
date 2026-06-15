# Référence de conformité SMS

Référence de conformité exhaustive pour le marketing SMS dans les principales juridictions, templates de copy d'opt-in et templates de réponse STOP/HELP.

> Ceci est une aide opérationnelle, pas un conseil juridique. Pour les programmes à fort volume (50K+ abonnés) ou tout programme générant un chiffre d'affaires non trivial, faites valider votre setup de conformité par un avocat expérimenté en TCPA.

---

## États-Unis — TCPA

### De quoi il s'agit

Le Telephone Consumer Protection Act (1991, amendé) régule les appels et SMS marketing. La FCC le fait appliquer ; des plaignants privés intentent des actions sur sa base. Dommages-intérêts légaux : 500–1 500 $ **par message**. Les class actions atteignent facilement 7 à 8 chiffres.

### Niveaux de consentement

| Type | Ce qu'il couvre | Comment le capturer |
|------|---------------|----------------|
| **Consentement écrit explicite** | SMS marketing (ventes, promotions, offres) | Case à cocher + mention claire, capturée électroniquement avec horodatage |
| **Consentement explicite (non écrit)** | Informationnel/transactionnel (livraison, alertes de compte) | Numéro fourni pendant la transaction, en sachant qu'il servira à envoyer des SMS |
| **Relation d'affaires établie** | PAS suffisante pour le SMS marketing | Ne s'applique pas |

### Exigences du consentement écrit explicite

Le flow d'opt-in doit capturer l'ensemble de :

1. Le destinataire a accepté de recevoir des SMS marketing de votre marque
2. Le destinataire comprend que le consentement n'est pas une condition d'achat
3. La mention a affiché l'attente de fréquence, l'avis de tarifs message et données, les instructions STOP/HELP, le lien vers les conditions
4. L'accord a été enregistré électroniquement avec horodatage

### Template de mention d'opt-in (conforme)

```
By signing up via text, you agree to receive recurring automated promotional and
personalized marketing text messages (e.g., cart reminders) from [Brand] at the
cell number used when signing up. Consent is not a condition of any purchase.
Reply HELP for help and STOP to cancel. Msg frequency varies. Msg & data rates
may apply. View [Terms](link) and [Privacy](link).
```

Placez ceci **directement à côté** du champ de numéro de téléphone et du bouton d'envoi. Ne l'enterrez pas dans un footer.

### Quiet hours

- **Fédéral** : 8h–21h dans le fuseau horaire local du destinataire
- **États plus stricts** : Floride (8h–20h), Oklahoma (8h–20h), Washington (8h–20h)
- **Recommandé par les opérateurs** : 9h–20h heure locale du destinataire
- **Défaut pratique** : 9h–20h heure locale du destinataire pour la sécurité

Le fuseau horaire est déterminé par l'indicatif régional, mais les indicatifs mentent (les gens déménagent). Les grandes plateformes (Klaviyo, Postscript, Attentive) gèrent cela automatiquement ; vérifiez que la vôtre le fait.

### Gestion STOP/HELP

**Variantes de STOP que vous devez honorer** : STOP, END, CANCEL, UNSUBSCRIBE, QUIT, STOPALL, OPTOUT

**Réponse STOP** (après réception de STOP) :
```
You're unsubscribed from [Brand] alerts. No more messages will be sent. Reply HELP for help.
```

**Variantes de HELP** : HELP, INFO

**Réponse HELP** :
```
[Brand] alerts: For help, visit [URL] or email [support@brand.com]. Msg & data rates may apply. Reply STOP to cancel.
```

**Règles critiques** :
- Honorer STOP **en quelques secondes**, à chaque fois, sur chaque variante de mot-clé
- Ne pas exiger du destinataire qu'il se connecte ou visite un site web pour se désinscrire
- Une seule confirmation de STOP est autorisée ; ne pas envoyer d'autres messages après
- Les réponses HELP ne comptent pas comme des messages marketing et ne sont pas soumises aux quiet hours

### Exemple de formulation de footer conforme TCPA par type de séquence

- **Confirmation d'opt-in** : « Reply HELP for help, STOP to cancel. Msg & data rates may apply. » — requis
- **Promotionnel récurrent** : « Reply STOP to opt out » — requis trimestriellement au minimum ; recommandé par les opérateurs à chaque envoi
- **Transactionnel** : non requis par le TCPA mais les opérateurs l'attendent ; à inclure pour la sécurité

---

## États-Unis — A2P 10DLC

### De quoi il s'agit

L'enregistrement Application-to-Person 10-Digit Long Code, géré par The Campaign Registry (TCR). Requis pour les entreprises envoyant des SMS via des numéros 10DLC (long codes classiques) depuis 2022. Les opérateurs (T-Mobile, AT&T, Verizon) le font appliquer ; le trafic non enregistré est bridé ou bloqué.

### Composants de l'enregistrement

1. **Enregistrement de la marque**
   - Nom de l'entité légale, EIN, type d'entreprise
   - Trust score attribué (Standard ou Verified)
   - Confiance plus élevée = meilleur débit, frais plus bas

2. **Enregistrement de campagne** (un par cas d'usage)
   - Cas d'usage : Marketing, Account Notification, Customer Care, Public Service, Higher Education, Polling and Voting, 2FA, Delivery Notification, etc.
   - Texte des exemples de messages (doit correspondre à ce que vous envoyez réellement)
   - Description et capture d'écran du flow d'opt-in
   - Formulation d'opt-out
   - Formulation du message d'aide
   - Estimation de volume

3. **Affectation des numéros** aux campagnes

### Niveaux de débit (varient selon l'opérateur et le trust score)

| Trust score + cas d'usage | Débit |
|------------------------|-----------|
| Marque vérifiée, marketing | 75–100+ msg/sec |
| Marque standard, marketing | 4–10 msg/sec |
| Non enregistré | 0,1 msg/sec ou bloqué |

### Rejets fréquents

- Le texte des exemples de messages ne correspond pas aux envois réels
- La capture d'écran du flow d'opt-in ne montre pas la mention requise
- Contenu « SHAFT » (Sex, Hate, Alcohol, Firearms, Tobacco) sans cas d'usage explicite
- Descriptions de campagne génériques ou vagues

**Délai de traitement** : 1–7 jours ouvrés. À anticiper dans les plannings de lancement.

---

## UE / UK — RGPD + Directive ePrivacy

### Exigences de consentement

- **Opt-in explicite** : action affirmative claire (pas de cases pré-cochées)
- **Spécifique** : l'opt-in doit porter spécifiquement sur le SMS marketing, distinct des CGU génériques
- **Informé** : la personne concernée doit savoir qui traite et pourquoi
- **Librement donné** : ne peut pas être lié à l'accès au service

### Dispositions obligatoires

- Identité de l'expéditeur dans chaque message
- Opt-out facile dans chaque message
- Droit d'accès aux données (DSAR)
- Droit à l'effacement
- Conservation des preuves de consentement pour la durée du traitement + délai de prescription

### Exposition aux sanctions

Amendes RGPD jusqu'à 20 M€ ou 4 % du chiffre d'affaires mondial, le montant le plus élevé étant retenu.

---

## Canada — CASL

### Consentement

- **Consentement explicite** : opt-in explicite (même standard que le consentement écrit explicite TCPA américain)
- **Consentement implicite** : relation d'affaires existante dans les 24 mois — usage limité, expire

### Chaque message doit inclure

- Identification de l'expéditeur (raison sociale + tout nom commercial)
- Adresse postale
- Contact téléphone, email ou site web
- Mécanisme de désinscription qui fonctionne dans les 10 jours ouvrés

### Exposition aux sanctions

Jusqu'à 10 M CAD par infraction. Appliqué par le CRTC.

---

## Australie — Spam Act 2003

- Consentement explicite ou inféré (l'inféré a une application étroite)
- ID expéditeur requis
- Désinscription fonctionnelle requise
- Appliqué par l'ACMA

---

## Programmes multi-juridictionnels

Si vous envoyez simultanément aux US + UE + Canada :

- Par défaut, appliquer le standard le **plus strict** de toutes les juridictions (consentement écrit explicite TCPA US + opt-in explicite RGPD)
- Tracker la juridiction de consentement par abonné
- Quiet hours par défaut 9h–20h heure locale du destinataire
- Inclure tous les identifiants requis dans chaque message

---

## Checklist de conformité prête pour audit

- [ ] Enregistrement A2P 10DLC complet (US, le cas échéant)
- [ ] Le flow d'opt-in inclut toutes les mentions requises, adjacentes au champ de téléphone
- [ ] Le texte de la mention correspond aux exemples de messages enregistrés en A2P
- [ ] L'événement d'opt-in capture : horodatage, IP, URL de la page, mention exacte affichée
- [ ] Mots-clés STOP/HELP honorés sur toutes les variantes
- [ ] Quiet hours appliquées au niveau plateforme (heure locale du destinataire)
- [ ] La politique de confidentialité inclut une section SMS
- [ ] Les conditions générales d'utilisation incluent les conditions SMS
- [ ] Preuves de consentement conservées selon la loi applicable (typiquement 4+ ans US, plus long UE)
- [ ] Processus de gestion des DSAR (UE) et de révocation du consentement
- [ ] Identité de l'expéditeur dans chaque message
- [ ] Footer de conformité sur chaque message promotionnel (recommandé) ou trimestriellement au minimum (requis)
- [ ] Tester STOP/HELP depuis un vrai numéro de téléphone chaque trimestre pour vérifier que ça fonctionne toujours
