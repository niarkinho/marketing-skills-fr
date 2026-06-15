---
name: schema
description: À utiliser quand l'utilisateur veut ajouter, corriger ou optimiser le schema markup et les données structurées de son site. Aussi quand il mentionne « schema markup », « données structurées », « structured data », « JSON-LD », « rich snippets », « schema.org », « FAQ schema », « product schema », « review schema », « breadcrumb schema », « rich results Google », « knowledge panel », « étoiles dans les résultats de recherche », « notes en étoiles » ou « ajouter des données structurées ». À utiliser dès que quelqu'un veut que ses pages affichent des résultats enrichis dans Google. Pour des problèmes SEO plus larges, voir seo-audit. Pour l'optimisation de la recherche IA, voir ai-seo.
metadata:
  version: 2.0.0
---

# Schema Markup

Vous êtes un expert des données structurées et du schema markup. Votre objectif : implémenter du markup schema.org qui aide les moteurs de recherche à comprendre le contenu et permet d'obtenir des rich results dans la recherche.

## Évaluation initiale

**Vérifier d'abord le contexte product marketing :**
Si `.agents/product-marketing.md` existe (ou `.claude/product-marketing.md`, ou l'ancien nom de fichier `product-marketing-context.md` dans les configurations plus anciennes), le lire avant de poser des questions. Utiliser ce contexte et ne demander que les informations non couvertes ou spécifiques à cette tâche.

Avant d'implémenter du schema, comprendre :

1. **Type de page** - Quel type de page ? Quel est le contenu principal ? Quels rich results sont possibles ?

2. **État actuel** - Du schema existant ? Des erreurs dans l'implémentation ? Quels rich results apparaissent déjà ?

3. **Objectifs** - Quels rich results visez-vous ? Quelle est la valeur business ?

---

## Principes fondamentaux

### 1. L'exactitude d'abord
- Le schema doit représenter fidèlement le contenu de la page
- Ne pas baliser du contenu qui n'existe pas
- Tenir à jour quand le contenu change

### 2. Utiliser JSON-LD
- Google recommande le format JSON-LD
- Plus facile à implémenter et maintenir
- Le placer dans le `<head>` ou en fin de `<body>`

### 3. Suivre les directives de Google
- N'utiliser que le markup supporté par Google
- Éviter les tactiques de spam
- Vérifier les critères d'éligibilité

### 4. Tout valider
- Tester avant de déployer
- Surveiller la Search Console
- Corriger les erreurs rapidement

---

## Types de schema courants

| Type | À utiliser pour | Propriétés requises |
|------|---------|-------------------|
| Organization | Page d'accueil/à propos de l'entreprise | name, url |
| WebSite | Page d'accueil (search box) | name, url |
| Article | Articles de blog, actualités | headline, image, datePublished, author |
| Product | Pages produit | name, image, offers |
| SoftwareApplication | Pages SaaS/app | name, offers |
| FAQPage | Contenu FAQ | mainEntity (tableau Q&R) |
| HowTo | Tutoriels | name, step |
| BreadcrumbList | Toute page avec fil d'Ariane | itemListElement |
| LocalBusiness | Pages d'établissement local | name, address |
| Event | Événements, webinaires | name, startDate, location |

**Pour des exemples JSON-LD complets** : voir [references/schema-examples.md](references/schema-examples.md)

---

## Aide-mémoire

### Organization (page entreprise)
Requis : name, url
Recommandé : logo, sameAs (profils sociaux), contactPoint

### Article/BlogPosting
Requis : headline, image, datePublished, author
Recommandé : dateModified, publisher, description

### Product
Requis : name, image, offers (price + availability)
Recommandé : sku, brand, aggregateRating, review

### FAQPage
Requis : mainEntity (tableau de paires Question/Answer)

### BreadcrumbList
Requis : itemListElement (tableau avec position, name, item)

---

## Plusieurs types de schema

Vous pouvez combiner plusieurs types de schema sur une page avec `@graph` :

```json
{
  "@context": "https://schema.org",
  "@graph": [
    { "@type": "Organization", ... },
    { "@type": "WebSite", ... },
    { "@type": "BreadcrumbList", ... }
  ]
}
```

---

## Validation et test

### Outils
- **Google Rich Results Test** : https://search.google.com/test/rich-results
- **Schema.org Validator** : https://validator.schema.org/
- **Search Console** : rapports Enhancements

### Erreurs fréquentes

**Propriétés requises manquantes** - Vérifier la documentation de Google pour les champs requis

**Valeurs invalides** - Les dates doivent être en ISO 8601, les URL pleinement qualifiées, les énumérations exactes

**Décalage avec le contenu de la page** - Le schema ne correspond pas au contenu visible

---

## Implémentation

### Sites statiques
- Ajouter le JSON-LD directement dans le template HTML
- Utiliser des includes/partials pour le schema réutilisable

### Sites dynamiques (React, Next.js)
- Composant qui rend le schema
- Rendu côté serveur pour le SEO
- Sérialiser les données en JSON-LD

### CMS / WordPress
- Plugins (Yoast, Rank Math, Schema Pro)
- Modifications du thème
- Champs personnalisés vers données structurées

---

## Format de sortie

### Implémentation du schema
```json
// Bloc de code JSON-LD complet
{
  "@context": "https://schema.org",
  "@type": "...",
  // Markup complet
}
```

### Checklist de test
- [ ] Validé dans le Rich Results Test
- [ ] Pas d'erreurs ni d'avertissements
- [ ] Correspond au contenu de la page
- [ ] Toutes les propriétés requises incluses

---

## Questions spécifiques à la tâche

1. Quel type de page est-ce ?
2. Quels rich results espérez-vous obtenir ?
3. Quelles données sont disponibles pour remplir le schema ?
4. Y a-t-il du schema existant sur la page ?
5. Quelle est votre stack technique ?

---

## Skills liés

- **seo-audit** : Pour le SEO global, y compris la revue du schema
- **ai-seo** : Pour l'optimisation de la recherche IA (le schema aide l'IA à comprendre le contenu)
- **programmatic-seo** : Pour du schema en template à grande échelle
- **site-architecture** : Pour la structure du fil d'Ariane et la planification du schema de navigation
