# Modèle de rapport d'audit ASO

Utiliser cette structure pour tous les rapports d'audit ASO.

---

## En-tête

```
# Audit ASO : {Nom de l'app}
**Store :** {Apple App Store / Google Play}
**URL :** {URL de la fiche}
**Date de l'audit :** {date}
**Palier de marque :** {Dominant / Établi / Challenger} — {justification en une ligne}
**Score global :** {score}/100 (Note : {A/B/C/D/F})
```

---

## Carte de score

```
| Dimension | Score | Note | Problème clé |
|-----------|-------|------|--------------|
| Titre et sous-titre | X/10 | {note} | {résumé en une ligne} |
| Description | X/10 | {note} | {résumé en une ligne} |
| Visuels | X/10 | {note} | {résumé en une ligne} |
| Notes et avis | X/10 | {note} | {résumé en une ligne} |
| Métadonnées et fraîcheur | X/10 | {note} | {résumé en une ligne} |
| Signaux de conversion | X/10 | {note} | {résumé en une ligne} |
| **GLOBAL** | **{pondéré}/100** | **{note}** | |
```

Échelle de note par dimension : 9-10 = A, 7-8 = B, 5-6 = C, 3-4 = D, 1-2 = F

---

## Top 3 des quick wins

Changements à plus fort impact qui prennent moins d'1 heure :

```
### 1. {Verbe d'action} — {changement spécifique}
**Impact :** {Élevé/Moyen} | **Effort :** {<15 min / <30 min / <1 heure}
**Actuel :** {ce que c'est aujourd'hui}
**Recommandé :** {remplacement exact, avec nombre de caractères}
**Pourquoi :** {une phrase expliquant l'impact}

### 2. ...
### 3. ...
```

---

## Constats détaillés

### Analyse titre et sous-titre

```
**Titre actuel :** « {titre} » ({X}/30 car. utilisés)
**Sous-titre/desc. courte actuel :** « {sous-titre} » ({X}/30 ou /80 car. utilisés)

**Problèmes trouvés :**
- {problème 1}
- {problème 2}

**Titre recommandé :** « {nouveau titre} » ({X}/30 car.) — {justification}
**Sous-titre recommandé :** « {nouveau sous-titre} » ({X}/30 ou /80 car.) — {justification}
```

### Analyse de la description

```
**3 premières lignes (au-dessus de la ligne de flottaison) :**
> {texte cité}

**Problèmes trouvés :**
- {problème 1}
- {problème 2}

**Densité de mots-clés (Google Play uniquement) :** {X}% — cible : 2-3%
**Top mots-clés trouvés :** {motcle1} (Xn), {motcle2} (Xn), ...
**Mots-clés à forte valeur manquants :** {motcle1}, {motcle2}, ...

**3 premières lignes recommandées :**
> {texte réécrit}
```

### Analyse des visuels

```
**Captures d'écran :** {nombre} ({store} affiche les {3/toutes} premières en recherche)
**Vidéo de présentation :** {Oui/Non}
**Évaluation de l'icône :** {description}
**Feature graphic (Google Play) :** {Oui/Non}

**Audit des captures :**
1. {description capture 1} — {ok/problème}
2. {description capture 2} — {ok/problème}
...

**Recommandations :**
- {changement visuel spécifique 1}
- {changement visuel spécifique 2}
```

### Analyse des notes et avis

```
**Note moyenne :** {X,X} étoiles ({nombre} notes)
**Sentiment des avis récents :** {Positif/Mitigé/Négatif}
**Plaintes courantes :** {thème1}, {thème2}
**Réponses du développeur :** {Oui, actives / Sporadiques / Aucune}

**Recommandations :**
- {action spécifique 1}
- {action spécifique 2}
```

### Métadonnées et fraîcheur

```
**Dernière mise à jour :** {date} ({X jours/mois})
**Localisations :** {nombre} langues
**Catégorie :** {catégorie actuelle}
**In-app events/LiveOps :** {Oui/Non}

**Recommandations :**
- {action spécifique 1}
- {action spécifique 2}
```

### Signaux de conversion

```
**Modèle de prix :** {Gratuit / Freemium / Payant}
**Nombre d'achats intégrés :** {nombre}
**Téléchargements (Google Play) :** {tranche}
**Preuve sociale visible :** {récompenses, presse, badges — ou « aucune »}

**Recommandations :**
- {action spécifique 1}
- {action spécifique 2}
```

---

## Suggestions de mots-clés

```
| Mot-clé | Justification | Où le placer | Priorité |
|---------|---------------|--------------|----------|
| {motcle} | {pourquoi ce mot-clé} | {titre/sous-titre/description/champ mots-clés} | {Élevée/Moy/Basse} |
| ... | ... | ... | ... |
```

Note : sans outils ASO payants, le volume de recherche exact n'est pas disponible. Ces
suggestions sont basées sur l'analyse de catégorie, les métadonnées concurrentes et la pertinence
sémantique. Valider avec AppTweak, Sensor Tower ou MobileAction pour les données de volume.

---

## Comparaison concurrentielle (le cas échéant)

```
| Métrique | {Votre app} | {Concurrent 1} | {Concurrent 2} |
|----------|-------------|----------------|----------------|
| Mots-clés du titre | ... | ... | ... |
| Note | ... | ... | ... |
| Captures | ... | ... | ... |
| Vidéo | ... | ... | ... |
| Mots-clés de la description | ... | ... | ... |
| Dernière mise à jour | ... | ... | ... |
| Score ASO global | ... | ... | ... |
```

---

## Plan d'action priorisé

Ordonné par impact (élevé à faible), groupé par effort :

```
### À faire cette semaine (quick wins)
1. {action} — {impact attendu}
2. {action} — {impact attendu}

### À faire ce mois-ci (effort moyen)
3. {action} — {impact attendu}
4. {action} — {impact attendu}

### À planifier pour le trimestre prochain (effort élevé)
5. {action} — {impact attendu}
6. {action} — {impact attendu}
```

---

## Limites

Toujours inclure cette section :

> **Ce que cet audit ne peut pas mesurer sans outils ASO payants :**
>
> - Volume de recherche exact et scores de difficulté des mots-clés
> - Positions de classement historiques des mots-clés
> - Estimations de téléchargements et de revenus
> - Contenu du champ mots-clés Apple (caché du public)
> - Données de taux de conversion en install (disponibles uniquement pour le propriétaire de l'app dans la console)
> - Résultats d'A/B test d'expériences précédentes
>
> Pour ces données, envisager d'utiliser AppTweak (69 €/mois), Sensor Tower ou
> MobileAction (69 €/mois).
