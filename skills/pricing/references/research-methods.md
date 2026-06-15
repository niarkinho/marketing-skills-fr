# Méthodes de recherche de pricing

## Sommaire
- Van Westendorp Price Sensitivity Meter (les quatre questions, comment analyser, conseils de sondage, exemple de sortie)
- Analyse MaxDiff (comment ça marche, exemple de question de sondage, analyse des résultats, utiliser MaxDiff pour le packaging)
- Sondages sur le consentement à payer
- Analyse de corrélation usage-valeur

## Van Westendorp Price Sensitivity Meter

Le sondage Van Westendorp identifie la fourchette de prix acceptable pour votre produit.

### Les quatre questions

Demandez à chaque répondant :
1. « À quel prix considéreriez-vous [produit] comme tellement cher que vous n'envisageriez pas de l'acheter ? » (Trop cher)
2. « À quel prix considéreriez-vous [produit] comme tellement bas que vous remettriez en question sa qualité ? » (Trop bon marché)
3. « À quel prix considéreriez-vous [produit] comme commençant à devenir cher, mais que vous pourriez encore l'envisager ? » (Cher/haut de la fourchette)
4. « À quel prix considéreriez-vous [produit] comme une bonne affaire — un excellent achat pour le prix ? » (Bon marché/bon rapport qualité-prix)

### Comment analyser

1. Tracez les distributions cumulées pour chaque question
2. Trouvez les intersections :
   - **Point of Marginal Cheapness (PMC) :** « Trop bon marché » croise « Cher »
   - **Point of Marginal Expensiveness (PME) :** « Trop cher » croise « Bon marché »
   - **Optimal Price Point (OPP) :** « Trop bon marché » croise « Trop cher »
   - **Indifference Price Point (IDP) :** « Cher » croise « Bon marché »

**La fourchette de prix acceptable :** de PMC à PME
**Zone de pricing optimale :** entre OPP et IDP

### Conseils de sondage
- Il faut 100-300 répondants pour des données fiables
- Segmentez par persona (consentement à payer différent)
- Utilisez des descriptions de produit réalistes
- Envisagez d'ajouter des questions d'intention d'achat

### Exemple de sortie

```
Résultats de l'analyse de sensibilité au prix :
─────────────────────────────────
Point of Marginal Cheapness:  29 €/mois
Optimal Price Point:          49 €/mois
Indifference Price Point:     59 €/mois
Point of Marginal Expensiveness: 79 €/mois

Fourchette recommandée : 49-59 €/mois
Prix actuel : 39 €/mois (sous l'optimal)
Opportunité : augmentation de prix de 25-50 % sans impact significatif sur la demande
```

---

## Analyse MaxDiff (Best-Worst Scaling)

MaxDiff identifie les fonctionnalités les plus valorisées par les clients, ce qui éclaire les décisions de packaging.

### Comment ça marche

1. Listez 8-15 fonctionnalités que vous pourriez inclure
2. Présentez aux répondants des ensembles de 4-5 fonctionnalités à la fois
3. Demandez : « Laquelle est la PLUS importante ? Laquelle est la MOINS importante ? »
4. Répétez sur plusieurs ensembles jusqu'à ce que toutes les fonctionnalités soient comparées
5. L'analyse statistique produit des scores d'importance

### Exemple de question de sondage

```
Quelle fonctionnalité est la PLUS importante pour vous ?
Quelle fonctionnalité est la MOINS importante pour vous ?

□ Projets illimités
□ Branding personnalisé
□ Support prioritaire
□ Accès API
□ Analytics avancées
```

### Analyse des résultats

Les fonctionnalités sont classées par score d'utilité :
- Forte utilité = Indispensable (à inclure dans le palier de base)
- Utilité moyenne = Différenciateur (sert à séparer les paliers)
- Faible utilité = Bonus (palier premium ou à supprimer)

### Utiliser MaxDiff pour le packaging

| Score d'utilité | Décision de packaging |
|---------------|-------------------|
| Top 20 % | Inclure dans tous les paliers (incontournable) |
| 20-50 % | Sert à différencier les paliers |
| 50-80 % | Paliers supérieurs uniquement |
| Bottom 20 % | Envisager de supprimer ou en add-on premium |

---

## Sondages sur le consentement à payer

**Méthode directe (simple mais biaisée) :**
« Combien paieriez-vous pour [produit] ? »

**Mieux : méthode Gabor-Granger :**
« Achèteriez-vous [produit] à [X €] ? » (Oui/Non)
Faites varier le prix entre les répondants pour construire une courbe de demande.

**Encore mieux : analyse conjointe :**
Présentez des bundles de produit à différents prix
Les répondants choisissent l'option préférée
L'analyse statistique révèle la sensibilité au prix par fonctionnalité

---

## Analyse de corrélation usage-valeur

### 1. Instrumenter les données d'usage
Suivez comment les clients utilisent votre produit :
- Fréquence d'usage des fonctionnalités
- Métriques de volume (utilisateurs, enregistrements, appels API)
- Métriques de résultat (chiffre d'affaires généré, temps gagné)

### 2. Corréler avec le succès client
- Quels patterns d'usage prédisent la rétention ?
- Quels patterns d'usage prédisent l'expansion ?
- Quels clients paient le plus, et pourquoi ?

### 3. Identifier les seuils de valeur
- À quel niveau d'usage les clients « comprennent » ?
- À quel niveau d'usage font-ils de l'expansion ?
- À quel niveau d'usage le prix devrait-il augmenter ?

### Exemple d'analyse

```
Analyse de corrélation usage-valeur :
─────────────────────────────────
Segment : clients à forte LTV (>10 k€ ARR)
Utilisateurs actifs mensuels moyens : 15
Projets moyens : 8
Intégrations moyennes : 4

Segment : clients churnés
Utilisateurs actifs mensuels moyens : 3
Projets moyens : 2
Intégrations moyennes : 0

Insight : la valeur est corrélée à l'adoption par l'équipe (utilisateurs)
        et à la profondeur d'usage (intégrations)

Recommandation : facturer par utilisateur, gater les intégrations aux paliers supérieurs
```
