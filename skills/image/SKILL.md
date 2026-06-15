---
name: image
description: "À utiliser quand l'utilisateur veut créer, générer, éditer ou optimiser des images marketing — hero d'article de blog, visuels sociaux, mockups produit, bannières de profil, visuels de listing ou assets de marque. Aussi quand il mentionne « génération d'image IA », « AI image generation », « génère une image », « crée un visuel », « mockup produit », « hero image », « image de couverture », « visuel réseaux sociaux », « bannière », « bannière de profil », « Flux », « Midjourney », « DALL-E », « GPT Image », « Ideogram », « Nano Banana », « Recraft », « Stable Diffusion », « Canva », « Figma », « optimisation d'image », « compresser des images », « WebP » ou « OG image ». Couvre la création et l'optimisation d'images marketing tout-terrain. Pour la créa image de pub payante et les specs par plateforme, voir ad-creative. Pour la production vidéo, voir video."
metadata:
  version: 2.0.1
---

# Image

Vous êtes un producteur de contenu visuel expert qui aide à créer des images marketing à l'aide de modèles de génération IA, d'outils de design et des bonnes pratiques d'optimisation. Votre objectif est d'aider les utilisateurs à produire efficacement des assets visuels professionnels — des hero d'article de blog et visuels sociaux aux mockups produit et bannières de profil.

## Avant de commencer

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non encore couvertes ou spécifiques à cette tâche.

Rassembler ce contexte (demander s'il n'est pas fourni) :

### 1. Objectif de l'image
- Quel type d'image ? (Hero de blog, visuel social, mockup produit, bannière, asset de marque, OG image)
- Quelle plateforme ou quel emplacement ? (Site web, social, listing d'annuaire, store d'applis, email)
- Quelles dimensions vous faut-il ?

### 2. Approche de production
- Avez-vous des assets de marque existants ? (Logo, couleurs, polices, charte graphique)
- Avez-vous besoin d'un style photoréaliste ou illustratif ?
- Est-ce un coup unique ou un template à réutiliser ?

### 3. Contexte technique
- Avez-vous des clés API pour des outils d'image ? (Gemini, Replicate/Flux, Ideogram)
- Contraintes de budget ? (Certains outils facturent à l'image)
- Avez-vous besoin que l'image soit optimisée pour la performance web ?

---

## Choisir votre approche

Choisissez le bon outil pour la tâche :

| Approche | Idéal pour | Outils | Quand l'utiliser |
|----------|----------|-------|-------------|
| **Génération IA** | Images originales à partir de prompts texte | Gemini/Nano Banana, Flux, Ideogram | Hero de blog, visuels sociaux, scènes lifestyle |
| **Édition IA** | Modifier des images existantes | Gemini, Flux Flex | Détourage, changements de style, variantes |
| **Outils de design** | Assets templatés, cohérents avec la marque | Canva, Figma | Bannières de profil, templates sociaux, présentations |
| **Capture + Overlay** | Mises en avant d'UI produit | Capture d'écran navigateur + overlay code | Mockups produit, annonces de fonctionnalités |
| **Banque d'images** | Scènes business/lifestyle génériques | Unsplash, Pexels | Quand la vitesse prime sur l'unicité |

---

## Génération d'images IA

Générer des images originales à partir de prompts texte. La façon la plus rapide de créer des visuels marketing uniques.

### Comparatif des modèles

| Modèle | Idéal pour | Texte dans les images | API | Coût |
|-------|----------|:-:|-----|------|
| **Gemini Image** (Google, « Nano Banana » / Nano Banana Pro) | Tout-terrain, édition, référence multi-images, rendu de texte | Bon | [Gemini API](https://ai.google.dev/gemini-api/docs/image-generation) | Voir [pricing](https://ai.google.dev/gemini-api/docs/pricing) |
| **Flux** (Black Forest Labs — Pro 1.1, Kontext, Dev, Schnell) | Photoréalisme, cohérence de marque, batch ; Kontext pour l'édition dans l'image | Limité | [BFL API](https://docs.bfl.ai/), Replicate, fal.ai | Voir [pricing](https://docs.bfl.ai/quick_start/pricing) |
| **Ideogram 3.0** | Typographie, visuels brandés, rendu de texte précis | Le meilleur | [Ideogram API](https://developer.ideogram.ai/) | Voir [pricing](https://about.ideogram.ai/api-pricing) |
| **ChatGPT Images 2.0 / GPT Image** (OpenAI) | Usage général, intégration ChatGPT, édition native | Bon | [OpenAI API](https://platform.openai.com/docs/guides/image-generation) | Voir [pricing](https://platform.openai.com/docs/pricing) |
| **Midjourney v7** | Visuels artistiques, haute esthétique, direction artistique | Amélioré | Pas d'API officielle ; Discord + Web | Sur abonnement |
| **Recraft V3** | Illustrations vectorielles + cohérentes avec la marque, assets de design | Solide | [Recraft API](https://www.recraft.ai/docs) | À la crédit |
| **Stable Diffusion 3.5 / SDXL** | Auto-hébergé, personnalisable, fine-tunable | Variable | Open source | Gratuit (coûts GPU) |

**Note :** DALL-E 3 est entièrement déprécié. Les modèles d'image actuels d'OpenAI sont la famille GPT Image / ChatGPT Images (`gpt-image-1` et suivants).

### Lequel utiliser

```
Besoin de texte/titres dans l'image ?
├── Oui → Ideogram 3.0 (le meilleur), Gemini (bon), GPT Image / ChatGPT Images (correct)
└── Non ↓

Besoin de cohérence produit/marque sur de nombreuses images ?
├── Oui → Flux (référence multi-images), Gemini Nano Banana Pro, Recraft V3
└── Non ↓

Besoin d'éditer une image existante (sur place) ?
├── Oui → Gemini (édition native), Flux Kontext, ChatGPT Images
└── Non ↓

Besoin d'assets de marque vectoriels / illustratifs ?
├── Oui → Recraft V3 (le meilleur pour le vectoriel + cohérence de marque), Midjourney (artistique)
└── Non ↓

Besoin de la plus haute qualité visuelle / direction artistique ?
├── Oui → Flux Pro 1.1, Midjourney v7
└── Non ↓

Besoin de volume à bas coût ?
└── Flux Schnell, Gemini Flash, Stable Diffusion (auto-hébergé)
```

### Bases du prompting

Un prompt image solide suit : **Sujet + Décor + Style + Lumière + Composition + Technique**

```
A laptop on a minimal white desk showing a dashboard UI,
soft directional lighting from the left, shallow depth of field,
clean commercial photography style, 16:9 aspect ratio, 4K
```

**Erreurs fréquentes :**
- Trop vague (« a business image ») — ajouter des détails précis
- Oublier le format d'image — toujours préciser les dimensions
- Demander du texte complexe — utiliser des overlays à la place pour tout ce qui dépasse de courts titres
- Aucune direction de style — « photorealistic », « flat illustration », « 3D render »

Pour des guides de prompting détaillés par modèle, voir [references/ai-image-prompting.md](references/ai-image-prompting.md).

---

## Outils de design

Pour du travail templaté et cohérent avec la marque, là où la génération IA est surdimensionnée ou trop imprévisible.

### Canva

Idéal pour les non-designers qui ont besoin d'un rendu léché rapidement.

- **Points forts :** Bibliothèque de templates massive, brand kit, Magic Resize (un design → toutes les tailles), collaboration d'équipe
- **Idéal pour :** Visuels sociaux, présentations, en-têtes d'email, bannières simples
- **Limites :** Moins de contrôle que Figma, les templates peuvent sembler génériques
- **Compatibilité agent :** Possède une API mais limitée — meilleur comme outil avec humain dans la boucle

### Figma

Idéal pour les équipes avec des design systems ou des besoins au pixel près.

- **Points forts :** Composants de design system, auto layout, handoff développeur, plugins
- **Idéal pour :** OG images via templates, assets de design system, layouts complexes
- **Limites :** Courbe d'apprentissage plus raide, demande des compétences de design
- **Compatibilité agent :** Possède une API et un serveur MCP pour lire les designs

### Quand utiliser les outils de design vs. la génération IA

| Scénario | Outil de design | Génération IA |
|----------|:-:|:-:|
| La charte graphique exacte doit être respectée | Oui | Peut-être (avec de fortes images de référence) |
| Besoin de 20 variantes de taille d'un design | Oui (Canva Magic Resize) | Non |
| Hero image unique pour un article de blog | Non | Oui |
| Template réseaux sociaux récurrent | Oui | Non |
| Mockup produit avec vraie UI | Non (utiliser des captures) | Non (UI hallucinée) |
| Visuel abstrait/créatif | Non | Oui |

---

## Workflows d'images marketing

### Hero images de blog et d'article

L'image en haut de chaque article. Donne le ton, améliore le partage, requise pour les previews OG/sociaux.

1. **Définir le concept** — quelle métaphore visuelle représente le sujet ?
2. **Générer avec l'IA** — utiliser Flux ou Gemini pour le photoréalisme, Ideogram si du texte est nécessaire
3. **Préciser 1200x630** (fonctionne à la fois pour le hero et l'OG image) ou **1920x1080** pour le pleine largeur
4. **Optimiser** — compresser à <200 Ko, servir en WebP avec fallback JPEG

**Pattern de prompt :**
```
[Visual metaphor for topic], clean modern style,
bright natural lighting, shallow depth of field,
professional blog header aesthetic, 1200x630
```

### Visuels réseaux sociaux

Images spécifiques par plateforme pour les posts organiques.

| Plateforme | Taille principale | Format | Notes |
|----------|-------------|:---:|-------|
| Twitter/X | 1200x675 | 16:9 | Large image card |
| LinkedIn | 1200x627 | 1.91:1 | Image de fil |
| Instagram Feed | 1080x1080 | 1:1 | Carré ; 1080x1350 (4:5) marche aussi très bien |
| Instagram Stories | 1080x1920 | 9:16 | Plein écran vertical |
| Facebook | 1200x630 | 1.91:1 | Image de partage de lien |

**Workflow :**
1. Créer le concept hero à la résolution maximale nécessaire
2. Utiliser Canva Magic Resize ou un recadrage manuel pour les variantes par plateforme
3. Ajouter les overlays texte de façon programmatique (Ideogram ou post-traitement) si nécessaire
4. Exporter aux dimensions spécifiques à la plateforme

### Mockups produit et captures d'écran

Mettez en valeur votre UI produit en contexte. Les modèles IA hallucinent l'UI — ne les utilisez pas pour ça.

1. **Capturer de vraies captures d'écran** de votre produit en résolution 2x
2. **Encadrer dans des mockups d'appareils** — utiliser un cadre navigateur, ordinateur portable ou templates de téléphone
3. **Ajouter du contexte** — flèches de callout, labels de fonctionnalités, comparaisons avant/après
4. **Annoter avec du code** — Hyperframes ou HTML/CSS pour des overlays programmatiques

**Outils :** DevTools du navigateur (capture), Shottr (Mac), CleanShot X, ou la CLI `screencapture`.

### Bannières de profil et de listing

Bannières pour les profils, listings d'annuaires et pages de marketplace. Souvent la première impression visuelle.

| Plateforme | Taille | Notes |
|----------|------|-------|
| Couverture personnelle LinkedIn | 1584x396 | 4:1, zone de sécurité au centre |
| Couverture entreprise LinkedIn | 1128x191 | 5.9:1 ; LinkedIn recommande jusqu'à 4200x700 |
| En-tête Twitter/X | 1500x500 | 3:1, partiellement masqué par l'avatar |
| Galerie Product Hunt | 1270x760 | 5:3, jusqu'à 6 images |
| Profil G2 | 1280x720 | 16:9, captures d'écran produit préférées |
| Aperçu social GitHub | 1280x640 | 2:1, s'affiche dans les link cards |
| Captures App Store | Variable selon l'appareil | Voir le skill `aso` pour les specs complètes |
| Feature graphic Google Play | 1024x500 | ~2:1, requise pour le listing du store |

**Bonnes pratiques :**
- **Garder le texte minimal** — les bannières sont vues en petites tailles sur mobile
- **Centrer le contenu critique** — les bords sont recadrés différemment selon l'appareil
- **Montrer le produit** — les vraies captures d'UI surperforment les visuels abstraits sur les listings d'annuaires
- **Respecter votre marque** — couleurs, polices, placement du logo cohérents
- **Mettre à jour selon la saison** — des bannières datées signalent un produit inactif

**Workflow :**
1. Choisir la ou les plateformes et noter les dimensions exactes
2. Pour les annuaires (Product Hunt, G2) : utiliser de vraies captures produit avec une annotation légère
3. Pour les profils (LinkedIn, Twitter) : utiliser les couleurs de marque + tagline + plan produit optionnel
4. Générer avec des templates Canva/Figma ou Ideogram (si beaucoup de texte)
5. Tester à la taille d'affichage réelle — dézoomer pour vérifier la lisibilité

### Assets de marque

Logos, icônes et illustrations. La génération IA a ses limites ici.

| Asset | Génération IA | Outil de design | Notes |
|-------|:-:|:-:|-------|
| Logo | Médiocre — incohérent, pas vectoriel | Oui (Figma) | Toujours concevoir ou commander les logos |
| Icône d'appli | Point de départ correct | Oui (Figma) | Générer des concepts, affiner manuellement |
| Illustrations | Bon pour explorer le style | Selon les cas | IA pour les concepts, finaliser dans un outil de design |
| Favicons | Non | Oui | Dériver du logo |
| Icônes sociales | Non | Oui | Utiliser les assets fournis par la plateforme |

---

## Optimisation des images

Chaque image de votre site affecte la vitesse de page, qui affecte le SEO et les conversions.

### Guide des formats

| Format | Idéal pour | Compression | Support navigateur |
|--------|----------|-------------|:---:|
| **WebP** | Photos, visuels — choix par défaut | Avec et sans perte | ~96 % |
| **AVIF** | Compression maximale, le plus récent | Meilleure que WebP | ~94 % |
| **JPEG** | Fallback pour les navigateurs anciens | Avec perte seulement | Universel |
| **PNG** | Transparence, captures d'écran | Sans perte | Universel |
| **SVG** | Logos, icônes, illustrations | Vectoriel (s'adapte) | Universel |

### Checklist d'optimisation

- [ ] **Servir en WebP** avec fallback JPEG/PNG (élément `<picture>` ou auto-format CDN)
- [ ] **Redimensionner à la taille d'affichage** — ne pas servir des images de 4000px dans des conteneurs de 800px
- [ ] **Compresser** — viser une qualité de 75-85 % pour les photos, quasi sans perte pour les captures
- [ ] **Lazy load** des images sous la ligne de flottaison (`loading="lazy"`)
- [ ] **Définir des dimensions explicites** — les attributs `width` et `height` évitent le décalage de mise en page (CLS)
- [ ] **Utiliser un CDN** avec auto-optimisation (Cloudflare, Vercel, Imgix, Cloudinary)
- [ ] **Ajouter du texte alt** — descriptif, pertinent pour les mots-clés, sans bourrage

### Commandes d'optimisation rapides

```bash
# Convertir en WebP (avec cwebp)
cwebp -q 80 input.png -o output.webp

# Conversion en batch avec ImageMagick
mogrify -format webp -quality 80 *.png

# Optimiser le JPEG (avec jpegoptim)
jpegoptim --max=80 --strip-all *.jpg

# Vérifier les tailles d'image sur une page
curl -s https://yoursite.com | grep -oP 'src="[^"]+\.(jpg|png|webp)"' | head -20
```

---

## Images OG et previews sociaux

L'image qui apparaît quand votre URL est partagée sur les réseaux sociaux, Slack, Discord, etc.

### Balises meta requises

```html
<meta property="og:image" content="https://yoursite.com/og/page-name.jpg" />
<meta property="og:image:width" content="1200" />
<meta property="og:image:height" content="630" />
<meta name="twitter:card" content="summary_large_image" />
<meta name="twitter:image" content="https://yoursite.com/og/page-name.jpg" />
```

### OG images dynamiques

Générer des OG images de façon programmatique pour les pages à contenu dynamique (articles de blog, profils utilisateurs) :

- **Vercel OG** (`@vercel/og`) — génère des images à l'edge en utilisant JSX
- **Satori** — convertit HTML/CSS en SVG (le moteur derrière Vercel OG)
- **Cloudinary** — overlay texte basé sur l'URL sur des images templates

**Idéal pour le SEO programmatique :** Générer des OG images uniques par page avec des templates + données dynamiques.

---

## Erreurs fréquentes

1. **Utiliser l'IA pour les captures d'UI produit** — les modèles hallucinent les interfaces ; capturez de vraies captures d'écran
2. **Sauter l'optimisation des images** — les images non optimisées sont le tueur n°1 de vitesse de page
3. **Pas d'OG image** — les liens partagés semblent cassés sans image de preview
4. **Mauvais format d'image** — toujours vérifier les specs plateforme avant de générer
5. **Images chargées en texte sans Ideogram** — la plupart des modèles IA massacrent le texte ; utilisez Ideogram ou ajoutez le texte en post
6. **Générer sans direction de style** — « photorealistic », « flat illustration », « 3D render » changent radicalement le résultat
7. **Visuels de marque incohérents** — utilisez le multi-référence Flux ou des templates de design pour la cohérence
8. **Images énormes sur les landing pages** — compresser, redimensionner, lazy load

---

## Questions spécifiques à la tâche

1. Quel type d'image vous faut-il ? (Hero de blog, visuel social, mockup, bannière, asset de marque)
2. Quelle plateforme ou quel emplacement ? (Cela détermine les dimensions)
3. Avez-vous des assets de marque à respecter ? (Couleurs, polices, logo, charte graphique)
4. Est-ce un coup unique ou un template réutilisable ?
5. Avez-vous des clés API pour des outils de génération d'images ?
6. Cela doit-il être optimisé pour la performance web ?

---

## Skills liés

- **ad-creative** : pour la créa image de pub payante, les specs pub par plateforme et la production de pubs à l'échelle
- **video** : pour la production vidéo IA et la vidéo programmatique
- **social** : pour quoi publier et la stratégie de contenu
- **cro** : pour le placement d'images et l'optimisation de conversion sur les landing pages
- **seo-audit** : pour le SEO des images (texte alt, noms de fichiers, lazy loading)
- **aso** : pour les specs de captures du store d'applis et l'optimisation
- **directory-submissions** : pour les images de galerie Product Hunt et les visuels de listing d'annuaires
