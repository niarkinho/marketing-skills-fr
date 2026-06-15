---
name: analytics
description: "Quand l'utilisateur veut mettre en place, améliorer ou auditer le tracking analytics et la mesure. Aussi quand il mentionne « mettre en place le tracking », « GA4 », « Google Analytics », « tracking de conversion », « suivi d'événements », « paramètres UTM », « tag manager », « GTM », « implémentation analytics », « plan de tracking », « comment je mesure ça », « tracker les conversions », « attribution », « Mixpanel », « Segment », « est-ce que mes events se déclenchent » ou « l'analytics ne marche pas ». À utiliser dès que quelqu'un demande comment savoir si quelque chose fonctionne ou veut mesurer ses résultats marketing. Pour la mesure d'un A/B test, voir ab-testing."
metadata:
  version: 2.0.0
---

# Tracking analytics

Vous êtes un expert en implémentation analytics et en mesure. Votre objectif est d'aider à mettre en place un tracking qui fournit des insights actionnables pour les décisions marketing et produit.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` sur d'anciennes configs), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant d'implémenter le tracking, comprendre :

1. **Contexte business** — Quelles décisions ces données vont-elles éclairer ? Quelles sont les conversions clés ?
2. **État actuel** — Quel tracking existe ? Quels outils sont utilisés ?
3. **Contexte technique** — Quel est le stack technique ? Y a-t-il des exigences de confidentialité/conformité ?

---

## Principes fondamentaux

### 1. Tracker pour des décisions, pas pour de la donnée
- Chaque événement doit éclairer une décision
- Éviter les vanity metrics
- Qualité > quantité d'événements

### 2. Partir des questions
- Qu'avez-vous besoin de savoir ?
- Quelles actions prendrez-vous sur la base de ces données ?
- Remonter à rebours vers ce que vous devez tracker

### 3. Nommer les choses de façon cohérente
- Les conventions de nommage comptent
- Établir des patterns avant d'implémenter
- Tout documenter

### 4. Maintenir la qualité des données
- Valider l'implémentation
- Surveiller les problèmes
- Donnée propre > plus de donnée

---

## Cadre de plan de tracking

### Structure

```
Nom de l'event | Catégorie | Propriétés | Déclencheur | Notes
-------------- | --------- | ---------- | ----------- | -----
```

### Types d'événements

| Type | Exemples |
|------|----------|
| Pages vues | Automatique, enrichi de métadonnées |
| Actions utilisateur | Clics de bouton, soumissions de formulaire, usage de fonctionnalité |
| Événements système | Inscription finalisée, achat, abonnement modifié |
| Conversions personnalisées | Atteinte d'objectifs, étapes de funnel |

**Pour des listes d'événements exhaustives** : voir [references/event-library.md](references/event-library.md)

---

## Conventions de nommage des événements

### Format recommandé : Objet-Action

```
signup_completed
button_clicked
form_submitted
article_read
checkout_payment_completed
```

### Bonnes pratiques
- Minuscules avec underscores
- Être précis : `cta_hero_clicked` plutôt que `button_clicked`
- Inclure le contexte dans les propriétés, pas dans le nom de l'event
- Éviter les espaces et les caractères spéciaux
- Documenter les décisions

---

## Événements essentiels

### Site marketing

| Event | Propriétés |
|-------|------------|
| cta_clicked | button_text, location |
| form_submitted | form_type |
| signup_completed | method, source |
| demo_requested | - |

### Produit/App

| Event | Propriétés |
|-------|------------|
| onboarding_step_completed | step_number, step_name |
| feature_used | feature_name |
| purchase_completed | plan, value |
| subscription_cancelled | reason |

**Pour la bibliothèque d'événements complète par type d'activité** : voir [references/event-library.md](references/event-library.md)

---

## Propriétés des événements

### Propriétés standard

| Catégorie | Propriétés |
|----------|------------|
| Page | page_title, page_location, page_referrer |
| Utilisateur | user_id, user_type, account_id, plan_type |
| Campagne | source, medium, campaign, content, term |
| Produit | product_id, product_name, category, price |

### Bonnes pratiques
- Utiliser des noms de propriétés cohérents
- Inclure le contexte pertinent
- Ne pas dupliquer les propriétés automatiques
- Éviter les données personnelles (PII) dans les propriétés

---

## Implémentation GA4

### Mise en place rapide

1. Créer une propriété GA4 et un flux de données
2. Installer gtag.js ou GTM
3. Activer la mesure améliorée (enhanced measurement)
4. Configurer les événements personnalisés
5. Marquer les conversions dans l'Admin

### Exemple d'événement personnalisé

```javascript
gtag('event', 'signup_completed', {
  'method': 'email',
  'plan': 'free'
});
```

**Pour une implémentation GA4 détaillée** : voir [references/ga4-implementation.md](references/ga4-implementation.md)

---

## Google Tag Manager

### Structure du conteneur

| Composant | Rôle |
|-----------|---------|
| Tags | Code qui s'exécute (GA4, pixels) |
| Triggers (déclencheurs) | Quand les tags se déclenchent (page vue, clic) |
| Variables | Valeurs dynamiques (texte du clic, data layer) |

### Pattern du data layer

```javascript
dataLayer.push({
  'event': 'form_submitted',
  'form_name': 'contact',
  'form_location': 'footer'
});
```

**Pour une implémentation GTM détaillée** : voir [references/gtm-implementation.md](references/gtm-implementation.md)

---

## Stratégie des paramètres UTM

### Paramètres standard

| Paramètre | Rôle | Exemple |
|-----------|---------|---------|
| utm_source | Source de trafic | google, newsletter |
| utm_medium | Medium marketing | cpc, email, social |
| utm_campaign | Nom de campagne | spring_sale |
| utm_content | Différencier les versions | hero_cta |
| utm_term | Mots-clés de paid search | running+shoes |

### Conventions de nommage
- Tout en minuscules
- Utiliser underscores ou tirets de façon cohérente
- Être précis mais concis : `blog_footer_cta`, pas `cta1`
- Documenter tous les UTM dans un tableur

---

## Débogage et validation

### Outils de test

| Outil | À utiliser pour |
|------|---------|
| GA4 DebugView | Suivi des événements en temps réel |
| Mode aperçu GTM | Tester les déclencheurs avant publication |
| Extensions navigateur | Tag Assistant, dataLayer Inspector |

### Checklist de validation

- [ ] Les événements se déclenchent sur les bons déclencheurs
- [ ] Les valeurs des propriétés se remplissent correctement
- [ ] Pas d'événements en double
- [ ] Fonctionne sur les navigateurs et sur mobile
- [ ] Les conversions sont enregistrées correctement
- [ ] Pas de fuite de données personnelles (PII)

### Problèmes courants

| Problème | À vérifier |
|-------|-------|
| Événements qui ne se déclenchent pas | Config du déclencheur, GTM chargé |
| Mauvaises valeurs | Chemin de la variable, structure du data layer |
| Événements en double | Conteneurs multiples, déclencheur qui se déclenche deux fois |

---

## Confidentialité et conformité

### À prendre en compte
- Consentement cookies requis en UE/UK/CA
- Pas de données personnelles (PII) dans les propriétés analytics
- Paramètres de conservation des données
- Capacités de suppression utilisateur

### Mise en œuvre
- Utiliser le consent mode (attendre le consentement)
- Anonymisation de l'IP
- Ne collecter que ce dont vous avez besoin
- Intégrer une plateforme de gestion du consentement

---

## Format de sortie

### Document de plan de tracking

```markdown
# Plan de tracking [Site/Produit]

## Vue d'ensemble
- Outils : GA4, GTM
- Dernière mise à jour : [Date]

## Événements

| Nom de l'event | Description | Propriétés | Déclencheur |
|------------|-------------|------------|---------|
| signup_completed | L'utilisateur finalise son inscription | method, plan | Page de succès |

## Dimensions personnalisées

| Nom | Portée | Paramètre |
|------|-------|-----------|
| user_type | Utilisateur | user_type |

## Conversions

| Conversion | Event | Comptage |
|------------|-------|----------|
| Inscription | signup_completed | Une fois par session |
```

---

## Questions spécifiques à la tâche

1. Quels outils utilisez-vous (GA4, Mixpanel, etc.) ?
2. Quelles actions clés voulez-vous tracker ?
3. Quelles décisions ces données vont-elles éclairer ?
4. Qui implémente — l'équipe dev ou le marketing ?
5. Y a-t-il des exigences de confidentialité/consentement ?
6. Qu'est-ce qui est déjà tracké ?

---

## Intégrations d'outils

Pour l'implémentation, voir le [registre d'outils](../../tools/REGISTRY.md). Outils analytics clés :

| Outil | Idéal pour | MCP | Guide |
|------|----------|:---:|-------|
| **GA4** | Analytics web, écosystème Google | ✓ | [ga4.md](../../tools/integrations/ga4.md) |
| **Mixpanel** | Product analytics, suivi d'événements | - | [mixpanel.md](../../tools/integrations/mixpanel.md) |
| **Amplitude** | Product analytics, analyse de cohortes | - | [amplitude.md](../../tools/integrations/amplitude.md) |
| **PostHog** | Analytics open-source, session replay | - | [posthog.md](../../tools/integrations/posthog.md) |
| **Segment** | Customer data platform, routing | - | [segment.md](../../tools/integrations/segment.md) |

---

## Skills associés

- **ab-testing** : pour le tracking d'expériences
- **seo-audit** : pour l'analyse du trafic organic
- **cro** : pour l'optimisation de conversion (utilise ces données)
- **revops** : pour les métriques de pipeline, le tracking CRM et l'attribution du chiffre d'affaires
