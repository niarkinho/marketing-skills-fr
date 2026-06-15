# AI SEO par type de contenu

Conseils tactiques pour optimiser des types de contenu spécifiques en vue de la citation par la recherche IA. Ces tactiques fonctionnent pour les moteurs IA non-Google (ChatGPT, Claude, Perplexity, Copilot) et ne nuisent pas à Google AI Overviews / AI Mode.

Pour la stratégie transversale, voir [SKILL.md](../SKILL.md).

---

## Pages produit SaaS

**Objectif :** Se faire citer dans les requêtes « Qu'est-ce que [catégorie] ? » et « Meilleur [catégorie] ».

**Optimiser :**
- Description produit claire dans le premier paragraphe (ce qu'il fait, à qui il s'adresse)
- Tableaux comparatifs de fonctionnalités (vous vs. la catégorie, pas seulement les concurrents)
- Métriques précises (« traite 10 000 transactions/sec » et non « ultra rapide »)
- Nombre de clients ou preuve sociale chiffrée
- Transparence des tarifs (l'IA cite les pages dont les tarifs sont visibles) — ajoutez un fichier `/pricing.md` pour que les agents IA puissent analyser vos offres sans rendre votre page (voir « Fichiers lisibles par machine » dans le skill principal)
- Section FAQ répondant aux questions fréquentes des acheteurs

---

## Contenu de blog

**Objectif :** Se faire citer comme source faisant autorité sur les sujets de votre domaine.

**Optimiser :**
- Une requête cible claire par article (faire correspondre le titre à la requête)
- Définition dans le premier paragraphe pour les requêtes « Qu'est-ce que »
- Données, recherches ou citations d'experts originales
- Date de « dernière mise à jour » visible
- Bio d'auteur avec des qualifications pertinentes
- Liens internes vers les pages produit/fonctionnalité liées

---

## Pages comparatif / alternative

**Objectif :** Se faire citer dans les requêtes « [X] vs [Y] » et « Meilleures alternatives à [X] ».

**Optimiser :**
- Tableaux comparatifs structurés (pas seulement de la prose)
- Justes et équilibrés (l'IA pénalise les comparaisons manifestement biaisées)
- Critères précis avec notes ou scores
- Tarifs et données de fonctionnalités à jour
- Renvoyer au skill `competitors` pour construire ces pages

---

## Documentation / contenu d'aide

**Objectif :** Se faire citer dans les requêtes « Comment faire [X] avec [votre produit] ».

**Optimiser :**
- Format étape par étape avec listes numérotées
- Exemples de code le cas échéant
- Schema markup HowTo
- Captures d'écran avec un texte alt descriptif
- Prérequis clairs et résultats attendus

---

## Commerce local / e-commerce (accent de Google)

Les fonctionnalités IA de Google tirent des flux produit et des fiches d'établissement pour les requêtes locales + e-commerce. Optimiser :

- **Flux Merchant Center** maintenus à jour avec un stock, des tarifs et des attributs exacts
- **Google Business Profile** complet avec horaires, services, photos, posts, Q&R répondues
- **Avis** — récents + en volume suffisant ; répondre aux avis pour signaler une gestion active
- **Schema de zone de service** pour les services locaux
- **Business Agent** (le cas échéant) pour l'engagement client conversationnel
