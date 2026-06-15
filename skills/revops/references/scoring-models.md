# Modèles de lead scoring

Modèles de scoring détaillés, modèles d'exemple par type d'activité, et guide de calibration.

## Modèle de scoring explicite (fit)

### Attributs de l'entreprise

| Attribut | Critères | Points |
|----------|----------|--------|
| **Taille d'entreprise** | 1-10 employés | +5 |
| | 11-50 employés | +10 |
| | 51-200 employés | +15 |
| | 201-1000 employés | +20 |
| | 1000+ employés | +15 (sauf si focus enterprise, alors +25) |
| **Secteur** | Secteur cible principal | +20 |
| | Secteur cible secondaire | +10 |
| | Secteur non ciblé | 0 |
| **Chiffre d'affaires** | Moins de 1 M€ | +5 |
| | 1 M€-10 M€ | +10 |
| | 10 M€-100 M€ | +15 |
| | 100 M€+ | +20 |
| **Géographie** | Marché principal | +10 |
| | Marché secondaire | +5 |
| | Marché non ciblé | 0 |

### Attributs du contact

| Attribut | Critères | Points |
|----------|----------|--------|
| **Titre du poste** | C-suite (CEO, CTO, CMO) | +25 |
| | Niveau VP | +20 |
| | Niveau Directeur | +15 |
| | Niveau Manager | +10 |
| | Contributeur individuel | +5 |
| **Département** | Département acheteur principal | +15 |
| | Département adjacent | +5 |
| | Département non lié | 0 |
| **Séniorité** | Décideur | +20 |
| | Influenceur | +10 |
| | Utilisateur final | +5 |

### Attributs technologiques

| Attribut | Critères | Points |
|----------|----------|--------|
| **Stack technique** | Utilise un outil complémentaire | +15 |
| | Utilise un concurrent | +10 (ils comprennent la catégorie) |
| | Utilise un outil que vous remplacez | +20 |
| **Maturité tech** | Stack moderne (cloud, SaaS-forward) | +10 |
| | Stack legacy | +5 |

---

## Modèle de scoring implicite (engagement)

### Signaux à forte intention

| Signal | Points | Décroissance |
|--------|--------|--------------|
| **Demande de démo** | +30 | Aucune |
| **Visite de la page de pricing** | +20 | -5 par semaine |
| **Inscription à un free trial** | +25 | Aucune |
| **Formulaire de contact ventes** | +30 | Aucune |
| **Page de cas client (2+)** | +15 | -5 par 2 semaines |
| **Visite de la page de comparaison** | +15 | -5 par semaine |
| **Calculateur de ROI utilisé** | +20 | -5 par 2 semaines |

### Signaux à intention moyenne

| Signal | Points | Décroissance |
|--------|--------|--------------|
| **Inscription à un webinaire** | +10 | -5 par mois |
| **Présence à un webinaire** | +15 | -5 par mois |
| **Téléchargement de livre blanc** | +10 | -5 par mois |
| **Visite de blog (3+ en une semaine)** | +10 | -5 par 2 semaines |
| **Clic email** | +5 par clic | -2 par mois |
| **Ouverture email (3+)** | +5 | -2 par mois |
| **Engagement sur les réseaux sociaux** | +5 | -2 par mois |

### Signaux à faible intention

| Signal | Points | Décroissance |
|--------|--------|--------------|
| **Visite de blog unique** | +2 | -2 par mois |
| **Ouverture de newsletter** | +2 | -1 par mois |
| **Ouverture d'email unique** | +1 | -1 par mois |
| **Visite de la page d'accueil uniquement** | +1 | -1 par semaine |

### Signaux d'usage produit (PLG)

| Signal | Points | Décroissance |
|--------|--------|--------------|
| **A créé un compte** | +15 | Aucune |
| **A complété l'onboarding** | +20 | Aucune |
| **A utilisé une feature cœur (3+ fois)** | +25 | -5 par mois d'inactivité |
| **A invité un membre d'équipe** | +25 | Aucune |
| **A atteint la limite d'usage** | +20 | -10 par mois |
| **A exporté des données** | +10 | -5 par mois |
| **A connecté une intégration** | +15 | Aucune |
| **Actif quotidiennement 5+ jours** | +20 | -10 par 2 semaines d'inactivité |

---

## Signaux de scoring négatif

| Signal | Points | Notes |
|--------|--------|-------|
| **Domaine email de concurrent** | -50 | Auto-signaler pour revue |
| **Email étudiant (.edu)** | -30 | Peut rester valide dans certains cas |
| **Email personnel (gmail, yahoo)** | -10 | Moins pertinent pour le B2B ; ajuster pour le SMB |
| **Désinscription des emails** | -20 | Réduire le score d'engagement |
| **Bounce (hard)** | -50 | Retirer du scoring |
| **Plainte spam** | -100 | Retirer de toutes les séquences |
| **Titre : Étudiant/Stagiaire** | -25 | Faible autorité d'achat |
| **Titre : Consultant** | -10 | Peut évaluer pour un client |
| **Aucune visite de site en 90 jours** | -15 | Décroissance du score |
| **Numéro de téléphone invalide** | -10 | Signal de qualité des données |
| **Visiteur de la page carrières uniquement** | -30 | Probablement un chercheur d'emploi |

---

## Modèles de scoring d'exemple

### Modèle 1 : SaaS PLG (ACV 500-5 000 €)

**Pondération : 30% fit / 70% engagement (favoriser fortement l'usage produit)**

**Critères de fit :**
- Taille d'entreprise 10-500 : +15
- Secteur cible : +10
- Rôle Manager+ : +10
- Utilise un outil complémentaire : +10

**Critères d'engagement :**
- A créé un compte gratuit : +15
- A complété l'onboarding : +20
- A utilisé une feature cœur 3+ fois : +25
- A invité un membre d'équipe : +25
- A atteint la limite d'usage : +20
- Visite de la page de pricing : +15

**Négatif :**
- Email personnel : -10
- Pas de login en 14 jours : -15
- Domaine de concurrent : -50

**Seuil MQL : 60 points**
**Recalibration : Mensuelle** (boucle de feedback rapide avec un fort volume)

---

### Modèle 2 : Enterprise Sales-Led (ACV 50 000 €+)

**Pondération : 60% fit / 40% engagement (le fit est critique à cet ACV)**

**Critères de fit :**
- Taille d'entreprise 500+ : +20
- Chiffre d'affaires 50 M€+ : +15
- Secteur cible : +15
- Titre VP+ : +20
- Décideur confirmé : +15
- Utilise un concurrent : +10

**Critères d'engagement :**
- Demande de démo : +30
- Plusieurs parties prenantes engagées : +20
- A assisté à un webinaire dirigeants : +15
- A téléchargé le guide ROI : +10
- A visité la page de pricing 2+ : +15

**Négatif :**
- Entreprise trop petite (<100) : -30
- Contributeur individuel uniquement : -15
- Domaine de concurrent : -50

**Seuil MQL : 75 points**
**Recalibration : Trimestrielle** (cycles de vente plus longs, échantillon plus petit)

---

### Modèle 3 : Mid-Market hybride (ACV 5 000-25 000 €)

**Pondération : 50% fit / 50% engagement (approche équilibrée)**

**Critères de fit :**
- Taille d'entreprise 50-1000 : +15
- Secteur cible : +10
- Titre Manager-VP : +15
- Géographie cible : +10
- Utilise un outil complémentaire : +10

**Critères d'engagement :**
- Demande de démo ou inscription au trial : +25
- Visite de la page de pricing : +15
- Téléchargement de cas client : +10
- Présence à un webinaire : +10
- Engagement email (3+ clics) : +10
- Visites de blog (5+ pages) : +10

**Négatif :**
- Email personnel : -10
- Aucun engagement en 30 jours : -10
- Domaine de concurrent : -50
- Titre étudiant/stagiaire : -25

**Seuil MQL : 65 points**
**Recalibration : Trimestrielle**

---

## Calibration du seuil

### Fixer le seuil initial

1. **Extraire les données closed-won** des 6-12 derniers mois
2. **Scorer rétroactivement** chaque deal avec votre nouveau modèle
3. **Trouver le point de rupture naturel** — quel score séparait les wins des losses ?
4. **Fixer le seuil** juste en dessous de là où 80% des deals closed-won auraient scoré
5. **Valider** contre les closed-lost — si beaucoup de closed-lost scorent au-dessus du seuil, resserrer les critères

### Cadence de calibration

| Type d'activité | Fréquence de recalibration | Pourquoi |
|-----------------|----------------------------|----------|
| PLG / Fort volume | Mensuelle | Boucle de feedback rapide, beaucoup de données |
| Mid-market | Trimestrielle | Durée de cycle modérée |
| Enterprise | Trimestrielle à semestrielle | Cycles longs, échantillon petit |

### Étapes de calibration

1. **Extraire les données MQL-vers-closing** de la période de calibration
2. **Comparer les MQL scorés vs les résultats réels :**
   - Score élevé + closed-won = correctement scoré
   - Score élevé + closed-lost = possible faux positif (resserrer)
   - Score bas + closed-won = possible faux négatif (relâcher)
3. **Ajuster les pondérations** selon les attributs qui ont réellement corrélé avec les wins
4. **Ajuster le seuil** si le volume de MQL est trop élevé (monter) ou trop bas (baisser)
5. **Documenter les changements** et les communiquer à l'équipe commerciale

### Signaux d'alerte que votre modèle a besoin de recalibration

- Le taux d'acceptation MQL-vers-SQL chute sous 30%
- Les ventes rejettent systématiquement les MQL comme « pas prêts »
- Les leads à score élevé ne convertissent pas ; les leads à score bas si
- Le volume de MQL grimpe sans revenu correspondant
- Changements de produit/marché depuis la dernière calibration
