# Guide de taille d'échantillon

Référence pour calculer les tailles d'échantillon et la durée d'un test.

## Sommaire
- Fondamentaux de la taille d'échantillon (entrées requises, ce qu'elles signifient)
- Tableaux de référence rapide de taille d'échantillon
- Calculateur de durée (formule, exemples, règles de durée minimale, lignes directrices de durée maximale)
- Calculateurs en ligne
- Ajustement pour plusieurs variantes
- Erreurs courantes de taille d'échantillon
- Quand les besoins en taille d'échantillon sont trop élevés
- Tests séquentiels
- Cadre de décision rapide

## Fondamentaux de la taille d'échantillon

### Entrées requises

1. **Taux de conversion de référence** : votre taux actuel
2. **Effet minimal détectable (MDE)** : le plus petit changement qui vaille la peine d'être détecté
3. **Niveau de significativité statistique** : généralement 95 % (α = 0,05)
4. **Puissance statistique** : généralement 80 % (β = 0,20)

### Ce qu'elles signifient

**Taux de conversion de référence** : si votre page convertit à 5 %, c'est votre référence.

**MDE (effet minimal détectable)** : la plus petite amélioration que vous tenez à détecter. À définir selon :
- L'impact business (un lift de 5 % est-il significatif ?)
- Le coût d'implémentation (ça vaut l'effort ?)
- Des attentes réalistes (qu'ont montré les tests passés ?)

**Significativité statistique (95 %)** : signifie qu'il y a moins de 5 % de chance que la différence observée soit due au hasard.

**Puissance statistique (80 %)** : signifie que s'il existe un effet réel de taille MDE, vous avez 80 % de chance de le détecter.

---

## Tableaux de référence rapide de taille d'échantillon

### Taux de conversion : 1 %

| Lift à détecter | Échantillon par variante | Échantillon total |
|----------------|-------------------|--------------|
| 5 % (1 % → 1,05 %) | 1 500 000 | 3 000 000 |
| 10 % (1 % → 1,1 %) | 380 000 | 760 000 |
| 20 % (1 % → 1,2 %) | 97 000 | 194 000 |
| 50 % (1 % → 1,5 %) | 16 000 | 32 000 |
| 100 % (1 % → 2 %) | 4 200 | 8 400 |

### Taux de conversion : 3 %

| Lift à détecter | Échantillon par variante | Échantillon total |
|----------------|-------------------|--------------|
| 5 % (3 % → 3,15 %) | 480 000 | 960 000 |
| 10 % (3 % → 3,3 %) | 120 000 | 240 000 |
| 20 % (3 % → 3,6 %) | 31 000 | 62 000 |
| 50 % (3 % → 4,5 %) | 5 200 | 10 400 |
| 100 % (3 % → 6 %) | 1 400 | 2 800 |

### Taux de conversion : 5 %

| Lift à détecter | Échantillon par variante | Échantillon total |
|----------------|-------------------|--------------|
| 5 % (5 % → 5,25 %) | 280 000 | 560 000 |
| 10 % (5 % → 5,5 %) | 72 000 | 144 000 |
| 20 % (5 % → 6 %) | 18 000 | 36 000 |
| 50 % (5 % → 7,5 %) | 3 100 | 6 200 |
| 100 % (5 % → 10 %) | 810 | 1 620 |

### Taux de conversion : 10 %

| Lift à détecter | Échantillon par variante | Échantillon total |
|----------------|-------------------|--------------|
| 5 % (10 % → 10,5 %) | 130 000 | 260 000 |
| 10 % (10 % → 11 %) | 34 000 | 68 000 |
| 20 % (10 % → 12 %) | 8 700 | 17 400 |
| 50 % (10 % → 15 %) | 1 500 | 3 000 |
| 100 % (10 % → 20 %) | 400 | 800 |

### Taux de conversion : 20 %

| Lift à détecter | Échantillon par variante | Échantillon total |
|----------------|-------------------|--------------|
| 5 % (20 % → 21 %) | 60 000 | 120 000 |
| 10 % (20 % → 22 %) | 16 000 | 32 000 |
| 20 % (20 % → 24 %) | 4 000 | 8 000 |
| 50 % (20 % → 30 %) | 700 | 1 400 |
| 100 % (20 % → 40 %) | 200 | 400 |

---

## Calculateur de durée

### Formule

```
Durée (jours) = (Échantillon par variante × Nombre de variantes) / (Trafic quotidien × % exposé)
```

### Exemples

**Scénario 1 : page à fort trafic**
- Besoin : 10 000 par variante (2 variantes = 20 000 au total)
- Trafic quotidien : 5 000 visiteurs
- 100 % exposés au test
- Durée : 20 000 / 5 000 = **4 jours**

**Scénario 2 : page à trafic moyen**
- Besoin : 30 000 par variante (60 000 au total)
- Trafic quotidien : 2 000 visiteurs
- 100 % exposés
- Durée : 60 000 / 2 000 = **30 jours**

**Scénario 3 : faible trafic avec exposition partielle**
- Besoin : 15 000 par variante (30 000 au total)
- Trafic quotidien : 500 visiteurs
- 50 % exposés au test
- Quotidien effectif : 250
- Durée : 30 000 / 250 = **120 jours** (trop long !)

### Règles de durée minimale

Même avec une taille d'échantillon suffisante, faites tourner les tests au moins :
- **1 semaine complète** : pour capturer la variation jour-de-semaine
- **2 cycles d'activité** : si B2B (patterns semaine vs. week-end)
- **Au-delà des jours de paie** : si e-commerce (début/fin de mois)

### Lignes directrices de durée maximale

Évitez de faire tourner des tests plus de 4-8 semaines :
- Les effets de nouveauté s'estompent
- Des facteurs externes interviennent
- Coût d'opportunité des autres tests

---

## Calculateurs en ligne

### Outils recommandés

**Calculateur d'Evan Miller**
https://www.evanmiller.org/ab-testing/sample-size.html
- Interface simple
- À mettre en favori

**Calculateur d'Optimizely**
https://www.optimizely.com/sample-size-calculator/
- Langage accessible aux non-experts
- Estimations de durée

**Calculateur d'AB Test Guide**
https://www.abtestguide.com/calc/
- Inclut une option bayésienne
- Plusieurs types de test

**Calculateur de durée de VWO**
https://vwo.com/tools/ab-test-duration-calculator/
- Centré sur la durée
- Pratique pour la planification

---

## Ajustement pour plusieurs variantes

Avec plus de 2 variantes (tests A/B/n), vous avez besoin de plus d'échantillon :

| Variantes | Multiplicateur |
|----------|------------|
| 2 (A/B) | 1x |
| 3 (A/B/C) | ~1,5x |
| 4 (A/B/C/D) | ~2x |
| 5+ | Envisager de réduire le nombre de variantes |

**Pourquoi ?** Plus de comparaisons augmente le risque de faux positifs. Vous comparez :
- A vs B
- A vs C
- B vs C (parfois)

Appliquez la correction de Bonferroni ou utilisez des outils qui gèrent ça automatiquement.

---

## Erreurs courantes de taille d'échantillon

### 1. Tests sous-puissants
**Problème** : pas assez d'échantillon pour détecter des effets réalistes
**Correctif** : être réaliste sur le MDE, obtenir plus de trafic, ou ne pas tester

### 2. Tests sur-puissants
**Problème** : attendre la taille d'échantillon alors que vous avez déjà la significativité
**Correctif** : c'est en fait acceptable — vous vous êtes engagé sur la taille d'échantillon, honorez-la

### 3. Mauvais taux de référence
**Problème** : utiliser le mauvais taux de conversion pour le calcul
**Correctif** : utiliser la métrique et la page spécifiques, pas les moyennes du site entier

### 4. Ignorer les segments
**Problème** : calculer pour tout le trafic, puis analyser des segments
**Correctif** : si vous prévoyez une analyse par segment, calculez l'échantillon pour le plus petit segment

### 5. Tester trop de choses
**Problème** : diviser le trafic en trop de parts
**Correctif** : prioriser sans pitié, faire tourner moins de tests en parallèle

---

## Quand les besoins en taille d'échantillon sont trop élevés

Options quand vous ne pouvez pas obtenir assez de trafic :

1. **Augmenter le MDE** : accepter de ne détecter que des effets plus grands (lift de 20 %+)
2. **Baisser la confiance** : utiliser 90 % au lieu de 95 % (risqué, à documenter)
3. **Réduire les variantes** : tester uniquement la variante la plus prometteuse
4. **Combiner le trafic** : tester sur plusieurs pages similaires
5. **Tester plus en amont** : tester plus tôt dans le funnel où le trafic est plus élevé
6. **Ne pas tester** : décider sur la base de données qualitatives à la place
7. **Test plus long** : accepter une durée plus longue (semaines/mois)

---

## Tests séquentiels

Si vous devez vérifier les résultats avant d'atteindre la taille d'échantillon :

### De quoi s'agit-il ?
Méthode statistique qui s'ajuste aux regards multiples sur les données.

### Quand l'utiliser
- Changements à fort risque
- Besoin d'arrêter tôt les mauvaises variantes
- Décisions urgentes

### Outils qui le supportent
- Optimizely (Stats Accelerator)
- VWO (SmartStats)
- PostHog (approche bayésienne)

### Compromis
- Plus de flexibilité pour arrêter tôt
- Besoin en taille d'échantillon légèrement plus grand
- Analyse plus complexe

---

## Cadre de décision rapide

### Puis-je faire tourner ce test ?

```
Trafic quotidien sur la page : _____
Taux de conversion de référence : _____
MDE qui m'intéresse : _____

Échantillon nécessaire par variante : _____ (d'après les tableaux ci-dessus)
Jours à faire tourner : Échantillon / Trafic quotidien = _____

Si jours > 60 : envisager des alternatives
Si jours > 30 : acceptable pour des tests à fort impact
Si jours < 14 : probablement faisable
Si jours < 7 : facile à faire tourner, envisager de le prolonger quand même
```
