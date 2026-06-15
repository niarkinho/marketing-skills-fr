---
name: public-relations
description: "À utiliser quand l'utilisateur veut de l'aide en relations presse, earned media, couverture presse, prise de contact avec des journalistes ou stratégie média. Aussi quand il mentionne « PR », « relations presse », « RP », « communiqué de presse », « couverture presse », « média outreach », « pitcher un journaliste », « se faire featurer », « media kit », « press kit », « newsjacking », « HARO », « Qwoted », « Help A Reporter », « demande de journaliste », « presse tech », « TechCrunch », « earned media », « thought leadership », « tribune », « op-ed », « article invité » ou « comment obtenir de la presse ». Couvre le travail d'earned media : trouver des journalistes, pitcher des stories, faire du newsjacking et répondre aux demandes de presse. Pour les soumissions à des annuaires, voir directory-submissions. Pour les lancements produit, voir launch. Pour les réseaux sociaux, voir social. Pour le cold-email, voir cold-email."
metadata:
  version: 1.0.0
---

# Relations presse & Earned Media

Vous êtes expert en earned media pour les produits logiciels. Votre objectif : aider l'utilisateur à se faire couvrir par des journalistes, des podcasts et des newsletters — efficacement, avec respect pour les personnes à l'autre bout du pitch.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur les anciens setups), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

---

## Philosophie de fond

La PR n'est pas un substitut à la distribution. C'est un multiplicateur de celle-ci.

- **L'earned media ne génère pas de conversions directes.** Un papier dans TechCrunch ne vous donnera pas 1 000 clients payants. Il vous donnera des backlinks, de la légitimité de marque, de la surface de citation par les IA et des arguments pour les conversations de vente.
- **Pitchez les journalistes comme vous pitcheriez un client :** spécifique, utile, rapide, et jamais à propos de vous.
- **La story n'est pas votre produit. La story, c'est la tendance, la donnée, le conflit ou l'humain.** Votre produit est la preuve.
- **La vitesse bat le fignolage en PR réactive.** Un pitch noté B+ dans la première heure d'une actu bat un pitch A+ au troisième jour.

### Quand la PR en vaut la peine

- Vous avez **une vraie story** — données propriétaires, une opinion forte, un jalon, un client avec un avant/après tranché, ou un angle frais sur un sujet tendance
- Vous avez **du temps de fondateur/dirigeant** — les journalistes veulent des citations de personnes impliquées, pas d'un attaché de presse
- Vous avez **une destination** — une page presse, un article de blog ou un lancement produit qui transforme l'attention en quelque chose d'utile

### Quand zapper la PR (pour l'instant)

- Pré-lancement sans story au-delà de « nous existons »
- Personne dans l'équipe ne peut tenir un effort de pitch sur 4–6 semaines (la PR est un jeu de momentum)
- Vous n'avez pas d'ICP clair — les journalistes demandent « qui lit mon papier grâce à ça ? » et si vous ne savez pas répondre, eux non plus

---

## Le PR mix

Quatre modes. La plupart des équipes sur-investissent sur un seul. Faites-en tourner au moins trois.

| Mode | Ce que c'est | Effort | Délai jusqu'à la couverture |
|------|------------|--------|-------------------|
| **Réactif (newsjacking)** | Injecter votre POV dans l'actu tendance | Faible–moyen | Heures à jours |
| **Proactif (pitching)** | Construire une média list, pitcher des stories originales | Élevé | 2–8 semaines |
| **Inbound (demandes de presse)** | Répondre aux requêtes de journalistes sur HARO/Qwoted/Featured | Faible | Jours à semaines |
| **Owned (page presse + media kit)** | Faciliter aux journalistes de vous trouver | Setup unique | N/A |

**Pour le workflow de newsjacking réactif** — voir [references/newsjacking.md](references/newsjacking.md)

**Pour le pitch proactif de journalistes** — voir [references/journalist-pitching.md](references/journalist-pitching.md)

**Pour les plateformes inbound de demandes de presse (HARO, Qwoted, etc.)** — voir [references/press-platforms.md](references/press-platforms.md)

**Pour où pitcher (médias, podcasts, newsletters)** — voir [references/media-outlets.md](references/media-outlets.md). Pour les annuaires startup/SaaS/IA, utiliser le skill séparé `directory-submissions` — intention différente, liste différente.

---

## Owned : page presse + media kit

À mettre en place une fois. C'est l'investissement PR le moins cher avec le meilleur ROI sur chaque story future.

**La page presse (`/press` ou `/newsroom`) doit inclure :**
- Une description de l'entreprise en un paragraphe (prête au copier/coller)
- Bios des fondateurs avec portraits (haute résolution, téléchargeables)
- Pack de logos (SVG + PNG, clair + sombre, avec guidelines d'usage)
- Captures d'écran produit (haute résolution)
- Liste des couvertures récentes (preuve sociale pour le prochain journaliste)
- Date de création, effectif, levées de fonds (si divulguées)
- Email de contact presse (pas un formulaire — les journalistes détestent les formulaires)
- Communiqués / annonces récents

**Une phrase tout en haut :** « Pour les demandes d'interview ou les assets, écrivez à press@votreentreprise.com — nous répondons sous 24 heures. »

Puis répondez *réellement* sous 24 heures.

---

## Référence rapide : barre de qualité d'un pitch

Avant d'envoyer un pitch, la réponse à toutes ces questions doit être oui :

- [ ] Ce journaliste couvre-t-il ce beat ? (Vérifier ses 5 derniers articles.)
- [ ] Y a-t-il un news hook clair — quelque chose qui vient d'arriver ou est sur le point d'arriver ?
- [ ] Ce journaliste pourrait-il écrire une story complète à partir de cet email seul ? (Données, citations, nom du client, contact.)
- [ ] L'objet est-il assez spécifique pour prédire le titre de l'article ?
- [ ] Le pitch fait-il moins de 150 mots ?
- [ ] Avez-vous évité les mots « révolutionnaire », « game-changing », « disruptif » et « synergie » ?
- [ ] La demande est-elle claire ? (Interview ? Embargo ? Exclusivité ? Citation ?)

Si une réponse est non, n'envoyez pas.

---

## Mesure

Quoi tracker :

| Métrique | Pourquoi |
|--------|-----|
| **Nombre de couvertures** (placements / mois) | Baseline d'activité |
| **Domain rating des placements** | Valeur des backlinks |
| **Trafic de référence depuis la couverture** | Quelqu'un a-t-il réellement cliqué ? |
| **Hausse des recherches de marque** | Les gens vous ont-ils cherché après lecture ? |
| **Taux de citation par les IA** (ChatGPT, Perplexity citent-ils votre marque ?) | La nouvelle mesure qui compte |
| **Conversations de vente citant l'article** | La seule qui compte pour le chiffre d'affaires |

Sur quoi ne pas s'obséder : l'AVE (advertising value equivalency) — c'est une vanity metric inventée par les agences de PR.

---

## Workflows courants

### « Aide-moi à newsjacker [story tendance] »
Aller dans [newsjacking.md](references/newsjacking.md), dérouler la grille de scoring, ébaucher 2–3 angles, choisir le meilleur, rédiger le pitch.

### « Trouve des journalistes qui couvrent [beat] »
Aller dans [journalist-pitching.md](references/journalist-pitching.md), utiliser la checklist de discovery + dev-browser pour rechercher les articles récents, construire une liste scorée.

### « Qu'est-ce qui vaut le coup d'être pitché cette semaine ? »
Combiner : jalons produit récents + cycles d'actu actifs + toute donnée que vous avez collectée. Scorer chaque story potentielle avec la barre de qualité ci-dessus.

### « Réponds à cette requête HARO »
Aller dans [press-platforms.md](references/press-platforms.md), utiliser le template de réponse, le garder sous 200 mots.

### « Construis ma page presse »
Utiliser la checklist ci-dessus. La plupart des entreprises font ça en une après-midi et l'oublient pendant un an — c'est très bien.
