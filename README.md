<div align="center">

# 🎯 Marketing Skills — Édition Française

**44 skills marketing pour Claude Code et agents IA, traduits et localisés en français.**

CRO · Copywriting · SEO · Paid Ads (Google / Meta / LinkedIn / TikTok) · Créa pub · Cold email · Growth · Plans AARRR · Relations presse

![Skills](https://img.shields.io/badge/skills-44-2563eb)
![Licence](https://img.shields.io/badge/licence-MIT-22c55e)
![Langue](https://img.shields.io/badge/langue-français-0ea5e9)
![Base](https://img.shields.io/badge/base-marketingskills%20v2.4.1-f97316)

</div>

---

Les skills se déclenchent **automatiquement** quand vous décrivez une tâche marketing **en français** dans Claude Code. Pas de commande à retenir : décrivez ce que vous voulez, le bon skill s'active avec la bonne méthodo.

> *« Crée-moi 5 angles de pub Meta pour cette offre »* → le skill `ad-creative` s'active.
> *« Fais un plan marketing 12 mois pour ce client »* → le skill `marketing-plan` s'active.
> *« Audite le SEO de ce site »* → le skill `seo-audit` s'active.

---

## 🙏 Crédit & licence

Ce projet est la **localisation française** du repo [**`marketingskills`**](https://github.com/coreyhaines31/marketingskills) créé par **[Corey Haines](https://corey.co)** (Swipe Files · Conversion Factory) — 33 000+ ⭐ sur GitHub.

**Tout le travail méthodologique original lui revient.** Cette version se contente de **traduire et localiser** le contenu en français. Distribuée sous **licence [MIT](LICENSE)**, comme l'original. Localisation FR par [Immersive](https://imrsiv.fr).

> 📄 Le README anglais d'origine est conservé sous [`README.en.md`](README.en.md).

---

## 📦 Installation

**Via le système de plugins Claude Code :**

```bash
/plugin marketplace add niarkinho/marketing-skills-fr
/plugin install marketing-skills-fr
```

**Ou en local** — clonez et copiez le dossier `skills/` dans votre projet (`.claude/skills/`) ou globalement (`~/.claude/skills/`) :

```bash
git clone https://github.com/niarkinho/marketing-skills-fr.git
```

Chaque skill est un dossier autonome avec un fichier `SKILL.md` — aucune dépendance à installer.

---

## 🧭 Comment ça marche

Les skills se référencent les uns les autres et partagent un **contexte commun**. Le skill `product-marketing` est le socle : tous les autres le lisent en premier pour comprendre votre produit, votre audience et votre positionnement avant d'agir.

**Convention de contexte** — chaque skill cherche d'abord un fichier :
`.agents/product-marketing.md` (ou `.claude/product-marketing.md`).

Lancez une fois le skill `product-marketing` pour le générer — ensuite, tous les autres skills s'en servent automatiquement.

```
                        ┌──────────────────────────────┐
                        │       product-marketing       │  ← lu en premier par tous
                        └───────────────┬───────────────┘
        ┌──────────┬──────────┬─────────┼─────────┬──────────┬──────────┐
        ▼          ▼          ▼         ▼         ▼          ▼          ▼
    SEO &       CRO       Copy &     Paid &    Growth &   Vente &   Stratégie
    Contenu                Contenu   Mesure    Rétention    GTM
```

> 💼 **En agence ?** Créez **un `.agents/product-marketing.md` par client**, dans le dossier de projet du client. Chaque client garde son contexte (positionnement, ICP, offre, ton), et les skills produisent du contenu sur-mesure pour chacun.

---

## 🎯 Démarrage rapide — campagnes Meta

Les skills clés pour le paid social :

| Skill | Rôle |
|-------|------|
| **`ads`** | Stratégie de campagne, ciblage, budgets, enchères, retargeting, optimisation (Google, **Meta**, LinkedIn, TikTok) |
| **`ad-creative`** | Génération et itération de créa pub à grande échelle — accroches, descriptions, texte principal, avec les **specs Meta exactes** (texte 125 car., titre 40, description 30) |
| **`marketing-psychology`** | Les leviers psychologiques derrière les créas qui performent |
| **`cro`** | Optimiser les landing pages où atterrit le trafic pub |
| **`analytics`** | Mettre en place le tracking de conversion |
| **`ab-testing`** | Tester les créas avec rigueur statistique |

**Exemple** — dans un projet client (avec son `.agents/product-marketing.md`) :

> *« Génère 5 angles de pub Meta pour [offre], avec 3 variantes de texte chacun, en respectant les limites de caractères Meta. »*

---

## 📚 Les 44 skills

<details open>
<summary><b>🔍 SEO &amp; Contenu</b></summary>

| Skill | Description |
|-------|-------------|
| `seo-audit` | Auditer et diagnostiquer les problèmes SEO d'un site |
| `ai-seo` | Optimiser pour les moteurs de recherche IA (AEO / GEO / LLMO) |
| `site-architecture` | Structurer l'arborescence, la navigation et le maillage interne |
| `programmatic-seo` | Créer des pages SEO à grande échelle via templates + data |
| `schema` | Balisage schema.org / données structurées (JSON-LD) |
| `content-strategy` | Planifier une stratégie de contenu et les sujets à couvrir |
| `aso` | Optimiser une fiche App Store / Google Play |

</details>

<details>
<summary><b>📈 CRO (taux de conversion)</b></summary>

| Skill | Description |
|-------|-------------|
| `cro` | Optimiser les conversions d'une page ou d'un formulaire |
| `signup` | Réduire la friction des flux d'inscription |
| `onboarding` | Améliorer l'activation et le time-to-value post-inscription |
| `popups` | Popups, modales et bannières orientés conversion |
| `paywalls` | Paywalls, écrans d'upgrade et feature gates |

</details>

<details>
<summary><b>✍️ Copy &amp; Contenu</b></summary>

| Skill | Description |
|-------|-------------|
| `copywriting` | Écrire et améliorer le copy des pages (home, landing, pricing…) |
| `copy-editing` | Relire, éditer et rafraîchir du copy existant |
| `cold-email` | Cold emails B2B et séquences de relance qui obtiennent des réponses |
| `emails` | Séquences email lifecycle, drip et flux automatisés |
| `social` | Contenu réseaux sociaux + social listening (LinkedIn, X, Insta, TikTok…) |
| `video` | Production de vidéos marketing avec outils IA / Remotion |
| `image` | Génération et optimisation d'images marketing |

</details>

<details>
<summary><b>💰 Paid &amp; Mesure</b></summary>

| Skill | Description |
|-------|-------------|
| `ads` | Stratégie, ciblage et optimisation de campagnes payantes |
| `ad-creative` | Créa pub à grande échelle (specs par plateforme) |
| `ab-testing` | Concevoir des A/B tests avec rigueur statistique |
| `analytics` | Mettre en place et auditer le tracking et la mesure |

</details>

<details>
<summary><b>🚀 Growth &amp; Rétention</b></summary>

| Skill | Description |
|-------|-------------|
| `referrals` | Programmes de parrainage, affiliation et bouche-à-oreille |
| `free-tools` | Concevoir des outils gratuits comme levier d'acquisition |
| `churn-prevention` | Réduire le churn, flux d'annulation, save offers |
| `community-marketing` | Construire et animer une communauté en ligne |
| `lead-magnets` | Créer et optimiser des lead magnets |
| `co-marketing` | Trouver des partenaires et monter des campagnes conjointes |

</details>

<details>
<summary><b>🤝 Vente &amp; Go-to-Market</b></summary>

| Skill | Description |
|-------|-------------|
| `revops` | Revenue operations, lifecycle des leads, handoff marketing→vente |
| `sales-enablement` | Decks, one-pagers, scripts démo, objection handling |
| `launch` | Plans de lancement produit / Product Hunt |
| `pricing` | Décisions de pricing, packaging, monétisation |
| `competitors` | Pages comparatives et « alternative to » pour SEO + vente |
| `competitor-profiling` | Recherche et profilage de concurrents |
| `directory-submissions` | Soumettre son produit à des annuaires (backlinks, découverte) |
| `prospecting` | Trouver, qualifier et lister des prospects |

</details>

<details>
<summary><b>🧠 Stratégie</b></summary>

| Skill | Description |
|-------|-------------|
| `marketing-plan` | Plan marketing complet en 13 sections, structuré AARRR |
| `marketing-ideas` | Banque d'idées et de tactiques de croissance |
| `marketing-psychology` | Principes psychologiques et modèles mentaux appliqués au marketing |
| `customer-research` | Mener et synthétiser de la recherche client (ICP, JTBD, VOC) |
| `product-marketing` | Créer le document de contexte produit (le socle des autres skills) |
| `public-relations` | Relations presse, earned media, pitch de journalistes |

</details>

---

## 🔧 Conventions de localisation

- **Registre** : français pro, avec les anglicismes que les marketeurs utilisent vraiment (ROAS, CPA, CTR, retargeting, lookalike, landing page, copywriting, funnel…).
- **Identifiants en anglais** : les noms de skills (`name:`), les dossiers et les renvois croisés restent en anglais — seul le contenu lisible est traduit.
- **Déclencheurs bilingues** : chaque `description:` mêle formulations FR et termes métier anglais pour un déclenchement fiable.
- Détail complet des règles dans [`GLOSSAIRE-TRADUCTION.md`](GLOSSAIRE-TRADUCTION.md).

**Mettre à jour depuis l'original** : comparer avec le [repo upstream](https://github.com/coreyhaines31/marketingskills) et retraduire les fichiers modifiés en suivant le glossaire.

---

## 📄 Licence

[MIT](LICENSE) — comme le projet original de [Corey Haines](https://github.com/coreyhaines31/marketingskills). Vous êtes libre d'utiliser, modifier et redistribuer, en conservant la mention de copyright.

<div align="center">
<sub>Localisation française par <a href="https://imrsiv.fr">Immersive</a> · Méthodologie originale par <a href="https://corey.co">Corey Haines</a></sub>
</div>
