# Guide de prompting image IA

Comment écrire des prompts efficaces pour les modèles de génération d'images IA (Gemini/Nano Banana, Flux, Ideogram, DALL-E, Midjourney).

---

## Structure d'un prompt

Un prompt image solide suit cette formule :

```
[Sujet] + [Décor/contexte] + [Style visuel] + [Lumière] + [Composition] + [Specs techniques]
```

### Exemples de prompts par cas d'usage

**Hero de blog — produit SaaS :**
```
A clean workspace with a laptop displaying a colorful analytics dashboard,
minimalist desk with a coffee cup and notebook,
bright natural window lighting from the right,
shallow depth of field, commercial photography style,
1200x630, high resolution
```

**Visuel réseaux sociaux — annonce :**
```
Abstract flowing gradient in deep purple and electric blue,
geometric shapes forming a network pattern,
dramatic rim lighting on edges,
modern tech aesthetic, clean and minimal,
1080x1080, vibrant colors
```

**Plan lifestyle produit :**
```
A person in a modern office smiling while looking at a tablet,
showing a project management interface on screen,
warm candid photography, natural lighting,
medium shot, shallow depth of field, editorial style
```

**Bannière de profil — professionnelle :**
```
Wide panoramic abstract background in navy blue and teal,
subtle geometric grid pattern with soft gradient,
clean corporate aesthetic, muted lighting,
1584x396, no text, space for logo overlay on left third
```

**Listing d'annuaire — Product Hunt :**
```
Product screenshot on a clean gradient background,
soft shadow underneath, slight 3D perspective tilt,
modern SaaS product presentation style,
1270x760, bright and professional
```

---

## Mots-clés de style

### Photoréaliste
- "commercial photography"
- "shot on Canon EOS R5"
- "editorial style"
- "natural lighting"
- "shallow depth of field"

### Clean/Corporate
- "clean modern aesthetic"
- "minimal design"
- "professional corporate style"
- "bright and airy"
- "white background"

### Illustratif
- "flat vector illustration"
- "isometric 3D render"
- "hand-drawn sketch style"
- "watercolor illustration"
- "line art"

### Abstrait/Marque
- "flowing gradient"
- "geometric pattern"
- "abstract data visualization"
- "particle effects"
- "holographic iridescent"

### Tech/SaaS
- "dark mode UI aesthetic"
- "neon accent lighting"
- "glassmorphism"
- "futuristic minimal"
- "developer-focused"

---

## Mots-clés de lumière

| Terme | Effet | Idéal pour |
|------|--------|----------|
| **Natural light** | Ambiance chaude, organique | Lifestyle, éditorial |
| **Studio lighting** | Uniforme, maîtrisée | Plans produit |
| **Rim lighting** | Reflets de contour, dramatique | Hero images, abstrait |
| **Soft directional** | Ombres douces, dimensionnel | En-têtes de blog |
| **Volumetric** | Rayons de lumière, atmosphérique | Dramatique, cinématique |
| **Flat/even** | Sans ombre, clean | Icônes, schémas |
| **Golden hour** | Tons orangés chauds | Lifestyle, extérieur |
| **High key** | Lumineux, ombres minimales | Clean, corporate |

---

## Mots-clés de composition

| Terme | Effet | Idéal pour |
|------|--------|----------|
| **Rule of thirds** | Sujet décentré | Éditorial, lifestyle |
| **Centered** | Sujet au milieu | Plans produit, icônes |
| **Wide/panoramic** | Vue large | Bannières, en-têtes |
| **Close-up/macro** | Focus sur le détail | Texture, détail produit |
| **Bird's eye/overhead** | Vue de dessus | Setups de bureau, flat lays |
| **Negative space** | Place pour overlay texte | En-têtes de blog, bannières |
| **Symmetrical** | Équilibré, formel | Corporate, luxe |

---

## Conseils spécifiques par modèle

### Gemini Image (Google)

- Le meilleur tout-terrain pour les images marketing — bonne qualité, coût raisonnable
- Prend en charge l'**édition d'image** — téléversez une image existante et décrivez les changements
- Rendu de texte correct — peut gérer de courts titres
- Précisez « high resolution » pour le meilleur résultat
- Fonctionne bien avec des prompts détaillés et descriptifs
- Même API que la génération de texte — facile à intégrer

### Flux (Black Forest Labs)

- La **référence multi-images** est la fonctionnalité phare — téléversez des captures produit, assets de marque ou références de style
- Le meilleur pour la **cohérence de marque** sur un ensemble d'images
- Utilisez Flux Pro pour les assets finaux, Flux Dev pour l'itération rapide
- Flux Klein pour la génération en batch à fort volume (le moins cher)
- Le transfert de style via images de référence > mots-clés de style dans le prompt
- Les prompts peuvent être plus courts que pour d'autres modèles — les références font le gros du travail

### Ideogram

- **Meilleur rendu de texte** de tous les modèles (précision à la pointe du secteur)
- À utiliser quand vous avez besoin de titres, taglines ou noms de marque dans l'image
- Système de référence de style (jusqu'à 3 images) pour la cohérence de marque
- Prend en charge l'auto-amélioration « Magic Prompt »
- Gardez les demandes de texte simples — 3-5 mots max pour la fiabilité
- Idéal pour les visuels sociaux et bannières qui ont besoin de texte intégré

### GPT Image (OpenAI)

- Modèles actuels : `gpt-image-1` et variantes (DALL-E 3 est déprécié)
- Intégré à ChatGPT — génération d'images conversationnelle
- Bon pour suivre des prompts détaillés
- Rendu de texte correct (derrière Ideogram, comparable à Gemini)
- Réécriture automatique du prompt — peut dévier de la demande exacte
- Idéal pour les coups uniques rapides via l'interface ChatGPT
- L'API donne plus de contrôle que l'interface ChatGPT

### Midjourney

- La plus haute qualité esthétique pour les images artistiques/éditoriales
- Pas d'API officielle — basé sur Discord ou interface web
- **Pas adapté aux agents** — à utiliser pour l'exploration créative manuelle uniquement
- Flags de style : `--style raw` pour moins stylisé, `--ar 16:9` pour le format d'image
- Idéal pour les hero images où la pure qualité visuelle prime
- V6+ a amélioré le rendu de texte mais reste peu fiable

---

## Erreurs de prompt fréquentes

| Erreur | Pourquoi ça échoue | Correctif |
|---------|-------------|-----|
| "A professional image" | Aucun détail visuel | Décrire sujet, décor, style, lumière |
| Long paragraphe de texte dans l'image | Les modèles ne savent pas rendre des paragraphes | 3-5 mots max ; ajouter le texte en post |
| "Make it look good" | Pas actionnable | Préciser le style : "commercial photography, bright" |
| Prompts de 200+ mots | Les modèles perdent le focus | 40-80 mots, le précis plutôt que l'exhaustif |
| Aucun format d'image | Taille de sortie aléatoire | Toujours préciser les dimensions ou le ratio |
| "Logo in bottom right" | Placement peu fiable | Ajouter les logos en post-traitement |
| "Make it viral" | Pas une instruction visuelle | Décrire l'esthétique voulue |
| Demander des captures d'UI | L'IA hallucine les interfaces | Capturer de vraies captures à la place |

---

## Workflow de génération en batch

Quand vous avez besoin de plusieurs images au style cohérent (ex. une série de blog ou une campagne sociale) :

1. **Générer 3-4 images de test** avec différents prompts de style
2. **Choisir le style gagnant** selon l'adéquation à la marque
3. **Sauvegarder le prompt exact** comme template
4. **Utiliser le multi-référence Flux** — téléverser l'image gagnante comme référence de style
5. **Générer en batch** des variantes au même style, sujets différents
6. **Post-traiter** — ajouter overlays texte, logos, recadrer aux tailles plateforme

---

## Aide-mémoire des formats d'image

| Cas d'usage | Ratio | Pixels | Notes |
|----------|-------|--------|-------|
| Hero de blog / OG image | 1.91:1 | 1200x630 | Standard web universel |
| Hero pleine largeur | 16:9 | 1920x1080 | En-têtes de site web |
| Instagram Feed | 1:1 | 1080x1080 | Carré |
| Instagram Feed (haut) | 4:5 | 1080x1350 | Plus de surface écran |
| Stories / Reels | 9:16 | 1080x1920 | Plein écran vertical |
| Couverture LinkedIn | 4:1 | 1584x396 | Profil personnel |
| En-tête Twitter/X | 3:1 | 1500x500 | Bannière de profil |
| Galerie Product Hunt | 5:3 | 1270x760 | Page de lancement |
| Aperçu social GitHub | 2:1 | 1280x640 | Link card de repo |

---

## Optimisation des coûts

- **Itérez d'abord en basse qualité** — utilisez Flux Dev ou Gemini Flash pour les brouillons, montez en gamme pour les finaux
- **Utilisez les références plutôt que de longs prompts** — le multi-référence Flux produit des résultats plus cohérents avec moins de reprises
- **Groupez les demandes similaires** — générez tous les en-têtes de blog en une session avec le même style
- **Mettez en cache et réutilisez** — les fonds abstraits, motifs et textures peuvent être réutilisés sur plusieurs images
- **Post-traitez plutôt que de re-générer** — recadrez, ajoutez du texte en overlay et ajustez la couleur dans le code plutôt que de générer de nouvelles images
