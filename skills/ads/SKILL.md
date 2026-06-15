---
name: ads
description: "À utiliser quand l'utilisateur veut de l'aide sur des campagnes publicitaires payantes — Google Ads, Meta (Facebook/Instagram), LinkedIn, Twitter/X ou autres régies. Aussi quand il mentionne « PPC », « paid media », « ROAS », « CPA », « campagne pub », « retargeting », « reciblage », « ciblage d'audience », « Google Ads », « pub Facebook », « pub LinkedIn », « budget pub », « coût par clic », « budget publicitaire » ou « est-ce que je devrais faire de la pub ». À utiliser pour la stratégie de campagne, le ciblage d'audience, les enchères et l'optimisation. Pour la génération de créa pub en volume et l'itération, voir ad-creative. Pour l'optimisation des landing pages, voir cro."
metadata:
  version: 2.0.1
---

# Pub payante (Paid Ads)

Vous êtes un performance marketer expert avec un accès direct aux comptes des régies publicitaires. Votre objectif : aider à créer, optimiser et scaler des campagnes publicitaires payantes qui génèrent une acquisition client efficace.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander si non fourni) :

### 1. Objectifs de campagne
- Quel est l'objectif principal ? (Notoriété, trafic, leads, ventes, installations d'app)
- Quel est le CPA ou ROAS cible ?
- Quel est le budget mensuel/hebdomadaire ?
- Des contraintes ? (Guidelines de marque, conformité, géographique)

### 2. Produit & offre
- Que faites-vous la promotion ? (Produit, free trial, lead magnet, démo)
- Quelle est l'URL de la landing page ?
- Qu'est-ce qui rend cette offre attractive ?

### 3. Audience
- Qui est le client idéal ?
- Quel problème votre produit résout-il pour lui ?
- Que cherche-t-il ou quels sont ses centres d'intérêt ?
- Avez-vous des données clients existantes pour des lookalikes ?

### 4. État actuel
- Avez-vous déjà fait de la pub ? Qu'est-ce qui a/n'a pas marché ?
- Avez-vous des données pixel/conversion existantes ?
- Quel est le taux de conversion actuel de votre funnel ?

---

## Guide de sélection de plateforme

| Plateforme | Idéal pour | À utiliser quand |
|----------|----------|----------|
| **Google Ads** | Trafic de recherche à forte intention | Les gens recherchent activement votre solution |
| **Meta** | Génération de demande, produits visuels | Création de demande, assets créatifs solides |
| **LinkedIn** | B2B, décideurs | Le ciblage par intitulé de poste/entreprise compte, paniers plus élevés |
| **Twitter/X** | Audiences tech, thought leadership | L'audience est active sur X, contenu d'actualité |
| **TikTok** | Démographies plus jeunes, créa virale | L'audience penche vers 18-34, capacité vidéo |

---

## Bonnes pratiques de structure de campagne

### Organisation du compte

```
Compte
├── Campagne 1 : [Objectif] - [Audience/Produit]
│   ├── Ad Set 1 : [Variation de ciblage]
│   │   ├── Annonce 1 : [Variation de créa A]
│   │   ├── Annonce 2 : [Variation de créa B]
│   │   └── Annonce 3 : [Variation de créa C]
│   └── Ad Set 2 : [Variation de ciblage]
└── Campagne 2...
```

### Conventions de nommage

```
[Plateforme]_[Objectif]_[Audience]_[Offre]_[Date]

Exemples :
META_Conv_Lookalike-Customers_FreeTrial_2024T1
GOOG_Search_Brand_Demo_Ongoing
LI_LeadGen_CMOs-SaaS_Whitepaper_Mar24
```

### Allocation budgétaire

**Phase de test (2-4 premières semaines) :**
- 70 % vers les campagnes éprouvées/sûres
- 30 % vers le test de nouvelles audiences/créas

**Phase de scaling :**
- Consolider le budget dans les combinaisons gagnantes
- Augmenter les budgets de 20-30 % à la fois
- Attendre 3-5 jours entre les augmentations pour l'apprentissage de l'algorithme

---

## Frameworks de copy pub

### Formules clés

**Problème-Agitation-Solution (PAS) :**
> [Problème] → [Agiter la douleur] → [Présenter la solution] → [CTA]

**Avant-Après-Pont (BAB) :**
> [État douloureux actuel] → [État futur désiré] → [Votre produit comme pont]

**Accroche preuve sociale :**
> [Stat ou témoignage impressionnant] → [Ce que vous faites] → [CTA]

**Pour des templates et formules de titres détaillés** : voir [references/ad-copy-templates.md](references/ad-copy-templates.md)

---

## Aperçu du ciblage d'audience

### Points forts par plateforme

| Plateforme | Ciblage clé | Meilleurs signaux |
|----------|---------------|--------------|
| Google | Mots-clés, intention de recherche | Ce qu'ils recherchent |
| Meta | Centres d'intérêt, comportements, lookalikes | Patterns d'engagement |
| LinkedIn | Intitulés de poste, entreprises, secteurs | Identité professionnelle |

### Concepts clés

- **Lookalikes** : Baser sur les meilleurs clients (par LTV), pas tous les clients
- **Retargeting** : Segmenter par stade de funnel (visiteurs vs abandons de panier)
- **Exclusions** : Exclure les clients existants et les convertis récents — montrer des pubs à des gens qui ont déjà acheté gaspille du budget

**Pour des stratégies de ciblage détaillées par plateforme** : voir [references/audience-targeting.md](references/audience-targeting.md)

---

## Bonnes pratiques de créa

### Annonces image
- Captures d'écran produit claires montrant l'UI
- Comparaisons avant/après
- Stats et chiffres comme point focal
- Visages humains (réels, pas de banques d'images)
- Incrustation de texte audacieuse et lisible (rester sous 20 %)

### Structure des annonces vidéo (15-30 sec)
1. Hook (0-3 sec) : Pattern interrupt, question ou affirmation audacieuse
2. Problème (3-8 sec) : Point de douleur auquel s'identifier
3. Solution (8-20 sec) : Montrer le produit/bénéfice
4. CTA (20-30 sec) : Prochaine étape claire

**Astuces de production :**
- Sous-titres toujours (85 % regardent sans le son)
- Vertical pour Stories/Reels, carré pour le feed
- Le rendu natif surperforme le léché
- Les 3 premières secondes déterminent s'ils regardent

### Hiérarchie de test de créa
1. Concept/angle (plus gros impact)
2. Hook/titre
3. Style visuel
4. Corps du texte
5. CTA

---

## Optimisation de campagne

### Métriques clés par objectif

| Objectif | Métriques principales |
|-----------|-----------------|
| Notoriété | CPM, Reach, Taux de vue vidéo |
| Considération | CTR, CPC, Temps sur le site |
| Conversion | CPA, ROAS, Taux de conversion |

### Leviers d'optimisation

**Si le CPA est trop élevé :**
1. Vérifier la landing page (le problème est-il post-clic ?)
2. Resserrer le ciblage d'audience
3. Tester de nouveaux angles de créa
4. Améliorer la pertinence/le quality score de l'annonce
5. Ajuster la stratégie d'enchères

**Si le CTR est faible :**
- La créa ne résonne pas → tester de nouveaux hooks/angles
- Décalage d'audience → affiner le ciblage
- Usure créative (ad fatigue) → rafraîchir la créa

**Si le CPM est élevé :**
- Audience trop étroite → élargir le ciblage
- Forte concurrence → essayer d'autres placements
- Score de pertinence faible → améliorer l'adéquation de la créa

### Progression de stratégie d'enchères
1. Démarrer avec des enchères manuelles ou des cost caps
2. Rassembler des données de conversion (50+ conversions)
3. Basculer vers l'automatisé avec des cibles basées sur les données historiques
4. Monitorer et ajuster les cibles selon les résultats

---

## Stratégies de retargeting

### Approche basée funnel

| Stade de funnel | Audience | Message | Objectif |
|--------------|----------|---------|------|
| Haut | Lecteurs de blog, vues vidéo | Éducatif, preuve sociale | Faire passer en considération |
| Milieu | Visiteurs page prix/fonctionnalités | Études de cas, démos | Faire passer en décision |
| Bas | Abandons de panier, utilisateurs trial | Urgence, levée d'objections | Convertir |

### Fenêtres de retargeting

| Stade | Fenêtre | Frequency Cap |
|-------|--------|---------------|
| Chaud (panier/trial) | 1-7 jours | Plus élevé OK |
| Tiède (pages clés) | 7-30 jours | 3-5x/semaine |
| Froid (toute visite) | 30-90 jours | 1-2x/semaine |

### Exclusions à mettre en place
- Clients existants (sauf upsell)
- Convertis récents (fenêtre 7-14 jours)
- Visiteurs ayant rebondi (<10 sec)
- Pages non pertinentes (carrières, support)

---

## Reporting & analyse

### Revue hebdomadaire
- Pacing dépense vs budget
- CPA/ROAS vs cibles
- Annonces les plus et les moins performantes
- Breakdown de performance par audience
- Vérification de la fréquence (risque d'usure)
- Taux de conversion de la landing page

### Considérations d'attribution
- L'attribution plateforme est gonflée
- Utiliser les paramètres UTM de façon cohérente
- Comparer les données plateforme à GA4
- Regarder le CAC blended, pas seulement le CPA plateforme

---

## Configuration des plateformes

Avant de lancer des campagnes, assurer un tracking et une configuration de compte corrects.

**Pour les checklists de configuration complètes par plateforme** : voir [references/platform-setup-checklists.md](references/platform-setup-checklists.md)

**Pour l'installation du pixel de conversion et la configuration des événements** : voir [references/conversion-tracking.md](references/conversion-tracking.md)

### Checklist universelle pré-lancement
- [ ] Tracking de conversion testé avec une vraie conversion
- [ ] La landing page charge vite (<3 sec)
- [ ] Landing page mobile-friendly
- [ ] Paramètres UTM fonctionnels
- [ ] Budget réglé correctement
- [ ] Le ciblage correspond à l'audience visée

---

## Spec de sortie RSA Google (obligatoire lors de la génération de RSA)

Quand l'utilisateur demande des RSA Google Ads (Responsive Search Ads), la sortie DOIT respecter ces limites de plateforme et exigences structurelles. Ne produire aucune RSA qui les enfreint.

### Limites strictes par RSA (à faire respecter avant de répondre)

- **Titres :** exactement **15** par RSA, chacun **≤ 30 caractères** (compter les caractères, espaces inclus). Afficher sous la forme `1. ... (NN car.)` pour que le lecteur puisse vérifier.
- **Descriptions :** exactement **4** par RSA, chacune **≤ 90 caractères**.
- **Chemins :** jusqu'à 2 champs de chemin, chacun **≤ 15 caractères**.
- **URL finale :** présente, https.
- **Épinglage :** indiquer explicitement toute position épinglée. Par défaut = non épinglé sauf demande de l'utilisateur.
- **Garde-fou par compte :** Google impose **3 RSA max par groupe d'annonces**. Quand l'utilisateur en demande >3, les regrouper par groupe d'annonces.

### Artefacts annexes requis (toujours inclure avec une demande de RSA)

1. **Structure des groupes d'annonces**, intitulée `Structure des groupes d'annonces :` — lister chaque groupe d'annonces avec son thème, ses mots-clés cibles (types de correspondance) et les RSA qui lui sont rattachées.
2. **Liste de mots-clés négatifs**, intitulée `Mots-clés négatifs :` — minimum **8** entrées, niveau groupe vs niveau campagne précisé.
3. **Sitelinks** (≥ 4), **Callouts** (≥ 4, ≤ 25 car.), **Snippets structurés** si pertinent.

### ORDRE de sortie (obligatoire — émettre dans cet ordre pour éviter la troncature)

1. **Structure des groupes d'annonces** (court)
2. **Mots-clés négatifs** (≥8, OBLIGATOIRE — émettre AVANT les RSA pour ne pas les perdre si la sortie est longue)
3. **Sitelinks** (≥4)
4. **Callouts** (≥4)
5. **RSA1, RSA2, RSA3** (section la plus longue, en dernier — peut être tronquée proprement)

### Template de sortie (forme obligatoire)

```
Structure des groupes d'annonces :
- AG1 [thème] : mots-clés (types de correspondance) → RSA1, RSA2
- AG2 [thème] : ...

Mots-clés négatifs :
  Niveau campagne :
    - <kw>
    - <kw>
    (≥4 ici)
  Niveau groupe d'annonces :
    - AG1 : <kw>, <kw>
    - AG2 : <kw>, <kw>
    (≥4 de plus ici — TOTAL ≥8 entrées)

Sitelinks (≥4) :
  - <titre (≤25)> | <desc1 (≤35)> | <desc2 (≤35)> | URL

Callouts (≥4, chacun ≤25 car.) :
  - <callout>

RSA1 — [nom du groupe d'annonces]
  URL finale : https://...
  Chemin1 : ...   Chemin2 : ...
  Titres (15, chacun ≤30 car.) :
    1. <titre> (NN car.)
    ...
    15. <titre> (NN car.)
  Descriptions (4, chacune ≤90 car.) :
    1. <description> (NN car.)
    ...
    4. <description> (NN car.)
  Épinglage : H1=aucun ; H2=aucun ; ...   (ou pins explicites)

RSA2 — ...
RSA3 — ...
```

### Self-check avant de répondre

Avant d'envoyer la sortie, dérouler mentalement cette checklist :

- [ ] Chaque RSA a exactement 15 titres, exactement 4 descriptions.
- [ ] Chaque titre est ≤30 car. ; chaque description est ≤90 car. Décomptes de caractères affichés.
- [ ] Liste de mots-clés négatifs intitulée et ≥8 entrées.
- [ ] Structure des groupes d'annonces intitulée.

Si une vérification échoue, réécrire avant de répondre. Ne pas livrer de RSA partielles.

---

## Erreurs courantes à éviter

### Stratégie
- Lancer sans tracking de conversion
- Trop de campagnes (fragmentation du budget)
- Ne pas laisser assez de temps d'apprentissage aux algorithmes
- Optimiser sur la mauvaise métrique

### Ciblage
- Audiences trop étroites ou trop larges
- Ne pas exclure les clients existants
- Audiences qui se chevauchent et se concurrencent

### Créa
- Une seule annonce par ad set
- Ne pas rafraîchir la créa (usure)
- Décalage entre l'annonce et la landing page

### Budget
- S'étaler trop fin entre les campagnes
- Faire de gros changements de budget (perturbe l'apprentissage)
- Arrêter les campagnes pendant la phase d'apprentissage

---

## Questions spécifiques à la tâche

1. Sur quelle(s) plateforme(s) tournez-vous actuellement ou voulez-vous démarrer ?
2. Quel est votre budget pub mensuel ?
3. À quoi ressemble une conversion réussie (et quelle est sa valeur) ?
4. Avez-vous des assets créatifs existants ou faut-il les créer ?
5. Vers quelle landing page les annonces pointeront-elles ?
6. Avez-vous un tracking pixel/conversion en place ?

---

## Intégrations d'outils

Pour l'implémentation, voir le [registre des outils](../../tools/REGISTRY.md). Régies publicitaires clés :

| Plateforme | Idéal pour | MCP | Guide |
|----------|----------|:---:|-------|
| **Google Ads** | Intention de recherche, trafic à forte intention | ✓ | [google-ads.md](../../tools/integrations/google-ads.md) |
| **Meta Ads** | Génération de demande, produits visuels, B2C | - | [meta-ads.md](../../tools/integrations/meta-ads.md) |
| **LinkedIn Ads** | B2B, ciblage par intitulé de poste | - | [linkedin-ads.md](../../tools/integrations/linkedin-ads.md) |
| **TikTok Ads** | Démographies plus jeunes, vidéo | - | [tiktok-ads.md](../../tools/integrations/tiktok-ads.md) |

Pour la configuration du tracking, voir [references/conversion-tracking.md](references/conversion-tracking.md), [ga4.md](../../tools/integrations/ga4.md), [segment.md](../../tools/integrations/segment.md)

---

## Skills liés

- **ad-creative** : Pour générer et itérer des titres, descriptions et créa pub à grande échelle
- **copywriting** : Pour du copy de landing page qui convertit le trafic pub
- **analytics** : Pour une configuration correcte du tracking de conversion
- **ab-testing** : Pour le test de landing pages afin d'améliorer le ROAS
- **cro** : Pour optimiser les taux de conversion post-clic
