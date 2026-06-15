# Guide de prompting vidéo IA

Comment écrire des prompts efficaces pour les modèles de génération vidéo IA (Veo, Runway, Kling, Pika).

---

## Structure d'un prompt

Un prompt vidéo solide suit cette formule :

```
[Sujet] + [Action] + [Mouvement de caméra] + [Style visuel] + [Lumière/ambiance] + [Specs techniques]
```

### Exemples de prompts par cas d'usage

**Plan hero produit :**
```
A sleek laptop on a minimal white desk, screen glowing with a dashboard UI,
camera slowly orbits 180 degrees around the desk,
soft volumetric lighting from the left, shallow depth of field,
cinematic commercial aesthetic, 4K
```

**B-roll lifestyle :**
```
A woman in a modern co-working space smiling while looking at her phone,
natural window light, candid documentary feel,
camera handheld with subtle movement, warm color grading
```

**Abstrait/marque :**
```
Flowing liquid gold particles forming the shape of a network graph,
dark background, particles catch light as they move,
slow-motion macro photography style, dramatic rim lighting
```

**Scène explicative SaaS :**
```
An overhead shot of a team around a conference table pointing at charts,
camera slowly pushes in, bright modern office,
clean corporate style, even lighting, 1080p
```

---

## Vocabulaire des mouvements de caméra

Utilisez ces termes — les modèles vidéo les comprennent :

| Terme | Effet |
|------|--------|
| **Static** | Caméra fixe, aucun mouvement |
| **Pan left/right** | La caméra pivote horizontalement |
| **Tilt up/down** | La caméra pivote verticalement |
| **Dolly in/out** | La caméra se rapproche/s'éloigne du sujet |
| **Orbit** | La caméra tourne autour du sujet |
| **Tracking shot** | La caméra suit un sujet en mouvement |
| **Crane/aerial** | La caméra monte ou descend |
| **Handheld** | Léger tremblement, ambiance documentaire |
| **Zoom** | Zoom optique (différent du dolly) |
| **Slow push** | Dolly in progressif — crée tension/focus |

---

## Mots-clés de style

### Cinématique
- "cinematic color grading"
- "anamorphic lens flare"
- "shallow depth of field"
- "film grain"
- "35mm film"

### Commercial/Corporate
- "clean commercial lighting"
- "bright and airy"
- "professional corporate aesthetic"
- "even, diffused lighting"

### Documentaire
- "handheld documentary style"
- "natural lighting"
- "candid, unposed"
- "observational camera"

### Social/Tendance
- "vertical 9:16"
- "fast-paced cuts"
- "bold text overlays"
- "high contrast, saturated colors"

---

## Conseils spécifiques par modèle

### Veo (Google)

- Excelle en photoréalisme et scènes complexes
- Prend en charge la génération audio synchronisée à la vidéo
- Donne son meilleur avec des prompts détaillés et descriptifs
- Précisez « high resolution » ou « 1080p » pour la meilleure qualité
- Peut gérer plusieurs sujets et transitions de scène

### Runway Gen-4

- Fort contrôle du mouvement — précisez les mouvements de caméra avec exactitude
- Meilleure cohérence temporelle (les sujets restent cohérents entre les frames)
- Utilisez le motion brush pour animer une zone précise
- L'image-to-video fonctionne bien — fournissez une frame de référence
- Gardez les prompts sous 100 mots pour de meilleurs résultats

### Kling

- Peut générer jusqu'à 2 minutes (bien plus long que les autres)
- Idéal pour les séquences narratives plus longues
- Plus abordable pour la génération en volume
- La qualité baisse légèrement sur les durées plus longues
- Donne son meilleur avec des scènes plus simples et moins de sujets

### Pika

- Temps de génération le plus rapide (sous 2 minutes)
- Idéal pour les itérations rapides et l'expérimentation
- Le mode effets ajoute du mouvement aux images fixes
- Idéal pour les clips courts (5-15 secondes)
- Moins de contrôle sur le mouvement de caméra

---

## Erreurs de prompt fréquentes

| Erreur | Pourquoi ça échoue | Correctif |
|---------|-------------|-----|
| "A person using our app" | Trop vague, aucun détail visuel | Décrire la personne, le décor, la lumière, la caméra |
| Inclure du texte/des logos | L'IA ne sait pas rendre du texte lisible | Ajouter le texte en post via Hyperframes/CapCut |
| "Make it viral" | Pas une instruction visuelle | Décrire le style visuel voulu |
| Prompts extrêmement longs (200+ mots) | Les modèles perdent le focus | Rester à 50-100 mots, être précis |
| Aucune direction de caméra | Caméra aléatoire/statique | Toujours préciser le mouvement ou « static » |
| "Realistic" seul | Pas assez précis | "Photorealistic, natural lighting, shot on RED camera" |

---

## Workflow de prompting

1. **Référence d'abord** — trouvez une vraie vidéo qui ressemble à ce que vous voulez
2. **Décrivez-la** — décomposez : sujet, action, caméra, style, ambiance
3. **Générez 3-4 variantes** — même concept, angles ou styles différents
4. **Itérez sur la meilleure** — affinez le prompt selon les résultats
5. **Composez** — combinez les rushes IA avec du texte/overlays programmatiques

---

## Formats d'image

Toujours préciser dans votre prompt ou dans les réglages de génération :

| Plateforme | Ratio | Résolution |
|----------|-------|-----------|
| YouTube | 16:9 | 1920x1080 ou 3840x2160 |
| TikTok/Reels/Shorts | 9:16 | 1080x1920 |
| Instagram Feed | 1:1 ou 4:5 | 1080x1080 ou 1080x1350 |
| Hero de site web | 16:9 | 1920x1080 |
| LinkedIn | 16:9 ou 1:1 | 1920x1080 |

---

## Optimisation des coûts

- **Itérez en basse résolution** — n'upscalez que la version finale
- **Utilisez Kling pour les brouillons** — le moins cher à la seconde, basculez sur Veo/Runway pour les finaux
- **Image-to-video** — fournir une frame de référence économise des crédits de génération et donne de meilleurs résultats
- **Groupez les prompts similaires** — les modèles offrent souvent des remises au volume
- **Mettez en cache et réutilisez** — les clips B-roll peuvent être réutilisés sur plusieurs vidéos
