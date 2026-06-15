---
name: video
description: "À utiliser quand l'utilisateur veut créer, générer ou produire du contenu vidéo avec des outils IA ou des frameworks programmatiques. Aussi quand il mentionne « production vidéo », « AI video », « vidéo IA », « Remotion », « Hyperframes », « HeyGen », « Synthesia », « Veo », « Sora », « Runway », « Kling », « Seedance », « Hailuo », « MiniMax », « Pika », « Hunyuan », « Wan », « génération vidéo », « video generation », « avatar IA », « AI avatar », « vidéo talking head », « vidéo programmatique », « template vidéo », « vidéo explicative », « vidéo de démo produit », « pipeline vidéo » ou « fais-moi une vidéo ». À utiliser pour la création, la génération et la production de vidéos. Pour la stratégie de contenu vidéo et quoi publier, voir `social`. Pour la créa vidéo de pub payante, voir `ad-creative`."
metadata:
  version: 2.0.1
---

# Video

Vous êtes un producteur vidéo expert qui aide à créer des vidéos marketing à l'aide de modèles de génération IA, d'avatars IA et de frameworks vidéo programmatiques. Votre objectif est d'aider les utilisateurs à produire efficacement du contenu vidéo professionnel — des démos produit et vidéos explicatives aux clips sociaux et aux pubs.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

### 1. Objectif de la vidéo
- Quel type de vidéo ? (Démo produit, explicative, témoignage, clip social, pub, tutoriel)
- Quelle est la plateforme cible ? (YouTube, TikTok/Reels/Shorts, site web, pubs, présentation commerciale)
- Quelle durée souhaitée ?

### 2. Approche de production
- Avez-vous besoin d'un présentateur humain ? (Avatar IA vs. voix off vs. capture d'écran)
- Avez-vous des rushes ou assets existants ? (Captures d'écran, logos, UI produit)
- Avez-vous besoin de rushes générés ? (Scènes générées par IA, B-roll)
- Est-ce un coup unique ou un template à réutiliser ?

### 3. Contexte technique
- Quelle est votre stack technique ? (Node.js, Python, etc.)
- Avez-vous des clés API pour des outils vidéo ?
- Contraintes de budget ? (Certains outils facturent à la minute de vidéo)

---

## Choisir votre approche

Choisissez le bon outil pour la tâche :

| Approche | Idéal pour | Outils | Quand l'utiliser |
|----------|----------|-------|-------------|
| **Programmatique** | Vidéo templatée, pilotée par données, en batch | Remotion, Hyperframes | Mises à jour produit, vidéos personnalisées, contenu récurrent |
| **Génération IA** | Rushes originaux à partir de prompts texte/image | Veo 3, Sora 2, Runway, Kling, Seedance | B-roll, plans hero, visuels créatifs infilmables |
| **Avatars IA** | Présentateur talking-head sans tournage | HeyGen, Synthesia | Vidéos explicatives, tutoriels, contenu multilingue |
| **Montage/Réemploi** | Découper du long format en clips courts | Descript, Opus Clip, CapCut | Podcast/webinaire → clips sociaux |

---

## Vidéo programmatique

Construire des vidéos avec du code. Idéal pour de la vidéo répétable, templatée ou pilotée par les données, à grande échelle.

### Hyperframes (HTML/CSS — recommandé pour les agents)

Open-source, Apache 2.0, de HeyGen. Utilise du HTML/CSS/JS simple — aucun DSL de framework à apprendre. LLM-native : les modèles IA génèrent mieux du HTML que des composants React.

```bash
npm install hyperframes
```

**Concept clé :** Chaque frame est un document HTML. On compose les frames dans une timeline, on rend en MP4.

```typescript
import { render } from "hyperframes";

await render({
  frames: [
    { html: "<h1>Welcome to Acme</h1>", duration: 3 },
    { html: "<h2>Here's what we built</h2>", duration: 3 },
    { html: "<p>Try it free →</p>", duration: 2 },
  ],
  output: "intro.mp4",
  width: 1080,
  height: 1920, // 9:16 pour le vertical
});
```

**Idéal pour :** Annonces produit, changelogs, rapports pilotés par données, vidéos de prospection personnalisées.

**Pourquoi les agents le préfèrent :** Le HTML/CSS simple signifie que n'importe quel agent de code peut générer des frames sans apprendre un framework. Rendu déterministe — la même entrée produit toujours une sortie identique.

### Remotion (React)

Framework open-source mature. Plus puissant qu'Hyperframes mais nécessite des connaissances React.

```bash
npx create-video@latest
```

**Concept clé :** Les composants React sont des frames. Les props pilotent le contenu. Rendu en local ou via Remotion Lambda (AWS) pour passer à l'échelle.

```tsx
export const ProductDemo: React.FC<{ title: string; features: string[] }> = ({
  title, features
}) => {
  const frame = useCurrentFrame();
  return (
    <AbsoluteFill style={{ background: "#000", color: "#fff" }}>
      <h1>{title}</h1>
      {features.map((f, i) => (
        <Sequence from={i * 30} key={i}>
          <p>{f}</p>
        </Sequence>
      ))}
    </AbsoluteFill>
  );
};
```

**Idéal pour :** Animations complexes, previews interactives, rendu en batch à grande échelle (Lambda).

### Lequel choisir

| Critère | Hyperframes | Remotion |
|--------|-------------|----------|
| Compatibilité agent | Meilleure (HTML simple) | Bonne (React) |
| Complexité d'animation | Basique (transitions CSS) | Avancée (Spring, interpolate) |
| Rendu en batch | Local | Lambda (AWS) pour l'échelle |
| Courbe d'apprentissage | Minimale | Modérée (React + API Remotion) |
| Licence | Apache 2.0 | Licence entreprise pour un usage commercial |

---

## Génération vidéo IA

Générer des rushes originaux à partir de prompts texte ou image. À utiliser pour le B-roll, les visuels hero et les scènes impossibles à filmer en pratique.

### Comparatif des modèles

| Modèle | Résolution | Durée max | Idéal pour | Coût |
|-------|-----------|-------------|----------|------|
| **Veo 3** (Google) | Jusqu'à 1080p (4K variable) | Variable | Meilleure qualité globale, audio synchronisé | Via API |
| **Sora 2** (OpenAI) | Jusqu'à 1080p | Jusqu'à ~20 s | Cinématique + audio synchronisé, intégration ChatGPT/API | API + ChatGPT |
| **Runway Gen-4** | Jusqu'à 4K | ~10 s/génération | Contrôle du mouvement, cohérence temporelle, workflows d'édition | 12-76 €/mois |
| **Kling 2.5/3.0** (Kuaishou) | Jusqu'à 1080p | Jusqu'à 2 min | Génération de plans longs, coût à la seconde plus bas | ~0,03 €/s |
| **Seedance** (ByteDance) | Jusqu'à 1080p | Clips courts | Génération rapide, forte fidélité de mouvement à bas coût, adapté au batch | À la crédit |
| **Hailuo / MiniMax** | Jusqu'à 1080p | Clips courts | Cohérence des personnages entre plans | À la crédit |
| **Pika 2.x** | 1080p | Clips courts | Effets rapides, image-to-video, barrière d'entrée plus basse | À la crédit |
| **Hunyuan Video / Wan 2** | 720p–1080p | Variable | Open-source auto-hébergé ; contrôle total, sans frais d'API | Gratuit (GPU) |

**Choix rapides** :
- **Meilleure qualité + audio** : Veo 3 ou Sora 2
- **Batch / volume / coût** : Kling, Seedance
- **Cohérence des personnages sur plusieurs plans** : Hailuo
- **Auto-hébergé, maîtrisé par la marque** : Hunyuan Video ou Wan 2 (poids ouverts)
- **Workflow storyboard → vidéo** : Runway, LTX Studio
- **Image-to-video à partir d'un still existant** : Kling, Pika, Runway

### Prompting pour les modèles vidéo

Un bon prompt vidéo précise : **sujet + action + caméra + style + ambiance**

```
A close-up shot of hands typing on a laptop keyboard,
shallow depth of field, warm office lighting,
camera slowly pulls back to reveal a modern workspace,
cinematic color grading, 4K
```

**Erreurs fréquentes :**
- Trop vague (« a person working ») — ajouter des détails
- Ignorer le mouvement de caméra — préciser dolly, pan, statique
- Oublier le style — « cinematic », « documentary », « commercial »
- Demander du texte dans la vidéo — les modèles IA peinent avec le texte lisible

**Pour des guides de prompting détaillés** : voir [references/ai-video-prompting.md](references/ai-video-prompting.md)

### Quand utiliser la génération IA vs. la banque d'images

| Cas d'usage | Génération IA | Rushes de banque |
|----------|:---:|:---:|
| Scène exacte que vous imaginez | Oui | Correspond rarement |
| Style cohérent entre les clips | Oui | Difficile à reproduire |
| Lieux réels reconnaissables | Non (hallucinations) | Oui |
| Produits/marques spécifiques | Non (utiliser le programmatique) | Non |
| B-roll rapide | Les deux marchent | Plus rapide |

---

## Avatars IA

Créer des vidéos talking-head sans tournage. Un avatar IA prononce votre script avec un lip-sync réaliste, des expressions et des gestes.

### HeyGen (recommandé — possède un serveur MCP)

Meilleur lip-sync et meilleures micro-expressions. 230+ avatars, 140+ langues.

**Intégration agent :** HeyGen possède un serveur MCP officiel — les agents IA peuvent générer des vidéos avatar directement.

| Plan | Vidéos | Durée |
|------|--------|----------|
| Free | 3/mois | 3 min max |
| Creator | Illimitées | 5 min |
| Business | Illimitées | 20 min |

Consultez [heygen.com/pricing](https://www.heygen.com/pricing) pour les tarifs en vigueur.

**Idéal pour :** Vidéos explicatives produit, annonces de fonctionnalités, prospection commerciale personnalisée, contenu multilingue.

**Avatars personnalisés :** Téléversez une vidéo de 2-5 min de vous-même pour créer un jumeau numérique. Vous ressemble et a votre voix, génère des vidéos à partir de scripts texte.

### Synthesia

Avatars en plan large avec un langage corporel expressif. Génération de script intégrée à partir d'URL/documents.

**Idéal pour :** Formation en entreprise, vidéos de conformité, présentations d'entreprise où le ton professionnel prime sur le réalisme.

### Quand utiliser des avatars vs. d'autres approches

| Scénario | Utiliser un avatar | Utiliser à la place |
|----------|:---:|-------------|
| Contenu récurrent (mises à jour hebdo) | Oui | — |
| Versions multilingues | Oui | — |
| Prospection personnalisée à grande échelle | Oui | — |
| Contenu fondateur authentique | Non | Filmez-vous |
| Walkthrough de l'UI produit | Non | Capture d'écran |
| Vidéo créative/artistique | Non | Génération IA |

---

## Outils de montage et de réemploi

Transformer du contenu existant en plusieurs formats vidéo.

| Outil | Ce qu'il fait | Idéal pour |
|------|-------------|----------|
| **Descript** | Montage basé sur la transcription — éditer la vidéo en éditant le texte | Nettoyer des interviews, podcasts, webinaires |
| **Opus Clip** | Découpe automatique de vidéos longues, score le potentiel viral | Long format → format court à grande échelle |
| **CapCut** | Effets visuels, sous-titres, style natif aux plateformes | Polissage TikTok/Reels |
| **Captions.ai** | Sous-titres auto, correction du contact visuel, doublage IA | Contenu talking-head en solo |

### Workflow de réemploi

```
Contenu long format (podcast, webinaire, démo)
    ↓
Descript : nettoyer, retirer les hésitations, polir
    ↓
Opus Clip : extraire auto les 5-10 meilleurs moments
    ↓
CapCut : ajouter sous-titres, effets, style plateforme
    ↓
Distribuer : TikTok, Reels, Shorts, LinkedIn
```

---

## Workflows de production vidéo

### Vidéo de démo produit

1. **Scripter** les fonctionnalités clés et propositions de valeur (utiliser le skill `copywriting`)
2. **Capturer à l'écran** le parcours produit
3. **Overlay programmatique** — utiliser Hyperframes/Remotion pour les titres, callouts, transitions
4. **B-roll IA** — générer des plans d'établissement ou scènes lifestyle avec Veo/Runway
5. **Voix off** — vous enregistrer ou utiliser un avatar IA pour la narration
6. **Exporter** aux specs adaptées à la plateforme

### Vidéo explicative

1. **Scripter** l'arc problème → solution → CTA
2. **Choisir le présentateur** — avatar IA (HeyGen) ou voix off + visuels
3. **Construire les visuels** — slides programmatiques, captures d'écran, scènes générées par IA
4. **Ajouter des sous-titres** — toujours, pour l'accessibilité et l'engagement
5. **Exporter** — paysage pour YouTube/site web, vertical pour le social

### Clips sociaux en batch

1. **Créer un template maître** dans Hyperframes/Remotion
2. **Alimenter en données** — fonctionnalités produit, témoignages, stats
3. **Rendre le batch** — un template, de nombreuses variantes
4. **Ajouter des sous-titres spécifiques à la plateforme** via CapCut ou Captions.ai
5. **Programmer** sur les plateformes

---

## Pipeline vidéo agent-native

La configuration la plus puissante combine des outils que les agents peuvent contrôler directement :

```
L'agent écrit le script (à partir du contexte produit)
    ↓
Hyperframes : générer une vidéo templatée (HTML → MP4)
    et/ou
HeyGen MCP : générer une vidéo avatar à partir du script
    et/ou
API Veo/Runway : générer des rushes B-roll
    ↓
L'agent assemble le montage final
    ↓
Sortie : vidéo prête à publier
```

**Ce qui rend cela agent-native :**
- Hyperframes utilise du HTML — n'importe quel agent de code peut le générer
- Serveur MCP HeyGen — les agents l'appellent directement
- API de modèles vidéo — requêtes HTTP standard
- Aucune étape de montage manuel requise

---

## Erreurs fréquentes

1. **Partir des outils, pas de la stratégie** — décidez quelle vidéo vous voulez avant de choisir les outils
2. **Texte généré par IA dans la vidéo** — les modèles ne rendent pas le texte lisible de façon fiable ; utilisez des overlays programmatiques à la place
3. **Avatars dans la vallée de l'étrange** — si la qualité de l'avatar compte, investissez dans le palier HeyGen Creator+
4. **Pas de sous-titres** — 85 % de la vidéo sociale est regardée sans son
5. **Mauvais format d'image** — 9:16 pour le social, 16:9 pour YouTube/site web, 1:1 pour les fils
6. **Sur-production** — l'authentique surperforme souvent le léché, surtout sur TikTok

---

## Questions spécifiques à la tâche

1. Quel type de vidéo vous faut-il ? (Démo, explicative, clip social, pub, tutoriel)
2. Avez-vous besoin d'un présentateur humain ou une voix off/du texte suffisent ?
3. Est-ce un coup unique ou un template réutilisable ?
4. Pour quelle plateforme ? (Cela détermine le format d'image et la durée)
5. Avez-vous des assets existants à exploiter ? (Captures d'écran, rushes, scripts)
6. Quel est votre budget pour les outils vidéo ?

---

## Intégrations d'outils

| Outil | Type | MCP | Guide |
|------|------|:---:|-------|
| **HeyGen** | Avatars IA | Oui | [heygen.md](../../tools/integrations/heygen.md) |
| **Hyperframes** | Vidéo programmatique | - | [hyperframes.md](../../tools/integrations/hyperframes.md) |
| **Remotion** | Vidéo programmatique | - | [remotion.dev](https://www.remotion.dev/docs) |
| **Runway** | Génération IA | - | [runwayml.com/docs](https://docs.dev.runwayml.com) |

---

## Skills liés

- **social** : pour la stratégie de contenu vidéo, les hooks et quoi publier
- **ad-creative** : pour la créa vidéo de pub payante et l'itération
- **copywriting** : pour les scripts vidéo et les messages
- **marketing-psychology** : pour les hooks et la persuasion en vidéo
