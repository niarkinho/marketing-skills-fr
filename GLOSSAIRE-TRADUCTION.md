# Glossaire & conventions de traduction (FR)

Ce document est la **référence unique** appliquée à la traduction française de tous les skills.
Toute personne (ou agent) qui traduit un fichier DOIT suivre ces règles à la lettre pour garantir l'homogénéité.

Projet : localisation française de `marketingskills` de Corey Haines (licence MIT).
Registre validé : **FR pro + anglicismes métier conservés**. Localisation légère.

---

## 1. Règle d'or : ce qui NE se traduit JAMAIS

Ce sont des **identifiants techniques**. Les modifier casse le déclenchement des skills et les renvois croisés.

- Le champ `name:` du frontmatter YAML → **inchangé** (ex : `name: ad-creative` reste `ad-creative`).
- Les **noms de dossiers** des skills → inchangés (`skills/ad-creative/`).
- `metadata.version` → inchangé.
- Les **renvois entre skills** dans le corps : « see ad-creative », « voir le skill `cro` » → le nom du skill reste en anglais (`cro`, `ads`, `ab-testing`…). On traduit la phrase autour, pas l'identifiant.
- Les **liens relatifs** (`[texte](references/audience-targeting.md)`, `../../tools/...`) → la **cible** du lien reste inchangée (les fichiers gardent leur nom). On traduit seulement le `texte` visible du lien.
- Les **noms de fichiers** `.md` dans `references/` → inchangés.
- Le bloc de code, les commandes shell, les endpoints d'API, les clés JSON, les noms de métriques techniques (`cost_per_action_type`, `daily_budget`) → inchangés.

---

## 2. Anglicismes métier : à CONSERVER tels quels

Ce sont les termes que les marketeurs francophones utilisent réellement. On NE les traduit PAS.

ROAS · ROI · CPA · CPC · CPM · CTR · CVR · AOV · LTV · CAC · ROAS cible ·
retargeting · remarketing · lookalike (audience) · custom audience · A/B test · split test ·
landing page · copywriting · copy · funnel · pixel · tracking · UTM · conversion ·
lead · lead magnet · lead gen · CTA · KPI · churn · paywall · opt-in · opt-out · nurturing ·
scoring · pipeline · onboarding · funnel · hook · creative (au sens « créa pub ») ·
SaaS · B2B · B2C · PME · PPC · paid media · paid ads · organic · earned media · owned media ·
bid · bidding · placement · frequency cap · prospect · prospecting · upsell · cross-sell ·
freemium · free trial · drip campaign · cold email · ad set · ad group · RSA · objective ·
brand · branding · positioning (peut devenir « positionnement ») · sitemap · backlink · schema markup

> Bon réflexe : si un dirigeant d'agence dirait le mot en anglais à l'oral, on le garde.

## 2bis. Termes à TRADUIRE (français naturel)

audience → audience · budget → budget · awareness → notoriété · traffic → trafic ·
sales → ventes · headline → titre (ou « accroche » selon contexte) · description → description ·
primary text → texte principal · ad copy → texte de l'annonce / accroche pub ·
targeting → ciblage · exclusions → exclusions · bidding strategy → stratégie d'enchères ·
conversion rate → taux de conversion · click-through rate → garder CTR · spend → dépense (budget dépensé) ·
customer → client · best customers → meilleurs clients · revenue → chiffre d'affaires (CA) ·
weekly review → revue hebdomadaire · learning phase → phase d'apprentissage ·
ad fatigue → usure créative (ad fatigue) · social proof → preuve sociale ·
pain point → point de douleur / problème · value proposition → proposition de valeur ·
free tool → outil gratuit · landing page → **garder** landing page

---

## 3. Frontmatter `description:` — déclencheurs BILINGUES

C'est le champ le plus important : il décide si le skill se déclenche.
Objectif : déclenchement fiable quand l'utilisateur écrit **en français**, sans perdre le déclenchement anglais.

Règles :
1. Reformuler la phrase d'intro en français : « Quand l'utilisateur veut… » / « À utiliser quand l'utilisateur… ».
2. Traduire les exemples de phrases en français **ET** garder les termes métier anglais courants.
3. Ajouter 2-4 formulations françaises typiques en plus de celles traduites.
4. Conserver les renvois vers les autres skills en anglais (`see ad-creative` → « pour la génération de créa, voir `ad-creative` »).

**Exemple — skill `ads` :**
```yaml
description: "À utiliser quand l'utilisateur veut de l'aide sur des campagnes publicitaires payantes — Google Ads, Meta (Facebook/Instagram), LinkedIn, Twitter/X ou autres régies. Aussi quand il mentionne « PPC », « paid media », « ROAS », « CPA », « campagne pub », « pub Facebook », « publicité Meta », « retargeting », « reciblage », « ciblage d'audience », « budget pub », « coût par clic », « budget publicitaire » ou « est-ce que je devrais faire de la pub ». Pour la stratégie de campagne, le ciblage, les enchères et l'optimisation. Pour la génération de créa pub en volume, voir `ad-creative`. Pour l'optimisation des landing pages, voir `cro`."
```

---

## 4. Localisation légère (au passage)

- **Devises** : `$` → `€` dans les exemples chiffrés (ex : `$50/day` → `50 €/jour`).
- **Exemples géographiques** : `US` / `United States` → `France` quand c'est trivial et sans incidence ; `["US"]` dans un bloc de code JSON d'API → **laisser** (`["FR"]` seulement si l'exemple est purement illustratif et hors bloc technique).
- **Suppression de bruit hors-sujet** : dans `skills/ads/SKILL.md`, **supprimer entièrement** la section « Medical / CFM compliance (when product context indicates pt-BR medical practice) » et toute référence à la conformité médicale brésilienne / aux termes pt-BR. Retirer aussi, dans le self-check et l'ordre de sortie, les puces qui renvoient à ce bloc CFM.
- **Specs plateformes intactes** : limites de caractères (Meta 125/40/30, RSA Google 15 titres × 30 car. / 4 desc. × 90 car., LinkedIn, TikTok, X…), quantités, dimensions d'images → **ne jamais modifier les chiffres**.
- **Dates / trimestres** : `2024Q1` → `2024T1` acceptable dans les exemples de nommage.

---

## 5. Registre & ton

- **Instructions adressées à l'agent IA** (la majorité du corps) : infinitif ou impératif neutre.
  - « Before Starting » → « Avant de commencer »
  - « Gather this context » → « Rassembler ce contexte »
  - « Check for product marketing context first » → « Vérifier d'abord le contexte product marketing »
- **Quand le skill s'adresse au marketeur humain** (questions, « you »): **vouvoiement** professionnel.
  - « What's your monthly budget? » → « Quel est votre budget mensuel ? »
- Titres de sections (`##`) : traduits.
- Garder le **même découpage** (mêmes titres, même ordre, mêmes tableaux, mêmes blocs de code). On traduit le contenu, on ne réorganise pas.
- Les tableaux : traduire les en-têtes et les cellules de texte ; garder les valeurs techniques.

---

## 6. Frontmatter — forme à préserver

```yaml
---
name: <inchangé>
description: <traduit, bilingue déclencheurs>
metadata:
  version: <inchangé>
---
```
Conserver exactement la structure YAML (clés, indentation). Ne traduire que la valeur de `description`.

---

## 7. Checklist par fichier (avant de valider)

- [ ] `name:` et `metadata.version` inchangés.
- [ ] `description:` reformulée en FR avec déclencheurs bilingues.
- [ ] Renvois entre skills : noms de skills laissés en anglais.
- [ ] Liens relatifs : cible inchangée, texte visible traduit.
- [ ] Anglicismes métier conservés (section 2), reste traduit.
- [ ] Blocs de code / endpoints / clés JSON / métriques inchangés.
- [ ] `$ → €`, exemples US → FR triviaux.
- [ ] (skill `ads` uniquement) bloc CFM médical brésilien supprimé.
- [ ] Chiffres de specs plateformes intacts.
- [ ] Même structure (titres, ordre, tableaux) que l'original.
