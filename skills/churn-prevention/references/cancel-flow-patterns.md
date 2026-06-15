# Patterns de cancel flow

Patterns de cancel flow détaillés par type d'entreprise, prestataire de facturation et secteur.

---

## Cancel flow par type d'entreprise

### SaaS B2C / self-serve

Fort volume, faible touch. Le flow doit fonctionner sans intervention humaine.

**Structure du flow :**
```
Bouton d'annulation → Exit survey (1 question) → Offre dynamique → Confirmer → Post-annulation
```

**Caractéristiques :**
- Entièrement automatisé, aucun humain dans la boucle
- Rapide — 2-3 écrans maximum
- Une offre + une de repli, pas un menu d'options
- Optimisé pour le mobile (annulations significatives sur mobile)
- « Continuer l'annulation » clair à chaque étape

**Taux de sauvegarde typique :** 20-30 %

**Exemple de flow pour une app de productivité à 29 €/mois :**
1. « Quelle est la raison principale ? » → 6 options
2. A sélectionné « Trop cher » → « Obtenez 25 % de remise pendant 3 mois (économisez 21,75 €) »
3. A refusé → « Ou passez à notre plan Starter à 12 €/mois »
4. A refusé → « Désolés de vous voir partir. Votre accès continue jusqu'au [date]. »

---

### B2B / plans d'équipe

Volume plus faible, enjeux plus élevés. Le contact personnel vaut le coût.

**Structure du flow :**
```
Bouton d'annulation → Exit survey → Offre (ou routage vers le CS) → Confirmer → Post-annulation
```

**Caractéristiques :**
- Router les comptes au-dessus d'un seuil de MRR vers le customer success
- Montrer l'impact sur l'équipe (« Vos 8 membres d'équipe perdront l'accès »)
- Proposer un appel admin-à-admin pour les comptes entreprise
- Considération plus longue — autoriser « planifier un appel » comme option de sauvegarde
- Exiger un rôle admin/owner pour annuler (pas n'importe quel membre)

**Taux de sauvegarde typique :** 30-45 % (plus élevé grâce au contact personnel)

**Routage basé sur le MRR :**

| MRR du compte | Cancel flow |
|-------------|-------------|
| <100 €/mois | Flow automatisé avec offres |
| 100-500 €/mois | Automatisé + flag pour suivi CS |
| 500-2 000 €/mois | Router vers le CS avant la fin de l'annulation |
| 2 000 €+/mois | Bloquer l'annulation self-serve, exiger un appel CS |

---

### Freemium / free-to-paid

Des utilisateurs qui annulent le payant pour revenir au palier gratuit. Psychologie différente — ils ne partent pas, ils downgradent.

**Structure du flow :**
```
Bouton d'annulation → Invitation « Passer au gratuit ? » → Exit survey (s'ils annulent encore) → Offre → Confirmer
```

**Caractéristiques :**
- Mener avec le palier gratuit comme première option (pas une save offer)
- Montrer ce qu'ils gardent sur le gratuit vs. ce qu'ils perdent
- La « sauvegarde » consiste à les garder sur le gratuit, pas à les perdre entièrement
- Suivre les utilisateurs du palier gratuit pour de futures campagnes de re-upgrade

---

## Cancel flow par intervalle de facturation

### Abonnés mensuels

- Plus sensibles au prix, engagement plus court
- Les offres de remise marchent bien (20-30 % pendant 2-3 mois)
- La pause est efficace (1-2 mois)
- Suggérer un plan annuel à prix réduit comme alternative

**Priorité des offres :**
1. Remise (si raison = prix)
2. Pause (si raison = pas d'usage / temporaire)
3. Passage au plan annuel (si engagé mais sensible au prix)

### Abonnés annuels

- Engagement plus fort, annulent souvent pour des raisons plus fortes
- Les attentes de remboursement au prorata comptent
- Fenêtre de sauvegarde plus longue (ils ont déjà payé)
- Contact personnel plus justifié (LTV plus élevée en jeu)

**Priorité des offres :**
1. Mettre en pause le reste du terme (si temporaire)
2. Ajustement de plan + crédit pour le prochain renouvellement
3. Contact personnel du CS
4. Remboursement partiel + downgrade (mieux qu'un remboursement complet + annulation)

**Gestion des remboursements :**
- Proposer un remboursement au prorata s'il reste un temps significatif
- « Pause jusqu'au renouvellement » s'il reste moins de 3 mois
- Être généreux — les mauvaises expériences de remboursement créent des détracteurs bruyants

---

## Patterns de save offers

### L'échelle de remise

Ne pas mener avec votre plus grosse remise. Escalader :

```
Clic d'annulation → 15 % de remise → Annule encore → 25 % de remise → Annule encore → Les laisser partir
```

**Règles :**
- Maximum 2 offres de remise par session d'annulation
- Ne jamais dépasser 30 % (au-delà, ça habitue au comportement annuler-pour-remise)
- Limiter les remises dans le temps (2-3 mois, puis retour au plein tarif)
- Suivre ceux qui acceptent la remise — s'ils annulent à nouveau au plein tarif, ne pas re-proposer

### Le playbook de la pause

La pause est souvent meilleure qu'une remise parce qu'elle ne dévalorise pas votre produit.

**Implémentation :**

| Réglage | Recommandation |
|---------|---------------|
| Options de durée de pause | 1 mois, 2 mois, 3 mois |
| Sélection par défaut | 1 mois (la plus courte) |
| Pause maximale | 3 mois (les pauses plus longues reviennent rarement) |
| Pendant la pause | Garder les données, retirer l'accès |
| Réactivation | Réactivation automatique avec email 7 jours à l'avance |
| Pauses répétées | Autoriser 1 pause par période de 12 mois |

**Séquence de réactivation après pause :**
- Jour -7 : « Votre pause se termine dans 7 jours. On a été occupés — voici les nouveautés. »
- Jour -1 : « De retour demain ! Voici ce qui vous attend. »
- Jour 0 : « Vous êtes de retour ! Voici un tour rapide des nouveautés. »

### Le chemin du downgrade

Pour les produits multi-plans, le downgrade est la sauvegarde la plus forte :

```
┌─────────────────────────────────────────┐
│  Avant de partir, et si on ajustait     │
│  votre plan ?                           │
│                                         │
│  Actuel : Pro (49 €/mois)               │
│                                         │
│  ┌─────────────────────────────────┐    │
│  │ Passer à Starter (19 €/mois)    │    │
│  │                                 │    │
│  │ ✓ Gardez : projets, intégrations│    │
│  │ ✗ Perdez : analytics avancées,  │    │
│  │           fonctionnalités équipe│    │
│  │                                 │    │
│  │ [Passer à Starter]              │    │
│  └─────────────────────────────────┘    │
│                                         │
│  [Non merci, continuer l'annulation]    │
└─────────────────────────────────────────┘
```

**Bonnes pratiques de downgrade :**
- Montrer exactement ce qu'ils gardent et ce qu'ils perdent
- Utiliser des coches et des croix pour la scannabilité
- Préserver leurs données même sur le plan inférieur
- S'ils downgradent, ne pas afficher d'invitations à upgrader pendant au moins 30 jours

### Le gestionnaire de passage à un concurrent

Quand la raison d'annulation est « passe à un concurrent » :

1. **Demander quel concurrent** (optionnel, ne pas forcer)
2. **Montrer une comparaison** si vous en avez une (voir le skill competitors)
3. **Proposer un crédit de migration** (« On s'aligne sur leur prix pendant 3 mois »)
4. **Demander un appel de feedback** (« 15 minutes pour comprendre ce qui nous manque »)

Ces données sont en or pour les équipes produit et marketing.

---

## Expérience post-annulation

Ce qui se passe après l'annulation compte pour :
- Le potentiel de win-back
- Le bouche-à-oreille
- Le sentiment des avis

### Page de confirmation

```
Votre abonnement a été annulé.

Ce qui se passe ensuite :
• Votre accès continue jusqu'au [date de fin de période de facturation]
• Vos données seront conservées pendant 90 jours
• Vous pouvez réactiver à tout moment depuis les paramètres de votre compte

[Réactiver mon compte]

On adorerait vous revoir. On continuera de s'améliorer grâce aux retours
de clients comme vous.
```

### Séquence post-annulation

| Timing | Action |
|--------|--------|
| Immédiatement | Email de confirmation avec date de fin d'accès |
| Jour 1 | (Rien — ne pas paraître désespéré) |
| Jour 7 | Sondage NPS/satisfaction sur l'expérience globale |
| Jour 30 | Email « Quoi de neuf » avec les améliorations récentes |
| Jour 60 | Traiter leur raison d'annulation précise si elle est résolue |
| Jour 90 | Win-back final avec une offre spéciale |

**Pour des séquences d'emails de win-back détaillées** : voir le skill emails.

---

## Règles de segmentation

Les cancel flows les plus efficaces utilisent la segmentation pour montrer différentes offres à différents clients.

### Dimensions de segmentation

| Dimension | Pourquoi c'est important |
|-----------|---------------|
| Plan / MRR | Les clients à forte valeur reçoivent un contact personnel |
| Ancienneté | Les clients de longue date reçoivent des offres plus généreuses |
| Niveau d'usage | Les gros utilisateurs reçoivent un message différent des dormants |
| Intervalle de facturation | Mensuel vs. annuel nécessitent des approches différentes |
| Sauvegardes précédentes | Ne pas re-proposer la même remise à un annuleur récidiviste |
| Raison d'annulation | Détermine quelle offre montrer (mapping central) |

### Flows spécifiques par segment

**Nouveau client (< 30 jours) :**
- Il n'a pas activé. La sauvegarde, c'est l'onboarding, pas les remises.
- Offre : appel d'onboarding gratuit, aide au setup, trial prolongé
- Demander : « Qu'espériez-vous accomplir ? » (apprendre ce qui manque)

**Client engagé qui annule pour le prix :**
- Il adore le produit mais ne peut pas justifier le coût.
- Offre : remise, passage au plan annuel, downgrade
- Fort potentiel de sauvegarde

**Client dormant (pas de connexion depuis 30+ jours) :**
- Il vous a oublié. Une remise ne le ramènera pas.
- Offre : mise en pause de l'abonnement, conversation « qu'est-ce qui a changé ? »
- Faible potentiel de sauvegarde — se concentrer sur comprendre pourquoi

**Power user qui passe à un concurrent :**
- Il choisit activement autre chose.
- Offre : alignement concurrentiel, appel de feedback, aperçu de la roadmap
- Potentiel de sauvegarde moyen — dépend de la raison

---

## Checklist d'implémentation

### Phase 1 : fondations (semaine 1)
- [ ] Ajouter un cancel flow (sondage + 1 offre + confirmation)
- [ ] Mettre en place l'exit survey avec 5-7 catégories de raisons
- [ ] Mapper une offre par raison (mapping simple 1:1)
- [ ] Suivre les raisons d'annulation et le taux de sauvegarde dans l'analytics
- [ ] Activer les emails pré-dunning d'expiration de carte

### Phase 2 : optimisation (semaines 2-4)
- [ ] Ajouter des offres de repli (principale + secondaire par raison)
- [ ] Implémenter l'option de mise en pause de l'abonnement
- [ ] Mettre en place la séquence d'emails de dunning (4 emails sur 10 jours)
- [ ] Activer les smart retries (Stripe Smart Retries ou équivalent)
- [ ] Ajouter le routage basé sur le MRR pour les comptes à forte valeur

### Phase 3 : avancé (mois 2+)
- [ ] Construire un health score à partir des signaux d'usage
- [ ] Mettre en place des déclencheurs d'intervention proactive
- [ ] A/B tester les montants de remise et les types d'offres
- [ ] Segmenter les flows par plan, ancienneté et usage
- [ ] Séquence de win-back post-annulation (coordonner avec le skill emails)
- [ ] Analyse de cohortes : churn par canal, plan, ancienneté

---

## Notes de conformité

### Règle Click-to-Cancel de la FTC (US)
- L'annulation doit être aussi facile que l'inscription
- Ne peut pas exiger un appel téléphonique pour annuler si l'inscription était en ligne
- Ne peut pas ajouter d'étapes excessives pour décourager l'annulation
- Les save offers sont autorisées mais « continuer l'annulation » doit être clair

### RGPD / rétention des données (UE)
- Informer les utilisateurs de la durée de rétention des données après l'annulation
- Proposer un export des données avant la suppression du compte
- Honorer les demandes de suppression dans les 30 jours
- Ne pas utiliser les données post-annulation à des fins marketing sans consentement

### Bonnes pratiques générales
- Toujours montrer un chemin clair pour finaliser l'annulation
- Ne jamais cacher le bouton d'annulation (dark pattern)
- Traiter l'annulation même si le save flow a des erreurs
- Confirmer l'annulation par un email de reçu
