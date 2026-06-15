# Comment chaque plateforme IA choisit ses sources

Chaque plateforme de recherche IA a son propre index de recherche, sa logique de classement et ses préférences de contenu. Ce guide couvre ce qui compte pour se faire citer sur chacune.

Sources citées tout au long : étude GEO de Princeton (KDD 2024), étude SE Ranking sur l'autorité de domaine, analyse ZipTie sur l'adéquation contenu-réponse.

---

## Les fondamentaux

Chaque plateforme IA partage trois prérequis de base :

1. **Votre contenu doit être dans leur index** — Chaque plateforme utilise un backend de recherche différent (Google, Bing, Brave ou le sien). Si vous n'êtes pas indexé, vous ne pouvez pas être cité.
2. **Votre contenu doit être crawlable** — Les bots IA ont besoin d'un accès via robots.txt. Bloquez le bot, perdez la citation.
3. **Votre contenu doit être extractible** — Les systèmes IA tirent des passages, pas des pages. Une structure claire et des paragraphes autonomes l'emportent.

Au-delà de ces bases, chaque plateforme pondère des signaux différents. Voici ce qui compte et où.

---

## Google AI Overviews

Google AI Overviews puise dans l'index propre de Google et s'appuie fortement sur les signaux E-E-A-T (Experience, Expertise, Authoritativeness, Trustworthiness). Ils apparaissent dans environ 45 % des recherches Google.

**Ce qui rend Google AI Overviews différent :** Ils disposent déjà de vos signaux SEO classiques — backlinks, autorité de page, pertinence thématique. La couche IA supplémentaire ajoute une préférence pour le contenu avec sources citées et données structurées. La recherche montre que l'inclusion de citations faisant autorité dans votre contenu corrèle avec un gain de visibilité de 132 %, et écrire avec un ton qui fait autorité (pas commercial) ajoute encore 89 %.

**Important, les AI Overviews ne recyclent pas simplement le Top 10 classique.** Seuls environ 15 % des sources d'AI Overview recoupent les résultats organiques conventionnels. Des pages qui ne perceraient pas en page 1 dans la recherche classique peuvent quand même être citées si elles ont de solides données structurées et des réponses claires et extractibles.

**Sur quoi se concentrer :**
- Le schema markup est le plus gros levier — les schemas Article, FAQPage, HowTo et Product donnent aux AI Overviews un contexte structuré exploitable (30-40 % de gain de visibilité)
- Construire une autorité thématique via des clusters de contenu avec un fort maillage interne
- Inclure des citations nommées et sourcées dans votre contenu (pas seulement des affirmations)
- Les bios d'auteurs avec de vraies qualifications comptent — l'E-E-A-T est fortement pondéré
- Entrer dans le Knowledge Graph de Google quand c'est possible (une fiche Wikipedia exacte aide)
- Cibler les schémas de requête « comment faire » et « qu'est-ce que » — ce sont eux qui déclenchent le plus souvent les AI Overviews

---

## ChatGPT

La recherche web de ChatGPT puise dans un index basé sur Bing. Il la combine avec sa connaissance d'entraînement pour générer ses réponses, puis cite les sources web sur lesquelles il s'est appuyé.

**Ce qui rend ChatGPT différent :** L'autorité de domaine compte davantage ici que sur les autres plateformes IA. Une analyse SE Ranking de 129 000 domaines a montré que les signaux d'autorité et de crédibilité représentent environ 40 % de ce qui détermine la citation, avec la qualité du contenu à environ 35 % et la confiance de la plateforme à 25 %. Les sites avec un très grand nombre de domaines référents (350K+) obtiennent en moyenne 8,4 citations par réponse, tandis que les sites avec des scores de confiance légèrement inférieurs (91-96 vs 97-100) passent de 8,4 à 6 citations.

**La fraîcheur est un différenciateur majeur.** Le contenu mis à jour dans les 30 derniers jours est cité environ 3,2x plus souvent que le contenu plus ancien. ChatGPT favorise clairement l'information récente.

**Le signal le plus important est l'adéquation contenu-réponse** — une analyse ZipTie de 400 000 pages a montré qu'à quel point le style et la structure de votre contenu correspondent au propre format de réponse de ChatGPT représente environ 55 % de la probabilité de citation. C'est bien plus important que l'autorité de domaine (12 %) ou la structure on-page (14 %) seules. Écrivez comme ChatGPT répondrait à la question, et vous avez plus de chances d'être la source qu'il cite.

**Là où ChatGPT regarde au-delà de votre site :** Wikipedia représente 7,8 % de toutes les citations ChatGPT, Reddit 1,8 % et Forbes 1,1 %. Les sites officiels de marque sont cités fréquemment mais les mentions tierces pèsent significativement.

**Sur quoi se concentrer :**
- Investir dans les backlinks et l'autorité de domaine — c'est le signal de base le plus fort
- Mettre à jour le contenu concurrentiel au moins une fois par mois
- Structurer votre contenu comme ChatGPT structure ses réponses (conversationnel, direct, bien organisé)
- Inclure des statistiques vérifiables avec des sources nommées
- Hiérarchie de titres propre (H1 > H2 > H3) avec des titres descriptifs

---

## Perplexity

Perplexity cite toujours ses sources avec des liens cliquables, ce qui en fait la plateforme de recherche IA la plus transparente. Il combine son propre index avec celui de Google et fait passer les résultats par plusieurs passes de reranking — récupération de pertinence initiale, puis scoring sur les facteurs de classement classiques, puis évaluation de qualité par ML qui peut écarter des ensembles de résultats entiers s'ils n'atteignent pas les seuils de qualité.

**Ce qui rend Perplexity différent :** C'est le moteur de recherche IA le plus « orienté recherche », et son comportement de citation le reflète. Perplexity maintient des listes curées de domaines faisant autorité (Amazon, GitHub, grands sites académiques) qui bénéficient de boosts de classement inhérents. Il utilise un algorithme de décroissance temporelle qui évalue rapidement le nouveau contenu, donnant aux éditeurs récents une vraie chance de citation.

**Perplexity a des préférences de contenu uniques :**
- **FAQ Schema (JSON-LD)** — Les pages avec des données structurées FAQ sont citées nettement plus souvent
- **Documents PDF** — Les PDF publiquement accessibles (livres blancs, rapports de recherche) sont priorisés. Si vous avez du contenu PDF faisant autorité gated derrière un formulaire, envisagez d'en rendre une version publique.
- **Vélocité de publication** — La fréquence de publication compte plus que le ciblage de mots-clés
- **Paragraphes autonomes** — Perplexity préfère les paragraphes atomiques, sémantiquement complets, qu'il peut extraire proprement

**Sur quoi se concentrer :**
- Autoriser PerplexityBot dans le robots.txt
- Implémenter le schema FAQPage sur toute page comportant du contenu Q&R
- Héberger des ressources PDF publiquement (livres blancs, guides, rapports)
- Ajouter le schema Article avec horodatages de publication et de modification
- Écrire en paragraphes clairs et autonomes qui fonctionnent comme réponses isolées
- Construire une autorité thématique profonde dans votre niche spécifique

---

## Microsoft Copilot

Copilot est intégré dans tout l'écosystème Microsoft — Edge, Windows, Microsoft 365 et Bing Search. Il s'appuie entièrement sur l'index de Bing, donc si Bing n'a pas indexé votre contenu, Copilot ne peut pas le citer.

**Ce qui rend Copilot différent :** La connexion à l'écosystème Microsoft crée des opportunités d'optimisation uniques. Les mentions et le contenu sur LinkedIn et GitHub procurent des boosts de classement que les autres plateformes n'offrent pas. Copilot accorde aussi plus de poids à la vitesse de page — des temps de chargement sous les 2 secondes sont un seuil clair.

**Sur quoi se concentrer :**
- Soumettre votre site à Bing Webmaster Tools (beaucoup de sites ne soumettent qu'à Google Search Console)
- Utiliser le protocole IndexNow pour une indexation plus rapide du contenu nouveau et mis à jour
- Optimiser la vitesse de page sous les 2 secondes
- Écrire des définitions d'entités claires — quand votre contenu définit un terme ou un concept, rendez la définition explicite et extractible
- Construire une présence sur LinkedIn (publier des articles, entretenir une page entreprise) et GitHub si pertinent
- Veiller à ce que Bingbot ait un accès de crawl complet

---

## Claude

Claude utilise Brave Search comme backend de recherche lorsque la recherche web est activée — ni Google, ni Bing. C'est un index complètement différent, ce qui signifie que votre visibilité sur Brave Search détermine directement si Claude peut vous trouver et vous citer.

**Ce qui rend Claude différent :** Claude est extrêmement sélectif sur ce qu'il cite. Bien qu'il traite d'énormes quantités de contenu, son taux de citation est très bas — il cherche le contenu le plus exact factuellement et le mieux sourcé sur un sujet donné. Le contenu riche en données, avec des chiffres précis et une attribution claire, performe nettement mieux que le contenu généraliste.

**Sur quoi se concentrer :**
- Vérifier que votre contenu apparaît dans les résultats Brave Search (cherchez votre marque et vos termes clés sur search.brave.com)
- Autoriser les user agents ClaudeBot et anthropic-ai dans le robots.txt
- Maximiser la densité factuelle — chiffres précis, sources nommées, statistiques datées
- Utiliser une structure claire et extractible avec des titres descriptifs
- Citer des sources faisant autorité au sein de votre contenu
- Viser à être la source la plus exacte factuellement sur votre sujet — Claude récompense la précision

---

## Autoriser les bots IA dans le robots.txt

Si votre robots.txt bloque un bot IA, cette plateforme ne peut pas citer votre contenu. Voici les user agents à autoriser :

```
User-agent: GPTBot           # OpenAI — propulse la recherche ChatGPT
User-agent: ChatGPT-User     # ChatGPT browsing mode
User-agent: PerplexityBot    # Perplexity AI search
User-agent: ClaudeBot        # Anthropic Claude
User-agent: anthropic-ai     # Anthropic Claude (alternate)
User-agent: Google-Extended   # Google Gemini and AI Overviews
User-agent: Bingbot          # Microsoft Copilot (via Bing)
Allow: /
```

**Entraînement vs. recherche :** Certains bots IA servent à la fois à l'entraînement des modèles et à la citation de recherche. Si vous voulez être cité mais ne voulez pas que votre contenu serve à l'entraînement, vos options sont limitées — GPTBot gère les deux pour OpenAI. Cependant, vous pouvez bloquer en toute sécurité **CCBot** (Common Crawl) sans affecter aucune citation de recherche IA, puisqu'il ne sert qu'à la collecte de jeux de données d'entraînement.

---

## Par où commencer

Si vous optimisez pour la recherche IA pour la première fois, concentrez votre effort là où se trouve réellement votre audience :

**Commencez par Google AI Overviews** — Ils touchent le plus d'utilisateurs (45 %+ des recherches Google) et vous avez probablement déjà des fondations SEO Google en place. Ajoutez le schema markup, incluez des sources citées dans votre contenu et renforcez les signaux E-E-A-T.

**Puis adressez ChatGPT** — C'est l'outil de recherche IA autonome le plus utilisé par les audiences tech et business. Concentrez-vous sur la fraîcheur (mettre à jour le contenu mensuellement), l'autorité de domaine et l'alignement de la structure de votre contenu sur la façon dont ChatGPT met en forme ses réponses.

**Puis élargissez à Perplexity** — Particulièrement précieux si votre audience inclut des chercheurs, des early adopters ou des professionnels tech. Ajoutez le FAQ schema, publiez des ressources PDF et écrivez en paragraphes clairs et autonomes.

**Copilot et Claude sont moins prioritaires** sauf si votre audience penche enterprise/Microsoft (Copilot) ou développeur/analyste (Claude). Mais les fondamentaux — contenu structuré, sources citées, schema markup — aident sur toutes les plateformes.

**Actions qui aident partout :**
1. Autoriser tous les bots IA dans le robots.txt
2. Implémenter le schema markup (FAQPage, Article, Organization au minimum)
3. Inclure des statistiques avec des sources nommées dans votre contenu
4. Mettre à jour le contenu régulièrement — mensuellement pour les sujets concurrentiels
5. Utiliser une structure de titres claire (H1 > H2 > H3)
6. Garder le temps de chargement de page sous les 2 secondes
7. Ajouter des bios d'auteurs avec qualifications
