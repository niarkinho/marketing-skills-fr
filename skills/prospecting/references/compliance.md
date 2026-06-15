# Référence conformité prospection

Les contraintes légales et de ToS plateformes qui s'appliquent à la constitution de listes de prospects. À lire en premier, à chaque mission.

> Conseils opérationnels, pas un avis juridique. Pour les programmes à fort volume ou ceux touchant des résidents UE/UK, faites valider votre dispositif par un avocat spécialisé en données personnelles.

---

## États-Unis — CAN-SPAM (en aval)

CAN-SPAM réglemente l'**envoi** du cold email, pas la constitution de liste. Mais la constitution de liste compte parce que :

- Vous devez pouvoir identifier la source de chaque adresse email que vous contactez (requis en cas de contestation)
- Les règles sur la ligne « from » et le contenu de l'email s'appliquent à l'envoi — mais vous ne pouvez pas mentir sur la façon dont vous avez obtenu le contact
- Les demandes de désinscription doivent être honorées sous 10 jours ouvrés et tracées

**Pour la prospection spécifiquement** : capturer et conserver l'URL source + la date pour chaque contact ajouté à une liste. CAN-SPAM ne l'exige pas explicitement, mais défendre vos pratiques d'expéditeur si.

---

## UE / UK — RGPD

Le cadre applicable le plus strict. Se déclenche quand :

- Votre prospect réside dans l'UE/UK
- Vous traitez des données personnelles (toute information identifiable, y compris les emails professionnels rattachés à une personne nommée)

### Bases légales pour le cold email B2B

Vous avez trois options crédibles :

1. **Intérêt légitime** (le plus courant en B2B). Exige :
   - Le contact occupe une fonction professionnelle susceptible d'être intéressée par votre offre
   - La donnée a été collectée depuis une source publique, en contexte professionnel
   - Vous fournissez un opt-out clair
   - Vous pouvez formuler le test de l'intérêt légitime par écrit

2. **Consentement** — généralement infaisable pour le cold email (vous n'avez pas de consentement avant le premier contact)

3. **Relation client existante** — ne s'applique qu'aux clients actuels, pas aux prospects

### Ce que vous devez faire

- Capturer **source + date + base légale** pour chaque contact
- Honorer les demandes d'accès des personnes concernées (DSAR) — vous devez pouvoir divulguer, corriger ou supprimer sur demande
- Inclure une mention d'information / un opt-out dans le premier outreach
- Ne pas conserver les données personnelles plus longtemps que nécessaire à l'intérêt légitime

### Ce qui disqualifie une liste

- Données LinkedIn scrapées en masse — violation explicite des ToS + risque RGPD
- Adresses email achetées à un courtier de listes sans provenance des sources
- Emails devinés « n'importe qui @ ce domaine » envoyés sans vérification (multiplie le risque + les bounces)

---

## Canada — CASL

Plus strict que CAN-SPAM. Le cold email B2B exige :

- **Consentement exprès** (opt-in explicite) — généralement absent en cold prospecting
- **OU consentement implicite** — relation d'affaires existante dans les 24 derniers mois, OU adresse professionnelle publiée publiquement sur le propre site de l'entreprise dans le but de recevoir de telles communications

**Implication pratique pour les prospects canadiens** : s'appuyer sur l'exception de l'adresse publiée publiquement est la base de cold prospecting la plus défendable au Canada. Vous devez inclure l'identification de l'expéditeur, une adresse postale et un mécanisme de désinscription dans chaque message.

---

## Conditions d'utilisation des plateformes

### LinkedIn

- **Sales Navigator** comme outil de recherche : OK
- **Scraper LinkedIn à quelque échelle que ce soit** : violation explicite des ToS. Les comptes bannis le sont définitivement. À ne pas faire.
- **Apollo, Clay et ZoomInfo** revendiquent des données recoupant LinkedIn via divers canaux légitimes — vérifiez leurs sources de données avant de présumer la conformité
- **InMail et demandes de connexion** : régis par les règles de messagerie propres à LinkedIn, pas par CAN-SPAM/RGPD (car internes à LinkedIn)

### Google Maps

- Les ToS interdisent l'extraction en masse ou la transformation des données Maps en produit
- Recherche assistée par navigateur comme aide à la découverte : acceptable
- Stocker des Place IDs ou de grandes quantités de données Maps structurées dans votre CRM : interdiction explicite des ToS
- Utiliser Maps pour **trouver** des commerces locaux, puis recouper depuis le propre site de l'entreprise pour les données que vous conservez

### Apollo / ZoomInfo / Clearbit

- Tous ont leurs propres ToS limitant la revente, le partage en aval et les cas d'usage
- Lisez votre contrat — vous pouvez généralement utiliser la donnée pour votre propre outreach mais pas en faire un produit
- Ne partagez pas d'extraits publiquement (ex : sur un classement, dans un rapport public)

### Crunchbase

- L'offre gratuite est en lecture seule pour usage personnel
- L'offre payante permet un usage plus large dans le périmètre contractuel
- L'accès API exige une offre payante Pro+

---

## Anti-patterns (à ne pas faire)

1. **Scraper en masse LinkedIn / Google Maps / Yelp.** La recherche assistée par navigateur est OK ; les scrapers automatisés pointés vers ces plateformes ne le sont pas. **Firecrawl et Browserbase conviennent pour le propre site web d'un prospect individuel** (l'URL trouvée par découverte manuelle) — pas pour les plateformes qui hébergent les prospects.
2. **Acheter des listes à des fournisseurs au hasard** sans provenance des sources. Vous héritez de leur exposition juridique.
3. **Deviner des emails et envoyer sans vérifier.** Des taux de bounce supérieurs à 2 % détruisent la réputation d'expéditeur ; juridiquement, vous ne pouvez pas invoquer une base d'« intérêt légitime » pour un email que vous avez fabriqué.
4. **Récupérer des adresses email personnelles** (Gmail, Outlook perso, etc.) depuis des profils publics. Les adresses personnelles augmentent fortement le risque RGPD.
5. **Stocker des données dont vous n'avez pas besoin.** Minimiser la conservation. Ne gardez pas les listes de prospects indéfiniment — le droit à l'effacement RGPD s'applique.
6. **Sauter la documentation de la base légale.** En cas de contestation, vous devez montrer votre travail. Capturez URL source + date de collecte pour chaque contact.
7. **Revendre des listes de prospects.** Vous n'avez peut-être pas le droit de les partager en aval. Lisez les contrats de vos fournisseurs de données.
8. **Contournement de CAPTCHA / mur de connexion.** Même techniquement possible, cela trahit un comportement de bot et viole quasiment tous les ToS.

---

## Checklist d'audit rapide

Avant de livrer une liste à l'utilisateur (ou en aval vers cold-email) :

- [ ] Chaque contact a une URL source + une date de collecte
- [ ] Aucun contact issu de données LinkedIn scrapées
- [ ] Aucun Place ID Google Maps ni grande quantité de données Maps structurées conservés
- [ ] Base légale documentée (test de l'intérêt légitime pour le B2B, ou alternative pertinente)
- [ ] Adresses email validées (contrôle de délivrabilité avant outreach)
- [ ] Adresses personnelles (Gmail, etc.) signalées ou exclues
- [ ] Les contrats des fournisseurs de sources autorisent le cas d'usage prévu
- [ ] Plan de conservation documenté (quand supprimer)
- [ ] Le premier outreach inclura désinscription + mention d'information (enjeu en aval pour le skill cold-email, mais le mentionner dès maintenant)
