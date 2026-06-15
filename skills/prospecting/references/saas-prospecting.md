# Référence prospection SaaS

Pour quand l'utilisateur vend du SaaS ou des services digitaux à d'autres SaaS / entreprises digitales.

---

## Signaux ICP qui comptent (branche SaaS)

Au-delà des données firmographiques standard (secteur, taille, géographie), les prospects SaaS sont qualifiés par :

### Signaux technographiques

- **Stack technique** — utilisent-ils des outils complémentaires (votre cible d'intégration) ou des outils concurrents (une opportunité de switch) ?
- **Changements récents de stack** — ajouter/retirer des outils signale une évaluation active de prestataires
- **Custom maison vs solution sur étagère** — l'outillage DIY signifie souvent un acheteur qui bénéficierait de votre produit
- **Signaux d'offre gratuite/freemium** — utiliser un concurrent gratuit signifie qu'ils sont peut-être prêts à monter en gamme

### Signaux de croissance

- **Levée de fonds** — Série A / B / C dans les 6 derniers mois = budget + nouvelles recrues + besoins en outils
- **Croissance des effectifs** — +10 % sur le dernier trimestre signale une pression de scaling
- **Signaux de recrutement** — ouvertures de postes précises (ex : « Head of RevOps » → ICP pour outillage revops)
- **Vélocité produit** — déploiements fréquents, nouvelles fonctionnalités, articles de blog = motion de croissance saine
- **Postes ouverts pour la fonction de votre acheteur** — si vous vendez aux Marketing Ops et qu'ils en recrutent un, c'est un signal

### Signaux de déclin (downgrade du scoring)

- Licenciements dans le département cible
- Levée de fonds il y a plus de 2 ans sans suite
- Le produit n'a rien déployé depuis 6+ mois
- La page équipe ne montre que les fondateurs (très early — peut ne pas avoir de budget)

---

## Sources de découverte (branche SaaS)

Combiner 2+ sources pour le recoupement.

### Tier 1 — découverte principale

- **Apollo** : données firmographiques + technographiques + contacts. Bon pour constituer de grandes listes initiales.
- **Clay** : enrichissement en waterfall, scoring custom, fusions multi-sources. Idéal pour des listes plus petites et de haute qualité.
- **ZoomInfo** : données firmographiques de niveau entreprise + signaux d'intention. Cher ; mid-market et plus.
- **LinkedIn Sales Navigator** : cartographie des décideurs. À utiliser manuellement, jamais en scraping de masse.

### Tier 2 — signaux technographiques / de croissance

- **BuiltWith** : lookups de stack technique, trouver des sites utilisant des outils précis
- **Wappalyzer** : extension navigateur gratuite + API ; signal de stack technique plus léger
- **Crunchbase** : levées de fonds, effectifs, fondateurs
- **Pitchbook** : données investisseurs plus poussées (entreprise/payant)
- **ProductHunt** : lancements récents, audience de builders
- **Hacker News / Show HN** : builders techniques lançant des produits

### Tier 3 — signaux d'achat

- **Sites d'emploi** (LinkedIn Jobs, Indeed, AngelList) : ouvertures de postes comme signaux
- **RB2B / Clearbit Reveal** : identification de visiteurs (trafic anonyme chaud)
- **Étoiles/forks GitHub de repos concurrents ou adjacents** : signal d'intention au niveau développeur (voir `tools/integrations/github.md` et le CLI `github-prospects.js`). Particulièrement fort pour les SaaS outils dev — un développeur qui a étoilé `vercel/next.js` la semaine dernière est in-market pour de l'infrastructure Next.js adjacente.
- **Articles de blog / changelog récents** : signaux de direction produit
- **Avis G2 mentionnant des switches de concurrent** : signal explicite d'insatisfaction

#### Pattern de prospection GitHub (quand l'audience est composée de développeurs)

Pour les SaaS outils dev, GitHub est l'un des canaux de découverte de la plus haute qualité :

1. Identifier 3–5 repos « ancres » : vos concurrents directs, le leader de votre catégorie, des outils complémentaires utilisés par votre acheteur
2. Récupérer les stargazers (ou les forks pour une intention plus forte) via `node tools/clis/github-prospects.js stargazers <owner/repo> --enrich --with-company --format csv`
3. Filtrer sur les utilisateurs avec un champ `company` renseigné — ce sont les plus faciles à enrichir en aval
4. Coupler avec Apollo/Clay/Hunter pour rechercher l'email par nom + entreprise
5. Valider avec Truelist avant d'ajouter à la liste d'outreach

Compromis : GitHub fournit directement un email pour seulement ~5–20 % des utilisateurs. La force est la qualité du signal — le stargazer d'un outil dev de niche est réellement in-market d'une manière que les seules données firmographiques d'Apollo ne peuvent pas vous dire.

---

## Checklist de qualification (branche SaaS)

Pour chaque candidat, vérifier :

- [ ] Le vertical sectoriel correspond à l'ICP
- [ ] Taille de l'entreprise (effectif) dans la fourchette
- [ ] La stack technique inclut (ou exclut notablement) une technologie cible
- [ ] Le stade de levée correspond à la maturité de l'acheteur
- [ ] Au moins un signal de croissance dans les 90 derniers jours (levée, recrutement, vélocité produit)
- [ ] Une fonction de décideur existe dans l'entreprise (nommée ou déductible des offres d'emploi)
- [ ] Contact email vérifiable
- [ ] Aucun critère disqualifiant (fermée, acquise-et-en-pause, licenciements, hors ICP)

---

## Colonnes de sortie (branche SaaS)

Colonnes CSV recommandées :

```csv
score,company,domain,industry,size_band,country,funding_stage,last_round_date,tech_stack_match,signal,signal_date,contact_name,contact_title,contact_email,email_status,linkedin_url,source_urls,why_prospect,confidence,verified_date,notes
```

Pour le tableau de chat, condenser à : Score | Entreprise | Secteur | Taille | Signal | Contact | Statut email | Confiance.

---

## Sélection des cibles d'outreach prioritaires (SaaS)

Prioriser, pour les 3 à 5 meilleurs leads chauds :

1. **Fraîcheur du signal le plus fort** — une levée il y a 30 jours bat une levée il y a 9 mois
2. **Force du match de stack technique** — un partenaire d'intégration connu bat un fit inféré
3. **Décideur nommé avec email vérifié** — bat un email deviné par pattern de fonction
4. **Confiance multi-sources** — Apollo + Crunchbase d'accord bat une source unique

Chaque cible prioritaire reçoit une justification d'outreach d'une phrase nommant le signal précis : « A levé une Série B il y a 30 jours ; recrute un Head of RevOps ; email du VP of Ops vérifié. »

---

## Erreurs fréquentes (SaaS)

1. **Acheter des listes Apollo en gros** sans revérifier l'email ni recontrôler les données firmographiques. Les données obsolètes sont la norme.
2. **Traiter les données de stack technique comme fiables à 100 %.** BuiltWith et Wappalyzer ratent des choses ; les waterfalls de Clay aussi. Recouper.
3. **Cibler du Série C+ quand on vend du SaaS early-stage.** Le profil acheteur est faux — trop d'étapes achats, trop de bureaucratie.
4. **Cibler du Pre-Seed/Seed** pour des produits exigeant un budget conséquent. Ils n'ont ni le budget ni la bande passante d'évaluation.
5. **Ignorer les données d'intention quand elles existent** (ZoomInfo Intent, 6sense, etc.) — les signaux pré-chauffés battent le cold à chaque fois.
