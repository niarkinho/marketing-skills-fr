---
name: ab-testing
description: "Quand l'utilisateur veut planifier, concevoir ou mettre en place un A/B test ou une expérimentation, ou construire un programme d'expérimentation growth. Aussi quand il mentionne « A/B test », « split test », « expérience », « tester ce changement », « variante de copy », « test multivarié », « hypothèse », « est-ce que je devrais tester ça », « quelle version est la meilleure », « tester deux versions », « significativité statistique », « combien de temps faut-il faire tourner ce test », « expériences growth », « vélocité d'expérimentation », « backlog d'expériences », « score ICE », « programme d'expérimentation » ou « playbook d'expériences ». À utiliser dès que quelqu'un compare deux approches et veut mesurer laquelle performe le mieux, ou veut bâtir une pratique d'expérimentation systématique. Pour la mise en place du tracking, voir analytics. Pour l'optimisation de conversion au niveau de la page, voir cro."
metadata:
  version: 2.0.0
---

# Mise en place d'un A/B test

Vous êtes un expert en expérimentation et A/B testing. Votre objectif est d'aider à concevoir des tests qui produisent des résultats statistiquement valides et actionnables.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur d'anciennes configs), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant de concevoir un test, comprendre :

1. **Contexte du test** — Qu'essayez-vous d'améliorer ? Quel changement envisagez-vous ?
2. **État actuel** — Taux de conversion de référence ? Volume de trafic actuel ?
3. **Contraintes** — Complexité technique ? Délai ? Outils disponibles ?

---

## Principes fondamentaux

### 1. Partir d'une hypothèse
- Pas juste « voyons ce qui se passe »
- Prédiction précise du résultat
- Fondée sur du raisonnement ou des données

### 2. Tester une seule chose
- Une seule variable par test
- Sinon vous ne savez pas ce qui a fonctionné

### 3. Rigueur statistique
- Pré-déterminer la taille d'échantillon
- Ne pas jeter un œil et arrêter trop tôt
- S'engager sur la méthodologie

### 4. Mesurer ce qui compte
- Métrique principale liée à la valeur business
- Métriques secondaires pour le contexte
- Métriques garde-fous pour éviter les dégâts

---

## Cadre d'hypothèse

### Structure

```
Parce que [observation/donnée],
nous pensons que [changement]
va provoquer [résultat attendu]
pour [audience].
Nous saurons que c'est vrai quand [métriques].
```

### Exemple

**Faible** : « Changer la couleur du bouton pourrait augmenter les clics. »

**Fort** : « Parce que les utilisateurs signalent des difficultés à trouver le CTA (selon les heatmaps et les retours), nous pensons qu'agrandir le bouton et utiliser une couleur contrastée augmentera les clics sur le CTA de 15 %+ pour les nouveaux visiteurs. Nous mesurerons le taux de clic entre la vue de page et le début d'inscription. »

---

## Types de test

| Type | Description | Trafic nécessaire |
|------|-------------|----------------|
| A/B | Deux versions, un seul changement | Modéré |
| A/B/n | Plusieurs variantes | Plus élevé |
| MVT | Plusieurs changements en combinaisons | Très élevé |
| Split URL | URLs différentes pour les variantes | Modéré |

---

## Taille d'échantillon

### Référence rapide

| Référence | Lift 10 % | Lift 20 % | Lift 50 % |
|----------|----------|----------|----------|
| 1 % | 150k/variante | 39k/variante | 6k/variante |
| 3 % | 47k/variante | 12k/variante | 2k/variante |
| 5 % | 27k/variante | 7k/variante | 1,2k/variante |
| 10 % | 12k/variante | 3k/variante | 550/variante |

**Calculateurs :**
- [Evan Miller](https://www.evanmiller.org/ab-testing/sample-size.html)
- [Optimizely](https://www.optimizely.com/sample-size-calculator/)

**Pour des tableaux détaillés de taille d'échantillon et les calculs de durée** : voir [references/sample-size-guide.md](references/sample-size-guide.md)

---

## Choix des métriques

### Métrique principale
- Une seule métrique qui compte le plus
- Directement liée à l'hypothèse
- Celle qui servira à conclure le test

### Métriques secondaires
- Aident à interpréter la métrique principale
- Expliquent pourquoi/comment le changement a fonctionné

### Métriques garde-fous
- Des choses qui ne doivent pas empirer
- Arrêter le test si nettement négatif

### Exemple : test d'une page de pricing
- **Principale** : taux de sélection d'une offre
- **Secondaires** : temps passé sur la page, répartition des offres
- **Garde-fou** : tickets de support, taux de remboursement

---

## Concevoir les variantes

### Quoi faire varier

| Catégorie | Exemples |
|----------|----------|
| Titres/Copy | Angle du message, proposition de valeur, précision, ton |
| Design visuel | Mise en page, couleur, images, hiérarchie |
| CTA | Texte du bouton, taille, emplacement, nombre |
| Contenu | Informations incluses, ordre, quantité, preuve sociale |

### Bonnes pratiques
- Un seul changement, significatif
- Assez marqué pour faire la différence
- Fidèle à l'hypothèse

---

## Répartition du trafic

| Approche | Répartition | Quand l'utiliser |
|----------|-------|-------------|
| Standard | 50/50 | Par défaut pour un A/B |
| Conservatrice | 90/10, 80/20 | Limiter le risque d'une mauvaise variante |
| Progressive (ramping) | Démarrer petit, augmenter | Atténuation du risque technique |

**À considérer :**
- Cohérence : les utilisateurs voient la même variante à leur retour
- Exposition équilibrée selon l'heure du jour/de la semaine

---

## Mise en œuvre

### Côté client
- Du JavaScript modifie la page après chargement
- Rapide à mettre en place, peut causer du flicker
- Outils : PostHog, Optimizely, VWO

### Côté serveur
- La variante est déterminée avant le rendu
- Pas de flicker, demande du travail de dev
- Outils : PostHog, LaunchDarkly, Split

---

## Faire tourner le test

### Checklist avant lancement
- [ ] Hypothèse documentée
- [ ] Métrique principale définie
- [ ] Taille d'échantillon calculée
- [ ] Variantes implémentées correctement
- [ ] Tracking vérifié
- [ ] QA réalisée sur toutes les variantes

### Pendant le test

**À FAIRE :**
- Surveiller les problèmes techniques
- Vérifier la qualité des segments
- Documenter les facteurs externes

**À éviter :**
- Jeter un œil aux résultats et arrêter trop tôt
- Modifier les variantes
- Ajouter du trafic depuis de nouvelles sources

### Le problème du peeking
Regarder les résultats avant d'atteindre la taille d'échantillon puis arrêter trop tôt mène à des faux positifs et à de mauvaises décisions. Engagez-vous à l'avance sur la taille d'échantillon et faites confiance au processus.

---

## Analyser les résultats

### Significativité statistique
- 95 % de confiance = p-value < 0,05
- Signifie < 5 % de chance que le résultat soit dû au hasard
- Pas une garantie — juste un seuil

### Checklist d'analyse

1. **Taille d'échantillon atteinte ?** Sinon, le résultat est préliminaire
2. **Statistiquement significatif ?** Vérifier les intervalles de confiance
3. **Taille d'effet significative ?** Comparer au MDE, projeter l'impact
4. **Métriques secondaires cohérentes ?** Appuient-elles la principale ?
5. **Inquiétudes sur les garde-fous ?** Quelque chose a-t-il empiré ?
6. **Différences par segment ?** Mobile vs. desktop ? Nouveaux vs. récurrents ?

### Interpréter les résultats

| Résultat | Conclusion |
|--------|------------|
| Gagnant significatif | Implémenter la variante |
| Perdant significatif | Garder le contrôle, comprendre pourquoi |
| Pas de différence significative | Plus de trafic ou test plus audacieux |
| Signaux mitigés | Creuser, peut-être segmenter |

---

## Documentation

Documenter chaque test avec :
- Hypothèse
- Variantes (avec captures d'écran)
- Résultats (échantillon, métriques, significativité)
- Décision et enseignements

**Pour les templates** : voir [references/test-templates.md](references/test-templates.md)

---

## Programme d'expérimentation growth

Les tests isolés ont de la valeur. Un programme d'expérimentation continu est un actif cumulatif. Cette section explique comment faire tourner des expériences comme un moteur de croissance permanent, et pas seulement des tests ponctuels.

### La boucle d'expérimentation

```
1. Générer des hypothèses (à partir de données, recherche, concurrents, retours clients)
2. Prioriser avec le scoring ICE
3. Concevoir et faire tourner le test
4. Analyser les résultats avec rigueur statistique
5. Promouvoir les gagnants dans un playbook
6. Générer de nouvelles hypothèses à partir des enseignements
→ Recommencer
```

### Génération d'hypothèses

Alimentez votre backlog d'expériences depuis plusieurs sources :

| Source | Quoi chercher |
|--------|-----------------|
| Analytics | Points de décrochage, pages à faible conversion, segments sous-performants |
| Recherche client | Points de douleur, confusion, attentes non satisfaites |
| Analyse concurrentielle | Fonctionnalités, messages ou patterns UX qu'ils utilisent et pas vous |
| Tickets de support | Questions ou plaintes récurrentes sur les parcours de conversion |
| Heatmaps/enregistrements | Là où les utilisateurs hésitent, rage-cliquent ou abandonnent |
| Expériences passées | Les tests « perdant significatif » révèlent souvent de nouveaux angles à essayer |

### Priorisation ICE

Notez chaque hypothèse de 1 à 10 sur trois dimensions :

| Dimension | Question |
|-----------|----------|
| **Impact** | Si ça marche, de combien ça fera bouger la métrique principale ? |
| **Confidence (confiance)** | À quel point sommes-nous sûrs que ça marchera ? (Sur la base de données, pas du feeling.) |
| **Ease (facilité)** | À quelle vitesse et à quel coût peut-on livrer et mesurer ça ? |

**Score ICE** = (Impact + Confiance + Facilité) / 3

Faites tourner d'abord les expériences au score le plus élevé. Re-notez chaque mois à mesure que le contexte change.

### Vélocité d'expérimentation

Suivez votre cadence d'expérimentation comme un indicateur avancé de croissance :

| Métrique | Cible |
|--------|--------|
| Expériences lancées par mois | 4-8 pour la plupart des équipes |
| Taux de réussite (win rate) | 20-30 % est courant pour les programmes matures (un taux durablement supérieur peut indiquer des hypothèses trop prudentes) |
| Durée moyenne d'un test | 2-4 semaines |
| Profondeur du backlog | 20+ hypothèses en file |
| Lift cumulé | Gains composés de tous les gagnants |

### Le playbook d'expériences

Quand un test gagne, ne vous contentez pas de l'implémenter — documentez le pattern :

```
## [Nom de l'expérience]
**Date** : [date]
**Hypothèse** : [l'hypothèse]
**Taille d'échantillon** : [n par variante]
**Résultat** : [gagnant/perdant/non concluant] — [métrique principale] a changé de [X %] (IC 95 % : [plage], p=[valeur])
**Garde-fous** : [métriques garde-fous et leurs résultats]
**Écarts par segment** : [différences notables par appareil, segment ou cohorte]
**Pourquoi ça a marché/échoué** : [analyse]
**Pattern** : [l'enseignement réutilisable — ex. « la preuve sociale près des CTA de pricing augmente la sélection d'offre »]
**À appliquer à** : [autres pages/parcours où ce pattern pourrait fonctionner]
**Statut** : [implémenté / mis en pause / test de suivi nécessaire]
```

Au fil du temps, votre playbook devient une bibliothèque de patterns de croissance éprouvés, spécifiques à votre produit et à votre audience.

### Cadence d'expérimentation

**Hebdomadaire (30 min)** : passer en revue les expériences en cours pour détecter les problèmes techniques et les métriques garde-fous. Ne pas conclure les gagnants trop tôt — mais arrêter les tests dont les garde-fous sont nettement négatifs.

**Bimensuel** : conclure les expériences terminées. Analyser les résultats, mettre à jour le playbook, lancer l'expérience suivante du backlog.

**Mensuel (1 heure)** : passer en revue la vélocité d'expérimentation, le win rate, le lift cumulé. Réalimenter le backlog d'hypothèses. Re-prioriser avec ICE.

**Trimestriel** : auditer le playbook. Quels patterns ont été appliqués largement ? Quels patterns gagnants n'ont pas encore été déployés à grande échelle ? Quelles zones du funnel sont sous-testées ?

---

## Erreurs courantes

### Conception du test
- Tester un changement trop petit (indétectable)
- Tester trop de choses (impossible d'isoler)
- Pas d'hypothèse claire

### Exécution
- Arrêter trop tôt
- Modifier des choses en cours de test
- Ne pas vérifier l'implémentation

### Analyse
- Ignorer les intervalles de confiance
- Cherry-picking de segments
- Sur-interpréter des résultats non concluants

---

## Questions spécifiques à la tâche

1. Quel est votre taux de conversion actuel ?
2. Combien de trafic reçoit cette page ?
3. Quel changement envisagez-vous et pourquoi ?
4. Quelle est la plus petite amélioration qui vaille la peine d'être détectée ?
5. Quels outils avez-vous pour tester ?
6. Avez-vous déjà testé cette zone auparavant ?

---

## Skills associés

- **cro** : pour générer des idées de test à partir des principes de CRO
- **analytics** : pour mettre en place la mesure du test
- **copywriting** : pour créer le copy des variantes
