# Templates d'A/B test

Templates pour planifier, documenter et analyser des expériences.

## Sommaire
- Template de plan de test
- Template de documentation des résultats
- Template d'entrée de référentiel de tests
- Template de brief de test rapide
- Template de mise à jour aux parties prenantes
- Scorecard de priorisation des expériences
- Template de banque d'hypothèses

## Template de plan de test

```markdown
# A/B Test : [Nom]

## Vue d'ensemble
- **Responsable** : [Nom]
- **ID du test** : [ID dans l'outil de testing]
- **Page/Fonctionnalité** : [Ce qui est testé]
- **Dates prévues** : [Début] - [Fin]

## Hypothèse

Parce que [observation/donnée],
nous pensons que [changement]
va provoquer [résultat attendu]
pour [audience].
Nous saurons que c'est vrai quand [métriques].

## Conception du test

| Élément | Détails |
|---------|---------|
| Type de test | A/B / A/B/n / MVT |
| Durée | X semaines |
| Taille d'échantillon | X par variante |
| Répartition du trafic | 50/50 |
| Outil | [Nom de l'outil] |
| Implémentation | Côté client / Côté serveur |

## Variantes

### Contrôle (A)
[Capture d'écran]
- Expérience actuelle
- [Détails clés sur l'état actuel]

### Variante (B)
[Capture d'écran ou maquette]
- [Changement précis #1]
- [Changement précis #2]
- Justification : [Pourquoi on pense que ça va gagner]

## Métriques

### Principale
- **Métrique** : [nom de la métrique]
- **Définition** : [comment elle est calculée]
- **Référence actuelle** : [X %]
- **Effet minimal détectable** : [X %]

### Secondaires
- [Métrique 1] : [ce qu'elle nous dit]
- [Métrique 2] : [ce qu'elle nous dit]
- [Métrique 3] : [ce qu'elle nous dit]

### Garde-fous
- [Métrique qui ne doit pas empirer]
- [Autre métrique de sécurité]

## Plan d'analyse par segment
- Mobile vs. desktop
- Nouveaux vs. visiteurs récurrents
- Source de trafic
- [Autres segments pertinents]

## Critères de réussite
- Gagnant : [La métrique principale s'améliore de X % avec 95 % de confiance]
- Perdant : [La métrique principale baisse significativement]
- Non concluant : [Ce qu'on fera s'il n'y a pas de résultat significatif]

## Checklist avant lancement
- [ ] Hypothèse documentée et revue
- [ ] Métrique principale définie et traçable
- [ ] Taille d'échantillon calculée
- [ ] Durée du test estimée
- [ ] Variantes implémentées correctement
- [ ] Tracking vérifié dans toutes les variantes
- [ ] QA réalisée sur toutes les variantes
- [ ] Parties prenantes informées
- [ ] Créneau calendrier réservé pour la date d'analyse
```

---

## Template de documentation des résultats

```markdown
# Résultats d'A/B test : [Nom]

## Synthèse
| Élément | Valeur |
|---------|-------|
| ID du test | [ID] |
| Dates | [Début] - [Fin] |
| Durée | X jours |
| Résultat | Gagnant / Perdant / Non concluant |
| Décision | [Ce qu'on fait] |

## Hypothèse (rappel)
[Copier depuis le plan de test]

## Résultats

### Taille d'échantillon
| Variante | Cible | Réel | % de la cible |
|---------|--------|--------|-------------|
| Contrôle | X | Y | Z % |
| Variante | X | Y | Z % |

### Métrique principale : [Nom de la métrique]
| Variante | Valeur | IC 95 % | vs. Contrôle |
|---------|-------|--------|-------------|
| Contrôle | X % | [X %, Y %] | — |
| Variante | X % | [X %, Y %] | +X % |

**Significativité statistique** : p = X,XX (95 % = sig / non sig)
**Significativité pratique** : [Ce lift est-il significatif pour le business ?]

### Métriques secondaires

| Métrique | Contrôle | Variante | Variation | Significatif ? |
|--------|---------|---------|--------|--------------|
| [Métrique 1] | X | Y | +Z % | Oui/Non |
| [Métrique 2] | X | Y | +Z % | Oui/Non |

### Métriques garde-fous

| Métrique | Contrôle | Variante | Variation | Inquiétude ? |
|--------|---------|---------|--------|----------|
| [Métrique 1] | X | Y | +Z % | Oui/Non |

### Analyse par segment

**Mobile vs. desktop**
| Segment | Contrôle | Variante | Lift |
|---------|---------|---------|------|
| Mobile | X % | Y % | +Z % |
| Desktop | X % | Y % | +Z % |

**Nouveaux vs. récurrents**
| Segment | Contrôle | Variante | Lift |
|---------|---------|---------|------|
| Nouveaux | X % | Y % | +Z % |
| Récurrents | X % | Y % | +Z % |

## Interprétation

### Que s'est-il passé ?
[Explication des résultats en langage simple]

### Pourquoi pense-t-on que c'est arrivé ?
[Analyse et raisonnement]

### Réserves
[Limites, facteurs externes ou inquiétudes éventuelles]

## Décision

**Gagnant** : [Contrôle / Variante]

**Action** : [Implémenter la variante / Garder le contrôle / Re-tester]

**Planning** : [Quand les changements seront implémentés]

## Enseignements

### Ce qu'on a appris
- [Enseignement clé 1]
- [Enseignement clé 2]

### Quoi tester ensuite
- [Idée de test de suivi 1]
- [Idée de test de suivi 2]

### Impact
- **Lift projeté** : [X % d'amélioration sur la métrique Y]
- **Impact business** : [Chiffre d'affaires, conversions, etc.]
```

---

## Template d'entrée de référentiel de tests

Pour suivre tous les tests dans un emplacement central :

```markdown
| ID du test | Nom | Page | Dates | Métrique principale | Résultat | Lift | Lien |
|---------|------|------|-------|----------------|--------|------|------|
| 001 | Test du titre hero | Page d'accueil | 1/1-1/15 | CTR | Gagnant | +12 % | [Lien] |
| 002 | Mise en page du tableau de pricing | Pricing | 1/10-1/31 | Sélection d'offre | Perdant | -5 % | [Lien] |
| 003 | Champs du formulaire d'inscription | Inscription | 2/1-2/14 | Complétion | Non concluant | +2 % | [Lien] |
```

---

## Template de brief de test rapide

Pour les tests simples qui n'ont pas besoin d'une documentation complète :

```markdown
## [Nom du test]

**Quoi** : [Description en une phrase]
**Pourquoi** : [Hypothèse en une phrase]
**Métrique** : [Métrique principale]
**Durée** : [X semaines]
**Résultat** : [À déterminer / Gagnant / Perdant / Non concluant]
**Enseignements** : [Point clé à retenir]
```

---

## Template de mise à jour aux parties prenantes

```markdown
## Mise à jour A/B test : [Nom]

**Statut** : En cours / Terminé
**Jours restants** : X (ou terminé)
**Échantillon actuel** : X % de la cible

### Observations préliminaires
[Ce qu'on observe — sans prendre de décision pour l'instant]

### Prochaines étapes
[Ce qui se passe ensuite]

### Planning
- [Date] : Analyse terminée
- [Date] : Décision et recommandation
- [Date] : Implémentation (si gagnant)
```

---

## Scorecard de priorisation des expériences

Pour décider quels tests faire tourner :

| Facteur | Poids | Test A | Test B | Test C |
|--------|--------|--------|--------|--------|
| Impact potentiel | 30 % | | | |
| Confiance dans l'hypothèse | 25 % | | | |
| Facilité d'implémentation | 20 % | | | |
| Risque en cas d'erreur | 15 % | | | |
| Alignement stratégique | 10 % | | | |
| **Total** | | | | |

Notation : 1-5 (5 = meilleur)

---

## Template de banque d'hypothèses

Pour collecter des idées de test :

```markdown
| ID | Page/Zone | Observation | Hypothèse | Impact potentiel | Statut |
|----|-----------|-------------|------------|------------------|--------|
| H1 | Page d'accueil | Faible profondeur de scroll | Un hero plus court augmentera le scroll | Élevé | En test |
| H2 | Pricing | Les utilisateurs comparent les offres | Un tableau comparatif aidera | Moyen | Backlog |
| H3 | Inscription | Décrochage à l'email | Le social login augmentera la complétion | Moyen | Backlog |
```
