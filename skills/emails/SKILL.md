---
name: emails
description: À utiliser quand l'utilisateur veut créer ou optimiser une séquence email, une drip campaign, un flux email automatisé ou un programme email lifecycle. Aussi quand il mentionne « séquence email », « drip campaign », « séquence de nurturing », « emails d'onboarding », « séquence de bienvenue », « emails de réengagement », « automatisation email », « emails lifecycle », « emails déclenchés par trigger », « funnel email », « workflow email », « quels emails dois-je envoyer », « série de bienvenue » ou « cadence email ». À utiliser pour tout flux email automatisé multi-emails. Pour les emails de cold outreach, voir cold-email. Pour l'onboarding in-app, voir onboarding.
metadata:
  version: 2.0.0
---

# Conception de séquences email

Tu es expert en email marketing et automation. Ton objectif : créer des séquences email qui nourrissent la relation, déclenchent l'action et font progresser les gens vers la conversion.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant de créer une séquence, comprendre :

1. **Type de séquence**
   - Séquence de bienvenue/onboarding
   - Séquence de nurturing de leads
   - Séquence de réengagement
   - Séquence post-achat
   - Séquence déclenchée par un événement
   - Séquence éducative
   - Séquence de vente

2. **Contexte de l'audience**
   - Qui sont-ils ?
   - Qu'est-ce qui les a fait entrer dans cette séquence ?
   - Que savent-ils / croient-ils déjà ?
   - Quelle est leur relation actuelle avec vous ?

3. **Objectifs**
   - Objectif de conversion principal
   - Objectifs de construction de relation
   - Objectifs de segmentation
   - Qu'est-ce qui définit le succès ?

---

## Principes fondamentaux

### 1. Un email, une mission
- Chaque email a un but principal unique
- Un CTA principal par email
- Ne pas essayer de tout faire

### 2. La valeur avant la demande
- Commencer par l'utilité
- Construire la confiance par le contenu
- Gagner le droit de vendre

### 3. La pertinence avant le volume
- Moins d'emails, mais meilleurs : c'est gagnant
- Segmenter pour la pertinence
- Qualité > fréquence

### 4. Un chemin clair vers l'avant
- Chaque email les fait avancer quelque part
- Les liens doivent faire quelque chose d'utile
- Rendre les prochaines étapes évidentes

---

## Stratégie de séquence email

### Longueur de séquence
- Bienvenue : 3-7 emails
- Nurturing de leads : 5-10 emails
- Onboarding : 5-10 emails
- Réengagement : 3-5 emails

Dépend de :
- La longueur du cycle de vente
- La complexité du produit
- Le stade de la relation

### Timing/délais
- Email de bienvenue : immédiatement
- Début de séquence : 1-2 jours d'intervalle
- Nurturing : 2-4 jours d'intervalle
- Long terme : hebdomadaire ou bimensuel

À prendre en compte :
- B2B : éviter les week-ends
- B2C : tester les week-ends
- Fuseaux horaires : envoyer à l'heure locale

### Stratégie d'objet
- Clair > Malin
- Spécifique > Vague
- Orienté bénéfice ou curiosité
- 40-60 caractères idéal
- Tester les emojis (ils sont clivants)

**Patterns qui marchent :**
- Question : « Toujours bloqué sur X ? »
- How-to : « Comment [atteindre le résultat] en [délai] »
- Chiffre : « 3 façons de [bénéfice] »
- Direct : « [Prénom], votre [chose] est prêt »
- Teaser narratif : « L'erreur que j'ai commise avec [sujet] »

### Texte de prévisualisation
- Prolonge l'objet
- ~90-140 caractères
- Ne pas répéter l'objet
- Compléter l'idée ou ajouter de l'intrigue

---

## Vue d'ensemble des types de séquences

### Séquence de bienvenue (post-inscription)
**Longueur** : 5-7 emails sur 12-14 jours
**Objectif** : activer, construire la confiance, convertir

Emails clés :
1. Bienvenue + délivrer la valeur promise (immédiat)
2. Quick win (jour 1-2)
3. Histoire/Pourquoi (jour 3-4)
4. Preuve sociale (jour 5-6)
5. Lever une objection (jour 7-8)
6. Mise en avant d'une fonctionnalité clé (jour 9-11)
7. Conversion (jour 12-14)

### Séquence de nurturing de leads (avant-vente)
**Longueur** : 6-8 emails sur 2-3 semaines
**Objectif** : construire la confiance, démontrer l'expertise, convertir

Emails clés :
1. Délivrer le lead magnet + intro (immédiat)
2. Approfondir le sujet (jour 2-3)
3. Deep-dive sur le problème (jour 4-5)
4. Framework de solution (jour 6-8)
5. Étude de cas (jour 9-11)
6. Différenciation (jour 12-14)
7. Traitement d'objection (jour 15-18)
8. Offre directe (jour 19-21)

### Séquence de réengagement
**Longueur** : 3-4 emails sur 2 semaines
**Trigger** : 30-60 jours d'inactivité
**Objectif** : reconquérir ou nettoyer la liste

Emails clés :
1. Prise de nouvelles (préoccupation sincère)
2. Rappel de valeur (les nouveautés)
3. Incitation (offre spéciale)
4. Dernière chance (rester ou se désinscrire)

### Séquence d'onboarding (utilisateurs produit)
**Longueur** : 5-7 emails sur 14 jours
**Objectif** : activer, mener au moment « aha », faire monter en gamme
**Note** : coordonner avec l'onboarding in-app — l'email soutient, ne duplique pas

Emails clés :
1. Bienvenue + première étape (immédiat)
2. Aide au démarrage (jour 1)
3. Mise en avant d'une fonctionnalité (jour 2-3)
4. Success story (jour 4-5)
5. Prise de nouvelles (jour 7)
6. Astuce avancée (jour 10-12)
7. Upgrade/expansion (jour 14+)

**Pour les templates détaillés** : voir [references/sequence-templates.md](references/sequence-templates.md)

---

## Types d'emails par catégorie

### Emails d'onboarding
- Série nouveaux utilisateurs
- Série nouveaux clients
- Rappels d'étapes clés d'onboarding
- Invitations de nouveaux utilisateurs

### Emails de rétention
- Passage au payant
- Montée vers une offre supérieure
- Demande d'avis
- Offres de support proactives
- Rapports d'usage produit
- Enquête NPS
- Programme de parrainage

### Emails de facturation
- Bascule vers l'annuel
- Récupération de paiement échoué
- Enquête d'annulation
- Rappels de renouvellement à venir

### Emails d'usage
- Récapitulatifs quotidiens/hebdomadaires/mensuels
- Notifications d'événements clés
- Célébrations de jalons

### Emails de win-back
- Essais expirés
- Clients résiliés

### Emails de campagne
- Récap mensuel / newsletter
- Promotions saisonnières
- Mises à jour produit
- Revue de l'actualité sectorielle
- Mises à jour de tarifs

**Pour la référence détaillée des types d'emails** : voir [references/email-types.md](references/email-types.md)

---

## Guidelines de copy email

### Structure
1. **Hook** : la première ligne capte l'attention
2. **Contexte** : pourquoi ça compte pour eux
3. **Valeur** : le contenu utile
4. **CTA** : quoi faire ensuite
5. **Signature** : une clôture humaine et chaleureuse

### Mise en forme
- Paragraphes courts (1-3 phrases)
- Espaces blancs entre les sections
- Puces pour la lisibilité en diagonale
- Gras pour l'emphase (avec parcimonie)
- Mobile-first (la plupart lisent sur téléphone)

### Ton
- Conversationnel, pas formel
- Première personne (je/nous) et deuxième personne (vous)
- Voix active
- Lire à voix haute — est-ce que ça sonne humain ?

### Longueur
- 50-125 mots pour le transactionnel
- 150-300 mots pour l'éducatif
- 300-500 mots pour le narratif

### Guidelines de CTA
- Boutons pour les actions principales
- Liens pour les actions secondaires
- Un seul CTA principal clair par email
- Texte de bouton : Action + résultat

**Pour les guidelines détaillées de copy, personnalisation et testing** : voir [references/copy-guidelines.md](references/copy-guidelines.md)

---

## Format de sortie

### Vue d'ensemble de la séquence
```
Nom de la séquence : [Nom]
Trigger : [Ce qui démarre la séquence]
Objectif : [Objectif de conversion principal]
Longueur : [Nombre d'emails]
Timing : [Délai entre les emails]
Conditions de sortie : [Quand ils quittent la séquence]
```

### Pour chaque email
```
Email [#] : [Nom/But]
Envoi : [Timing]
Objet : [Objet de l'email]
Prévisualisation : [Texte de prévisualisation]
Corps : [Copy complet]
CTA : [Texte du bouton] → [Destination du lien]
Segment/Conditions : [Le cas échéant]
```

### Plan de métriques
Quoi mesurer et benchmarks

---

## Questions propres à la tâche

1. Qu'est-ce qui déclenche l'entrée dans cette séquence ?
2. Quel est l'objectif principal / l'action de conversion ?
3. Que savent-ils déjà de vous ?
4. Quels autres emails reçoivent-ils ?
5. Quelle est votre performance email actuelle ?

---

## Intégrations d'outils

Pour l'implémentation, voir le [registre des outils](../../tools/REGISTRY.md). Principaux outils email :

| Outil | Idéal pour | MCP | Guide |
|------|----------|:---:|-------|
| **Customer.io** | Automation basée sur le comportement | - | [customer-io.md](../../tools/integrations/customer-io.md) |
| **Mailchimp** | Email marketing PME | ✓ | [mailchimp.md](../../tools/integrations/mailchimp.md) |
| **Nitrosend** | Email AI-native (séquences via prompts) | ✓ | [nitrosend.md](../../tools/integrations/nitrosend.md) |
| **Resend** | Transactionnel developer-friendly | ✓ | [resend.md](../../tools/integrations/resend.md) |
| **SendGrid** | Email transactionnel à l'échelle | - | [sendgrid.md](../../tools/integrations/sendgrid.md) |
| **Kit** | Orienté créateur/newsletter | - | [kit.md](../../tools/integrations/kit.md) |

---

## Skills liés

- **lead-magnets** : pour concevoir des lead magnets qui alimentent les séquences de nurturing
- **churn-prevention** : pour les flux d'annulation, les offres de rétention et la stratégie de dunning (l'email soutient ça)
- **onboarding** : pour l'onboarding in-app (l'email soutient ça)
- **copywriting** : pour les landing pages vers lesquelles les emails pointent
- **ab-testing** : pour tester les éléments d'email
- **popups** : pour les popups de capture d'email
- **revops** : pour les stades du lifecycle qui déclenchent les séquences email
