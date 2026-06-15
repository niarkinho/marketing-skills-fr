# Marketing Skills — version française 🇫🇷

**44 skills marketing pour Claude Code et agents IA, traduits et localisés en français.**
CRO, copywriting, SEO, paid ads (Google / Meta / LinkedIn / TikTok), créa pub, cold email, prospection, growth, plans marketing AARRR, relations presse, et plus encore.

Les skills se déclenchent automatiquement quand vous décrivez une tâche marketing **en français** (ex : « crée-moi une campagne Meta », « écris des accroches pub », « fais-moi un plan marketing pour ce client »).

---

## 🙏 Crédit & licence

Ce projet est la **localisation française** du repo [`marketingskills`](https://github.com/coreyhaines31/marketingskills) créé par **[Corey Haines](https://corey.co)** (Swipe Files / Conversion Factory) — 33 000+ ⭐ sur GitHub.

Tout le travail méthodologique original lui revient. Cette version se contente de **traduire et localiser** le contenu en français. Distribué sous **licence MIT** (voir [`LICENSE`](LICENSE)), comme l'original. Localisation FR réalisée pour **[Immersive](https://imrsiv.fr)**.

> Le README anglais d'origine est conservé sous [`README.en.md`](README.en.md).

---

## 📦 Installation (Claude Code)

```bash
# Ajouter ce dossier comme marketplace de plugins, puis installer
/plugin marketplace add /chemin/vers/marketing-skills-fr
/plugin install marketing-skills-fr
```

Ou copier directement le dossier `skills/` dans votre projet (`.claude/skills/` ou `~/.claude/skills/`). Chaque skill est un dossier autonome avec un `SKILL.md`.

---

## 🧭 Comment ça marche

Les skills se référencent les uns les autres et partagent un **contexte commun**. Le skill `product-marketing` est le socle : tous les autres le lisent en premier pour comprendre le produit, l'audience et le positionnement avant d'agir.

**Convention de contexte** — au début, chaque skill cherche un fichier de contexte :
`.agents/product-marketing.md` (ou `.claude/product-marketing.md`).

### 👉 Adaptation agence (Immersive)

Comme on travaille en agence **pour plusieurs clients**, le bon réflexe est de créer **un fichier de contexte par client** dans le dossier de projet du client. Exemple pour un projet Cupkiller :

```
projet-cupkiller/
└── .agents/product-marketing.md   ← positionnement, ICP, offre, ton de Cupkiller
```

Lancez ensuite le skill `product-marketing` une fois par client pour générer ce fichier — les autres skills (ads, ad-creative, cro…) s'en serviront automatiquement.

---

## 🎯 Démarrage rapide — campagnes Meta

Les skills clés pour le paid social :

| Skill | À quoi il sert |
|-------|----------------|
| `ads` | Stratégie de campagne, ciblage, budgets, enchères, retargeting, optimisation (Google, **Meta**, LinkedIn, TikTok) |
| `ad-creative` | Génération et itération de créa pub à grande échelle — accroches, descriptions, texte principal, avec les **specs Meta exactes** (texte 125 car., titre 40, description 30) |
| `marketing-psychology` | Principes psychologiques derrière les créas qui performent |
| `cro` | Optimisation des landing pages où atterrit le trafic pub |
| `analytics` | Mise en place du tracking de conversion |
| `ab-testing` | Tests de créa avec rigueur statistique |

Exemple : ouvrez Claude Code dans un projet client avec son `.agents/product-marketing.md`, puis tapez
*« Génère 5 angles de pub Meta pour [offre] avec 3 variantes de texte chacun »* → le skill `ad-creative` se déclenche.

---

## 📚 Les 44 skills

SEO & contenu : `seo-audit` · `ai-seo` · `site-architecture` · `programmatic-seo` · `schema` · `content-strategy` · `aso`
CRO : `cro` · `signup` · `onboarding` · `popups` · `paywalls`
Copy & contenu : `copywriting` · `copy-editing` · `cold-email` · `emails` · `social` · `video` · `image`
Paid & mesure : `ads` · `ad-creative` · `ab-testing` · `analytics`
Growth & rétention : `referrals` · `free-tools` · `churn-prevention` · `community-marketing` · `lead-magnets` · `co-marketing`
Vente & GTM : `revops` · `sales-enablement` · `launch` · `pricing` · `competitors` · `competitor-profiling` · `directory-submissions` · `prospecting`
Stratégie : `marketing-plan` · `marketing-ideas` · `marketing-psychology` · `customer-research` · `product-marketing` · `public-relations`

Chaque skill a sa description complète dans son `SKILL.md`.

---

## 🔧 Maintenance & mise à jour

- Les **conventions de traduction** (anglicismes conservés, identifiants laissés en anglais, localisation €/FR…) sont documentées dans [`GLOSSAIRE-TRADUCTION.md`](GLOSSAIRE-TRADUCTION.md). À suivre pour toute nouvelle traduction.
- Les **noms de skills** (`name:`), **noms de dossiers** et **renvois croisés** restent en anglais (identifiants techniques) — seul le contenu lisible est en français.
- Pour répercuter une mise à jour de l'original : comparer avec le repo upstream de Corey Haines et retraduire les fichiers modifiés en suivant le glossaire.
- Les `evals/*.json` (fixtures de test) et `tools/integrations/*.md` (doc API) sont restés en anglais (contenu technique universel).
