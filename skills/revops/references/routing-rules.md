# Règles de lead routing

Arbres de décision, configurations spécifiques aux plateformes, routing par territoire, routing ABM et benchmarks de speed-to-lead.

## Arbre de décision de routing

Utiliser ce modèle pour cartographier votre logique de routing :

```
Nouveau lead arrive
│
├─ Est-ce un compte nommé/cible ?
│  ├─ OUI → Router vers le propriétaire du compte assigné
│  └─ NON ↓
│
├─ L'ACV est-il probablement > 50 000 € ? (selon taille d'entreprise + secteur)
│  ├─ OUI → Router vers l'équipe AE enterprise
│  └─ NON ↓
│
├─ Est-ce une inscription PLG avec usage en équipe ?
│  ├─ OUI → Router vers le spécialiste ventes PLG
│  └─ NON ↓
│
├─ Le lead correspond-il à un territoire ?
│  ├─ OUI → Router vers le propriétaire du territoire
│  └─ NON ↓
│
└─ Défaut : Round-robin dans les commerciaux disponibles
   └─ Si aucun commercial disponible : Assigner à la file d'équipe avec SLA de 1 heure
```

Personnalisez cet arbre pour votre activité. Le principe clé : **router vers la correspondance la plus spécifique d'abord, se rabattre sur le général.**

---

## Configuration du round-robin

### Règles de base du round-robin

1. Distribuer les leads équitablement entre les commerciaux éligibles
2. Sauter les commerciaux en congés, à pleine capacité, ou avec un pipeline plein
3. Pondérer par atteinte de quota (les commerciaux sous quota obtiennent une légère priorité)
4. Réinitialiser le compteur de distribution chaque semaine ou chaque mois
5. Logger chaque assignation pour l'audit

### Setup round-robin HubSpot

**Avec l'outil de rotation de HubSpot :**
- Naviguer vers Automation → Workflows
- Déclencheur : La propriété de contact « Lifecycle Stage » égale « MQL »
- Action : Faire tourner le propriétaire du contact parmi les utilisateurs sélectionnés
- Options : Distribution égale, sauter les propriétaires indisponibles
- Ajouter un délai + création de tâche après l'assignation

**Rotation personnalisée avec workflows :**
1. Créer une propriété personnalisée « Rotation Counter » (nombre)
2. Déclencheur de workflow : Nouveau MQL créé
3. Brancher selon la valeur du compteur de rotation (0, 1, 2... pour chaque commercial)
4. Régler le propriétaire du contact sur le commercial correspondant
5. Incrémenter le compteur (réinitialiser au max)
6. Créer une tâche de relance avec échéance SLA

### Setup round-robin Salesforce

**Avec les Lead Assignment Rules :**
1. Setup → Feature Settings → Marketing → Lead Assignment Rules
2. Créer les entrées de règle par ordre de priorité (plus spécifique d'abord)
3. Pour le round-robin : Utiliser la règle d'assignation + logique personnalisée

**Avec Flow pour un routing avancé :**
1. Créer un Record-Triggered Flow à la création de Lead
2. Get Records : Interroger un objet personnalisé « Rep Queue » pour le prochain commercial disponible
3. Élément Decision : Vérifier la disponibilité, la capacité, le territoire du commercial
4. Update Records : Assigner le propriétaire du lead
5. Create Task : Tâche de relance avec SLA
6. Mettre à jour « Rep Queue » pour suivre la dernière assignation

---

## Routing par territoire

### Par géographie

| Territoire | Régions | Équipe assignée |
|------------|---------|-----------------|
| Ouest | CA, WA, OR, NV, AZ, UT, CO, HI | Team West |
| Centre | TX, IL, MN, MO, OH, MI, WI, IN | Team Central |
| Est | NY, MA, PA, NJ, CT, VA, FL, GA | Team East |
| International | Tous hors US | Équipe internationale |

### Par taille d'entreprise

| Segment | Taille d'entreprise | Équipe |
|---------|---------------------|--------|
| SMB | 1-50 employés | Inside sales |
| Mid-market | 51-500 employés | AE mid-market |
| Enterprise | 501-5000 employés | AE enterprise |
| Stratégique | 5000+ employés | Équipe comptes stratégiques |

### Par secteur

| Vertical | Secteurs | Spécialiste |
|----------|----------|-------------|
| Tech | SaaS, services IT, hardware | Commercial vertical tech |
| Financier | Banque, assurance, fintech | Commercial vertical financier |
| Santé | Hôpitaux, pharma, healthtech | Commercial vertical santé |
| Général | Tous les autres | Pool général (round-robin) |

### Modèle de territoire hybride

Combiner plusieurs dimensions pour la précision :

```
Lead arrive
├─ Taille d'entreprise > 1000 ?
│  ├─ OUI → Équipe enterprise
│  │  └─ Sous-router par géographie
│  └─ NON ↓
├─ Secteur = Santé ou Financier ?
│  ├─ OUI → Spécialiste vertical
│  └─ NON ↓
└─ Round-robin dans le pool général
   └─ Pondéré par préférence géographique
```

---

## Routing par compte nommé / ABM

### Setup

1. **Définir la liste des comptes cibles** (généralement 50-500 comptes)
2. **Assigner les propriétaires de compte** dans le CRM (1 commercial par compte)
3. **Logique de matching :** Tout lead d'un domaine de compte cible route vers le propriétaire du compte
4. **Règles de matching :**
   - Match de domaine email (principal)
   - Match approximatif du nom d'entreprise (secondaire, nécessite une revue manuelle)
   - Résolution IP-vers-entreprise (tertiaire, pour les visiteurs anonymes)

### Règles de routing ABM

| Palier | Type de compte | Routing | SLA de réponse |
|--------|----------------|---------|----------------|
| Palier 1 | Top 20 comptes stratégiques | Propriétaire nommé, alerte instantanée | 1 heure |
| Palier 2 | Top 100 comptes cibles | Propriétaire nommé, alerte standard | 4 heures |
| Palier 3 | Match secteur cible / taille | Territoire ou round-robin | Même jour ouvré |

### Gestion multi-contacts

Quand plusieurs contacts du même compte s'engagent :
- Router tous les contacts vers le **même propriétaire de compte**
- Notifier le propriétaire des nouveaux contacts entrants
- Suivre le score d'engagement au niveau du compte (somme de tous les contacts)
- Déclencher une alerte « buying committee » quand 3+ contacts d'un même compte s'engagent

---

## Données de speed-to-lead

### Impact du délai de réponse sur la conversion

| Délai de réponse | Taux de qualification relatif | Notes |
|------------------|-------------------------------|-------|
| Moins de 5 minutes | **21x** plus de chances de qualifier | Référence absolue |
| 5-10 minutes | 10x plus de chances | Toujours fort |
| 10-30 minutes | 4x plus de chances | Acceptable pour la plupart |
| 30 min - 1 heure | 2x plus de chances | Sous la bonne pratique |
| 1-24 heures | Baseline | Moyenne du secteur |
| 24h+ | 60% plus bas que la baseline | Le lead est de fait froid |

Source : Lead Connect, InsideSales.com

### Implémenter le speed-to-lead

1. **Notification instantanée** — Push notification + email au commercial à la création du MQL
2. **Auto-tâche avec minuteur** — Créer une tâche avec décompte de SLA de 5 minutes
3. **Chaîne d'escalade :**
   - 5 min : Commercial d'origine alerté
   - 15 min : Commercial de secours alerté
   - 30 min : Manager alerté
   - 1 heure : Lead réassigné au prochain commercial disponible
4. **Mesurer et reporter** — Suivre les délais de réponse réels chaque semaine ; reconnaître les répondeurs rapides

### Automatisation du speed-to-lead

**Déclencheur :** Nouveau MQL créé
**Actions :**
1. Assigner à un commercial via les règles de routing (instantané)
2. Envoyer push notification + email au commercial
3. Créer une tâche : « Contacter [Nom du lead] — SLA 5 min »
4. Démarrer le minuteur de SLA
5. Si aucune activité loggée en 15 min → alerter le commercial de secours
6. Si aucune activité en 30 min → alerter le manager
7. Si aucune activité en 60 min → réassigner via round-robin

### Mesurer le speed-to-lead

Suivre ces métriques chaque semaine :
- **Temps moyen jusqu'au premier contact** (de la création du MQL au premier appel/email)
- **Temps médian jusqu'au premier contact** (moins faussé par les valeurs extrêmes)
- **% de leads contactés dans le SLA** (cible : 90%+)
- **Taux de contact par heure de la journée** (identifier les trous de couverture)
- **Taux de conversion par délai de réponse** (prouver le ROI de la rapidité)
