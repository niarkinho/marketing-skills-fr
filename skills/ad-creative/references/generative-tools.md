# Outils d'IA générative pour la créa pub

Référence pour utiliser les générateurs d'images IA, les générateurs de vidéos et les outils de vidéo basée code afin de produire des visuels pub à grande échelle.

---

## Quand utiliser les outils génératifs

| Besoin | Catégorie d'outil | Meilleur choix |
|------|---------------|----------|
| Images pub statiques (bannières, social) | Génération d'images | ChatGPT Images 2.0, Nano Banana Pro, Flux, Ideogram |
| Images pub avec texte incrusté | Génération d'images (gestion du texte) | Ideogram, Nano Banana Pro |
| Pubs vidéo courtes (6-30 sec) | Génération de vidéos | Veo, Kling, Runway, Sora, Seedance |
| Pubs vidéo avec voix off | Génération de vidéos + voix | Veo/Sora (natif), ou Runway + ElevenLabs |
| Pistes de voix off pour pubs | Génération de voix | ElevenLabs, OpenAI TTS, Cartesia |
| Versions pub multilingues | Génération de voix | ElevenLabs, PlayHT |
| Clonage de brand voice | Génération de voix | ElevenLabs, Resemble AI |
| Mockups produit et variations | Génération d'images + références | Flux (référence multi-images) |
| Pubs vidéo templatées à grande échelle | Vidéo basée code | Remotion |
| Vidéo personnalisée (nom, data) | Vidéo basée code | Remotion |
| Variations cohérentes avec la marque | Génération d'images + refs de style | Flux, Ideogram, Nano Banana Pro |

---

## Génération d'images

### Nano Banana Pro (Gemini)

Le modèle de génération d'images de Google DeepMind, disponible via l'API Gemini.

**Idéal pour :** Images pub haute qualité, visuels produit, rendu de texte
**API :** API Gemini (Google AI Studio, Vertex AI)
**Tarif :** ~0,04 €/image (Gemini 2.5 Flash Image), ~0,24 €/image 4K (Nano Banana Pro)

**Points forts :**
- Rendu de texte solide dans les images (logos, titres)
- Édition d'images native (modifier des images existantes par prompt)
- Disponible via la même API Gemini utilisée pour la génération de texte
- Prend en charge génération et édition dans un seul modèle

**Cas d'usage créa pub :**
- Générer des images pub réseaux sociaux à partir de descriptions textuelles
- Créer des variations de mockup produit
- Éditer des images pub existantes (changer les fonds, modifier les couleurs)
- Générer des images avec le texte du titre incrusté

**Exemple d'API :**
```bash
# En utilisant l'API Gemini pour la génération d'images
curl -X POST "https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-image:generateContent" \
  -H "Content-Type: application/json" \
  -H "x-goog-api-key: $GEMINI_API_KEY" \
  -d '{
    "contents": [{"parts": [{"text": "Create a clean, modern social media ad image for a project management tool. Show a laptop with a kanban board interface. Bright, professional, 16:9 ratio."}]}],
    "generationConfig": {"responseModalities": ["TEXT", "IMAGE"]}
  }'
```

**Docs :** [Gemini Image Generation](https://ai.google.dev/gemini-api/docs/image-generation)

---

### Flux (Black Forest Labs)

Modèles de génération d'images à poids ouverts avec accès API via Replicate et l'API native de BFL.

**Idéal pour :** Images photoréalistes, variations cohérentes avec la marque, génération multi-références
**API :** Replicate, API BFL, fal.ai
**Tarif :** ~0,01-0,06 €/image selon le modèle et la résolution

**Variantes de modèle :**
| Modèle | Vitesse | Qualité | Coût | Idéal pour |
|-------|-------|---------|------|----------|
| Flux 2 Pro | ~6 sec | La plus haute | 0,015 €/MP | Assets de production finaux |
| Flux 2 Flex | ~22 sec | Haute + édition | 0,06 €/MP | Édition itérative |
| Flux 2 Dev | ~2,5 sec | Bonne | 0,012 €/MP | Prototypage rapide |
| Flux 2 Klein | La plus rapide | Bonne | Le plus bas | Génération batch haut volume |

**Points forts :**
- Référence multi-images (jusqu'à 8 images) pour une identité cohérente entre les annonces
- Cohérence produit — même produit dans différents contextes
- Transfert de style depuis des images de référence
- Modèle Dev à poids ouverts pour l'auto-hébergement

**Cas d'usage créa pub :**
- Générer 50+ variations d'annonces avec une identité produit/personne cohérente
- Créer des images produit-en-contexte (votre SaaS sur différents appareils)
- Style-matcher des assets de marque existants à l'aide d'images de référence
- A/B tester rapidement des variations d'images

**Docs :** [Replicate Flux](https://replicate.com/black-forest-labs/flux-2-pro), [BFL API](https://docs.bfl.ml/)

---

### Ideogram

Spécialisé dans la typographie et le rendu de texte dans les images.

**Idéal pour :** Bannières pub avec texte, graphiques de marque, images pub social avec titres
**API :** API Ideogram, Runware
**Tarif :** ~0,06 €/image (API), ~0,009 €/image (abonnement)

**Points forts :**
- Rendu de texte le meilleur du marché (~90 % de précision contre ~30 % pour la plupart des outils)
- Système de référence de style (uploadez jusqu'à 3 images de référence)
- 4,3 milliards de presets de style pour une esthétique de marque cohérente
- Excellent sur les logos et la typographie de marque

**Cas d'usage créa pub :**
- Générer des bannières pub avec le texte du titre directement dans l'image
- Créer des graphiques réseaux sociaux avec du texte de marque incrusté
- Produire plusieurs variations de design avec une typographie cohérente
- Générer des supports promotionnels sans avoir besoin d'un designer pour chaque itération

**Docs :** [Ideogram API](https://developer.ideogram.ai/), [Ideogram](https://ideogram.ai/)

---

### Autres outils d'images

| Outil | Idéal pour | Statut API | Notes |
|------|----------|------------|-------|
| **DALL-E 3** (OpenAI) | Génération d'images générale | API officielle | Intégré à ChatGPT, bon rendu de texte |
| **Midjourney** | Images artistiques, à forte esthétique | Pas d'API publique officielle | Basé sur Discord ; des API non officielles existent mais risque de ban |
| **Stable Diffusion** | Auto-hébergé, personnalisable | Open source | Idéal pour les équipes avec une infrastructure GPU |

---

## Génération de vidéos

### Google Veo

Le modèle de génération de vidéos de Google DeepMind, disponible via l'API Gemini et Vertex AI.

**Idéal pour :** Pubs vidéo haute qualité avec audio natif, vidéo verticale pour le social
**API :** API Gemini, Vertex AI
**Tarif :** ~0,15 €/sec (Veo 3.1 Fast), ~0,40 €/sec (Veo 3.1 Standard)

**Capacités :**
- Jusqu'à 60 secondes en 1080p
- Génération audio native (dialogue, effets sonores, ambiance)
- Sortie verticale 9:16 pour Stories/Reels/Shorts
- Upscale en 4K
- Text-to-video et image-to-video

**Cas d'usage créa pub :**
- Générer des pubs vidéo courtes (15-30 sec) à partir de descriptions textuelles
- Créer des pubs vidéo verticales pour TikTok, Reels, Shorts
- Produire des démos produit avec voix off
- Générer plusieurs variations vidéo depuis le même prompt avec des styles différents

**Docs :** [Veo on Vertex AI](https://cloud.google.com/vertex-ai/generative-ai/docs/video/overview)

---

### Kling (Kuaishou)

Génération de vidéos avec génération audiovisuelle simultanée et contrôles de caméra.

**Idéal pour :** Pubs vidéo cinématiques, contenu plus long, vidéo synchronisée avec l'audio
**API :** API Kling, PiAPI, fal.ai
**Tarif :** ~0,09 €/sec (via fal.ai tiers)

**Capacités :**
- Jusqu'à 3 minutes en 1080p/30-48 fps
- Génération audiovisuelle simultanée (Kling 2.6)
- Text-to-video et image-to-video
- Contrôles de mouvement et de caméra

**Cas d'usage créa pub :**
- Vidéos explicatives produit plus longues
- Vidéos de marque cinématiques avec audio synchronisé
- Animer des images produit en pubs vidéo

**Docs :** [Kling AI Developer](https://klingai.com/global/dev/model/video)

---

### Runway

Plateforme de génération et d'édition vidéo à forte contrôlabilité.

**Idéal pour :** Génération vidéo contrôlée, contenu cohérent en style, édition de séquences existantes
**API :** Runway Developer Portal

**Capacités :**
- Gen-4 : Cohérence personnage/scène entre les plans
- Motion brush et contrôles de caméra
- Image-to-video avec images de référence
- Transfert de style video-to-video

**Cas d'usage créa pub :**
- Générer des pubs vidéo avec des personnages/produits cohérents entre les scènes
- Style-transférer des séquences existantes pour matcher l'esthétique de la marque
- Étendre ou remixer du contenu vidéo existant

**Docs :** [Runway API](https://docs.dev.runwayml.com/)

---

### Sora 2 (OpenAI)

Le modèle de génération de vidéos d'OpenAI avec audio synchronisé.

**Idéal pour :** Vidéo haute fidélité avec dialogue et son
**API :** API OpenAI
**Tarif :** Palier gratuit disponible ; Pro à partir de 0,10-0,50 €/sec selon la résolution

**Capacités :**
- Jusqu'à 60 secondes avec audio synchronisé
- Dialogue, effets sonores et audio d'ambiance
- Variantes sora-2 (rapide) et sora-2-pro (qualité)
- Text-to-video et image-to-video

**Cas d'usage créa pub :**
- Témoignages vidéo et pubs de type talking-head
- Vidéos de démo produit avec narration
- Vidéos de marque narratives

**Docs :** [OpenAI Video Generation](https://platform.openai.com/docs/guides/video-generation)

---

### Seedance 2.0 (ByteDance)

Le modèle de génération de vidéos de ByteDance avec génération audiovisuelle simultanée et entrées multimodales.

**Idéal pour :** Pubs vidéo rapides et abordables avec audio natif, entrées de référence multimodales
**API :** BytePlus (officiel), Replicate, WaveSpeedAI, fal.ai (tiers) ; format d'API compatible OpenAI
**Tarif :** ~0,10-0,80 €/min selon la résolution (estimé 10-100x moins cher que Sora 2 par clip)

**Capacités :**
- Jusqu'à 20 secondes jusqu'en 2K de résolution
- Génération audiovisuelle simultanée (Dual-Branch Diffusion Transformer)
- Text-to-video et image-to-video
- Jusqu'à 12 fichiers de référence en entrée multimodale
- Structure d'API compatible OpenAI

**Cas d'usage créa pub :**
- Production de pubs vidéo courtes en haut volume à faible coût
- Pubs vidéo avec voix off et effets sonores synchronisés en une seule passe
- Génération multi-références (alimenter avec images produit, assets de marque, références de style)
- Itération rapide sur des concepts de pub vidéo

**Docs :** [Seedance](https://seed.bytedance.com/en/seedance2_0)

---

### Higgsfield

Plateforme de création vidéo full-stack avec contrôles de caméra cinématiques.

**Idéal pour :** Pubs vidéo social, style cinématique, contenu mobile-first
**Plateforme :** [higgsfield.ai](https://higgsfield.ai/)

**Capacités :**
- 50+ mouvements de caméra professionnels (zooms, panoramiques, plans drone FPV)
- Animation image-to-video
- Édition, transitions et keyframing intégrés
- Workflow tout-en-un : génération d'image, animation, édition

**Cas d'usage créa pub :**
- Pubs vidéo réseaux sociaux à rendu cinématique
- Animer des images produit en vidéo dynamique
- Créer plusieurs variations vidéo avec différents styles de caméra
- Contenu vidéo rapide à produire pour les campagnes social

---

### Comparatif des outils vidéo

| Outil | Durée max | Audio | Résolution | API | Idéal pour |
|------|-----------|-------|------------|-----|----------|
| **Veo 3.1** | 60 sec | Natif | 1080p/4K | Gemini | Vidéo social verticale |
| **Kling 2.6** | 3 min | Natif | 1080p | Tiers | Cinématique plus long |
| **Runway Gen-4** | 10 sec | Non | 1080p | Officiel | Contrôlé, cohérent |
| **Sora 2** | 60 sec | Natif | 1080p | Officiel | Riche en dialogue |
| **Seedance 2.0** | 20 sec | Natif | 2K | Officiel + tiers | Haut volume abordable |
| **Higgsfield** | Variable | Oui | 1080p | Web | Social, mobile-first |

---

## Génération de voix & audio

Pour superposer des voix off réalistes sur des pubs vidéo, ajouter une narration à des démos produit, ou générer de l'audio pour des vidéos rendues avec Remotion. Ces outils transforment des scripts pub en pistes vocales au son naturel.

### Quand utiliser les outils de voix

De nombreux générateurs vidéo (Veo, Kling, Sora, Seedance) incluent désormais de l'audio natif. Utiliser les outils de voix autonomes quand vous avez besoin de :

- **Voix off sur vidéo muette** — Runway Gen-4 et Remotion produisent une sortie muette
- **Cohérence de brand voice** — Cloner une voix spécifique pour toutes les pubs
- **Versions multilingues** — Le même script pub en 20+ langues
- **Itération de script** — Réenregistrer la voix off sans retourner la vidéo
- **Contrôle précis** — Timing, émotion et rythme exacts

---

### ElevenLabs

Le leader du marché de la génération de voix réaliste et du clonage vocal.

**Idéal pour :** Voix off au son le plus naturel, clonage de brand voice, multilingue
**API :** API REST avec support du streaming
**Tarif :** ~0,12-0,30 € pour 1 000 caractères selon le plan ; à partir de 5 €/mois

**Capacités :**
- 29+ langues avec accent et intonation naturels
- Clonage vocal à partir de courts clips audio (instantané) ou d'enregistrements plus longs (professionnel)
- Contrôle de l'émotion et du style
- Streaming pour génération en temps réel
- Bibliothèque de voix avec des centaines de voix préfabriquées

**Cas d'usage créa pub :**
- Générer des pistes de voix off pour les pubs vidéo
- Cloner la voix du porte-parole de votre marque pour toutes les variations d'annonces
- Produire la même pub en 10+ langues à partir d'un seul script
- A/B tester différents styles de voix (autoritaire vs amical vs urgent)

**Exemple d'API :**
```bash
curl -X POST "https://api.elevenlabs.io/v1/text-to-speech/{voice_id}" \
  -H "xi-api-key: $ELEVENLABS_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "text": "Stop wasting hours on manual reporting. Try DataFlow free for 14 days.",
    "model_id": "eleven_multilingual_v2",
    "voice_settings": {"stability": 0.5, "similarity_boost": 0.75}
  }' --output voiceover.mp3
```

**Docs :** [ElevenLabs API](https://elevenlabs.io/docs/api-reference/text-to-speech)

---

### OpenAI TTS

Text-to-speech simple et abordable intégré à l'API OpenAI.

**Idéal pour :** Voix off rapides, rentable à grande échelle, intégration simple
**API :** API OpenAI (même SDK que GPT/DALL-E)
**Tarif :** 15 €/million de caractères (standard), 30 €/million de caractères (HD) ; ~0,015 €/min avec gpt-4o-mini-tts

**Capacités :**
- 13 voix intégrées (pas de clonage personnalisé)
- Plusieurs langues
- Streaming en temps réel
- Option qualité HD
- API simple — le même SDK que vous utilisez déjà pour GPT

**Cas d'usage créa pub :**
- Voix off rapide et peu coûteuse pour les versions pub de brouillon/test
- Narration en haut volume à faible coût
- Prototyper l'audio d'une pub avant d'investir dans une voix premium

**Docs :** [OpenAI TTS](https://platform.openai.com/docs/guides/text-to-speech)

---

### Cartesia Sonic

Génération de voix à latence ultra-faible conçue pour les applications temps réel.

**Idéal pour :** Voix en temps réel, latence la plus faible, expressivité émotionnelle
**API :** Streaming REST + WebSocket
**Tarif :** À partir de 5 €/mois ; à l'usage à partir de 0,03 €/min

**Capacités :**
- 40 ms de time-to-first-audio (le plus rapide de sa catégorie)
- 15+ langues
- Expressivité non verbale : rires, respiration, inflexions émotionnelles
- Sonic Turbo pour une latence encore plus faible
- API de streaming pour génération en temps réel

**Cas d'usage créa pub :**
- Aperçu pub en temps réel pendant l'itération créative
- Vidéos de démo interactives avec narration dynamique
- Pubs nécessitant des rires, soupirs ou réactions émotionnelles naturels

**Docs :** [Cartesia Sonic](https://docs.cartesia.ai/build-with-cartesia/tts-models/latest)

---

### Voicebox (Open Source)

Studio de synthèse vocale gratuit, local-first, propulsé par Qwen3-TTS. L'alternative open source à ElevenLabs.

**Idéal pour :** Clonage vocal gratuit, génération locale/privée, production batch à coût nul
**API :** API REST locale sur `http://localhost:8000`
**Tarif :** Gratuit (licence MIT). Tourne entièrement sur votre machine.
**Stack :** Tauri (Rust) + React + FastAPI (Python)

**Capacités :**
- Clonage vocal à partir de courts échantillons audio via Qwen3-TTS
- Support multilingue (anglais, chinois, plus à venir)
- Éditeur de timeline multipiste pour composer des conversations
- Inférence 4-5x plus rapide sur Apple Silicon via l'accélération MLX Metal
- API REST locale pour génération programmatique
- Aucune dépendance cloud — tout le traitement en local

**Cas d'usage créa pub :**
- Clonage vocal gratuit du porte-parole de la marque sur toutes les variations d'annonces
- Générer des voix off en batch sans coût par caractère
- Génération privée/locale quand le contenu pub est sensible ou pré-lancement
- Prototyper des variations de voix avant de s'engager sur un service payant

**Exemple d'API :**
```bash
curl -X POST http://localhost:8000/generate \
  -H "Content-Type: application/json" \
  -d '{"text": "Stop wasting hours on manual reporting.", "profile_id": "abc123", "language": "en"}'
```

**Installation :** Applications desktop pour macOS et Windows sur [voicebox.sh](https://voicebox.sh), ou build depuis les sources :
```bash
git clone https://github.com/jamiepine/voicebox.git
cd voicebox && make setup && make dev
```

**Docs :** [GitHub](https://github.com/jamiepine/voicebox)

---

### Autres outils de voix

| Outil | Idéal pour | Différenciateur | API |
|------|----------|---------------|-----|
| **PlayHT** | Grande bibliothèque de voix, faible latence | 900+ voix, latence <300 ms, ultra-réaliste | [play.ht](https://play.ht/) |
| **Resemble AI** | Clonage vocal entreprise | Déploiement on-premise, speech-to-speech en temps réel | [resemble.ai](https://www.resemble.ai/) |
| **WellSaid Labs** | Voix éthiques, sûres pour le commercial | Voix d'acteurs rémunérés, sûres pour usage commercial | [wellsaid.io](https://www.wellsaid.io/) |
| **Fish Audio** | Économique, contrôle de l'émotion | ~50-70 % moins cher qu'ElevenLabs, tags d'émotion | [fish.audio](https://fish.audio/) |
| **Murf AI** | Équipes non techniques | Studio dans le navigateur, 200+ voix | [murf.ai](https://murf.ai/) |
| **Google Cloud TTS** | Écosystème Google, échelle | 220+ voix, 40+ langues, SLA entreprise | [Google TTS](https://cloud.google.com/text-to-speech) |
| **Amazon Polly** | Écosystème AWS, coût | Voix neuronales, contrôle SSML, peu cher en volume | [Amazon Polly](https://aws.amazon.com/polly/) |

---

### Comparatif des outils de voix

| Outil | Qualité | Clonage | Langues | Latence | Prix/1K car. |
|------|---------|---------|-----------|---------|----------------|
| **ElevenLabs** | Le meilleur | Oui (instantané + pro) | 29+ | ~200 ms | 0,12-0,30 € |
| **OpenAI TTS** | Bonne | Non | 13+ | ~300 ms | 0,015-0,030 € |
| **Cartesia Sonic** | Très bonne | Non | 15+ | ~40 ms | ~0,03 €/min |
| **PlayHT** | Très bonne | Oui | 140+ | <300 ms | ~0,10-0,20 € |
| **Fish Audio** | Bonne | Oui | 13+ | ~200 ms | ~0,05-0,10 € |
| **WellSaid** | Très bonne | Non (voix d'acteurs) | Anglais | ~300 ms | Tarif sur mesure |
| **Voicebox** | Bonne | Oui (local) | 2+ | Local | Gratuit (open source) |

### Choisir un outil de voix

```
Besoin d'une voix off pour des pubs ?
├── Besoin de cloner une brand voice spécifique ?
│   ├── Meilleure qualité → ElevenLabs
│   ├── Entreprise/on-premise → Resemble AI
│   └── Économique → Fish Audio, PlayHT
├── Besoin de multilingue (même pub, plusieurs langues) ?
│   ├── Le plus de langues → PlayHT (140+)
│   └── Meilleure qualité → ElevenLabs (29+)
├── Besoin de gratuit / open source / local ?
│   └── Voicebox (MIT, tourne sur votre machine)
├── Besoin de pas cher, rapide, suffisamment bon ?
│   └── OpenAI TTS (0,015 €/min)
├── Besoin d'une licence sûre pour le commercial ?
│   └── WellSaid Labs (voix d'acteurs rémunérés)
└── Besoin de temps réel/interactif ?
    └── Cartesia Sonic (40 ms TTFA)
```

### Workflow : voix + vidéo

```
1. Écrire le script pub (utiliser le skill ad-creative pour le copy)
2. Générer la voix off avec ElevenLabs/OpenAI TTS
3. Générer ou rendre la vidéo :
   a. Vidéo muette depuis Runway/Remotion → superposer la piste vocale
   b. Ou utiliser Veo/Sora/Seedance avec audio natif (sauter la VO séparée)
4. Combiner avec ffmpeg si superposition séparée :
   ffmpeg -i video.mp4 -i voiceover.mp3 -c:v copy -c:a aac output.mp4
5. Générer des variations (scripts, voix ou langues différents)
```

---

## Vidéo basée code : Remotion

Pour des pubs vidéo templatées et data-driven à grande échelle, Remotion est la meilleure option. Contrairement aux générateurs vidéo IA qui produisent une vidéo unique à partir de prompts, Remotion utilise du code React pour rendre une vidéo déterministe, parfaitement conforme à la marque, à partir de templates et de données.

**Idéal pour :** Variations d'annonces templatées, vidéo personnalisée, production cohérente avec la marque
**Stack :** React + TypeScript
**Tarif :** Gratuit pour les particuliers/petites équipes ; licence commerciale requise pour 4+ employés
**Docs :** [remotion.dev](https://www.remotion.dev/)

### Pourquoi Remotion pour les pubs

| Générateurs vidéo IA | Remotion |
|---------------------|----------|
| Sortie unique à chaque fois | Déterministe, pixel-perfect |
| Basé prompt, moins de contrôle | Contrôle code complet sur chaque image |
| Difficile de matcher exactement la marque | Couleurs, polices, espacements de marque exacts |
| Génération une par une | Rendu batch de centaines depuis des données |
| Pas d'insertion de données dynamiques | Personnalisation avec noms, prix, stats |

### Cas d'usage créa pub

**1. Pubs produit dynamiques**
Alimenter un tableau JSON de produits et rendre une pub vidéo unique pour chacun :
```tsx
// Composant Remotion simplifié pour des pubs produit
export const ProductAd: React.FC<{
  productName: string;
  price: string;
  imageUrl: string;
  tagline: string;
}> = ({productName, price, imageUrl, tagline}) => {
  return (
    <AbsoluteFill style={{backgroundColor: '#fff'}}>
      <Img src={imageUrl} style={{width: 400, height: 400}} />
      <h1>{productName}</h1>
      <p>{tagline}</p>
      <div className="price">{price}</div>
      <div className="cta">Shop Now</div>
    </AbsoluteFill>
  );
};
```

**2. A/B tester des variations vidéo**
Rendre le même template avec différents titres, CTA ou schémas de couleurs :
```tsx
const variations = [
  {headline: "Save 50% Today", cta: "Get the Deal", theme: "urgent"},
  {headline: "Join 10K+ Teams", cta: "Start Free", theme: "social-proof"},
  {headline: "Built for Speed", cta: "Try It Now", theme: "benefit"},
];
// Rendre toutes les variations de manière programmatique
```

**3. Vidéos de prospection personnalisées**
Générer des vidéos qui s'adressent aux prospects par leur nom pour du cold outreach ou de la vente.

**4. Production batch de pubs social**
Rendre le même contenu sur différents ratios d'aspect :
- 1:1 pour le feed
- 9:16 pour Stories/Reels
- 16:9 pour YouTube

### Workflow Remotion pour la créa pub

```
1. Concevoir le template en React (ou utiliser l'IA pour générer le composant)
2. Définir le schéma de données (produits, titres, CTA, images)
3. Alimenter le template avec le tableau de données
4. Rendre toutes les variations en batch
5. Uploader vers la régie publicitaire
```

### Pour démarrer

```bash
# Créer un nouveau projet Remotion
npx create-video@latest

# Rendre une seule vidéo
npx remotion render src/index.ts MyComposition out/video.mp4

# Rendre en batch depuis des données
npx remotion render src/index.ts MyComposition --props='{"data": [...]}'
```

---

## Choisir le bon outil

### Arbre de décision

```
Besoin de pubs vidéo ?
├── Templatées, data-driven (même structure, données différentes)
│   └── Utiliser Remotion
├── Créa unique à partir de prompts (exploratoire)
│   ├── Besoin de dialogue/voix off ? → Sora 2, Veo 3.1, Kling 2.6, Seedance 2.0
│   ├── Besoin de cohérence entre les scènes ? → Runway Gen-4
│   ├── Besoin de vidéo social verticale ? → Veo 3.1 (9:16 natif)
│   ├── Besoin de haut volume à faible coût ? → Seedance 2.0
│   └── Besoin de travail de caméra cinématique ? → Higgsfield, Kling
└── Les deux → Utiliser l'IA générative pour la créa hero, Remotion pour les variations

Besoin de pubs image ?
├── Besoin de texte/titres dans l'image ? → Ideogram
├── Besoin de cohérence produit entre les variations ? → Flux (multi-réf)
├── Besoin d'itérations rapides sur des images existantes ? → Nano Banana Pro
├── Besoin de la plus haute qualité visuelle ? → Flux Pro, Midjourney
└── Besoin de haut volume à faible coût ? → Flux Klein, Nano Banana
```

### Comparatif de coûts pour 100 variations pub

| Approche | Outil | Coût approximatif |
|----------|------|-----------------|
| 100 images statiques | Nano Banana Pro | ~4-24 € |
| 100 images statiques | Flux Dev | ~1-2 € |
| 100 images statiques | API Ideogram | ~6 € |
| 100 × vidéos de 15 sec | Veo 3.1 Fast | ~225 € |
| 100 × vidéos de 15 sec | Remotion (templaté) | ~0 € (rendu auto-hébergé) |
| 10 vidéos hero + 90 templatées | Veo + Remotion | ~22 € + temps de rendu |

### Workflow recommandé pour une production pub à grande échelle

1. **Générer la créa hero** avec l'IA (Nano Banana, Flux, Veo) — haute qualité, exploratoire
2. **Construire des templates** dans Remotion basés sur les patterns de créa gagnants
3. **Produire des variations en batch** avec Remotion via des données (produits, titres, CTA)
4. **Itérer** — utiliser les outils IA pour les nouveaux angles, Remotion pour l'échelle

Cette approche hybride vous donne l'exploration créative des générateurs IA et la cohérence et l'échelle du rendu basé code.

---

## Specs d'images par plateforme

En générant des images pour des pubs, demander les bonnes dimensions :

| Plateforme | Placement | Ratio d'aspect | Taille recommandée |
|----------|-----------|-------------|-----------------|
| Meta Feed | Image unique | 1:1 | 1080x1080 |
| Meta Stories/Reels | Vertical | 9:16 | 1080x1920 |
| Meta Carousel | Carré | 1:1 | 1080x1080 |
| Google Display | Paysage | 1.91:1 | 1200x628 |
| Google Display | Carré | 1:1 | 1200x1200 |
| LinkedIn Feed | Paysage | 1.91:1 | 1200x627 |
| LinkedIn Feed | Carré | 1:1 | 1200x1200 |
| TikTok Feed | Vertical | 9:16 | 1080x1920 |
| Twitter/X Feed | Paysage | 16:9 | 1200x675 |
| Twitter/X Card | Paysage | 1.91:1 | 800x418 |

Incluez ces dimensions dans vos prompts de génération pour éviter d'avoir à recadrer ou redimensionner.
