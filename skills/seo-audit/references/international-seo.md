# SEO international : preuves & sources

Preuves détaillées étayant la section SEO international & localisation du skill SEO Audit. Organisé par sujet avec les URL des sources et les citations clés.

---

## Hreflang

### Méthodes de placement

Google supporte trois méthodes équivalentes : `<link>` HTML dans le `<head>`, en-têtes HTTP `Link`, et éléments `<xhtml:link>` du sitemap XML. Google a confirmé qu'aucune méthode n'est priorisée sur une autre.

Google combine les signaux du HTML et des sitemaps. Si la même paire langue-région pointe vers des URL différentes selon les méthodes, Google abandonne cette paire plutôt que de deviner.

- [Google Search Central: Localized Versions](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [SEJ: Google Combines Hreflang Signals](https://www.searchenginejournal.com/google-combines-hreflang-signals-from-html-sitemaps/389219/)

### Exigence de réciprocité

Doc Google : « Si la page X pointe vers la page Y, la page Y doit pointer en retour vers la page X. Sinon, ces annotations peuvent être ignorées ou mal interprétées. »

Chaque page doit s'inclure elle-même (auto-référence) dans le set hreflang. L'absence d'auto-référence est l'erreur n°1 relevée par les audits Semrush. Une étude de 374 756 domaines a constaté que 67 % des implémentations hreflang présentaient des problèmes.

- [Google Search Central: Localized Versions](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Semrush: 9 Common Hreflang Errors](https://www.semrush.com/blog/hreflang-errors/)
- [SE Land: 31% of International Websites Contain Hreflang Errors](https://searchengineland.com/study-31-of-international-websites-contain-hreflang-errors-395161)

### x-default

Introduit en avril 2013. Désigne la page de repli pour les utilisateurs dont la langue/région ne correspond à aucune variante déclarée. Peut pointer vers la même URL que l'un des alternates spécifiques à une langue. Doit figurer dans le set complet d'annotations sur chaque page variante.

- [Google Blog: x-default hreflang](https://developers.google.com/search/blog/2013/04/x-default-hreflang-for-international-pages)
- [Google Blog: How x-default can help you (2023)](https://developers.google.com/search/blog/2023/05/x-default)

### Codes de langue et de région

Langue : ISO 639-1 (2 lettres). Région : ISO 3166-1 Alpha 2 (2 lettres). Format : `langue[-script][-région]`.

Vous ne pouvez pas spécifier un code de région seul. Erreurs fréquentes : `en-UK` (devrait être `en-GB`), `es-419` (pas ISO 3166-1). Une étude a constaté que 8,9 % des sites utilisant hreflang contiennent des codes de langue invalides.

- [Google Search Central: Localized Versions](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [SE Land: 31% Study](https://searchengineland.com/study-31-of-international-websites-contain-hreflang-errors-395161)

### Hreflang à grande échelle (20+ locales)

Avec 20 locales, le hreflang en `<head>` HTML ajoute ~1,5 Ko par page pour zéro bénéfice utilisateur. Le hreflang via sitemap a un impact de performance nul à l'exécution. Les éléments enfants `<xhtml:link>` ne comptent PAS dans la limite de 50 000 URL du sitemap (seuls les éléments `<loc>` comptent).

John Mueller recommande de concentrer le hreflang sur les pages recevant du trafic dans la mauvaise langue, pas sur chaque page : « Je ne le ferais pas pour les autres pages du site car c'est tellement complexe et difficile à gérer. »

- [SERoundtable: Child Elements Don't Count](https://www.seroundtable.com/google-child-elements-dont-count-towards-sitemap-url-limit-34377.html)
- [SERoundtable: Where To Focus Hreflang](https://www.seroundtable.com/using-hreflang-34127.html)
- [Yoast: hreflang Ultimate Guide](https://yoast.com/hreflang-ultimate-guide/)

### Google vs Bing

Bing traite le hreflang comme un « signal faible ». Bing s'appuie sur la balise meta `content-language`, l'attribut HTML `lang`, les ccTLD et la localisation du serveur. Yandex supporte le hreflang comme Google.

Pour les deux moteurs : implémenter le hreflang (Google/Yandex) + `<html lang="...">` + `<meta http-equiv="content-language">` (Bing).

- [Digital Ready Marketing: Bing Doesn't Use Hreflang](https://digitalreadymarketing.com/bing-doesnt-use-hreflang-annotation-what-does-it-use/)
- [Yoast: hreflang Ultimate Guide](https://yoast.com/hreflang-ultimate-guide/)

---

## Canonicalisation & i18n

### Canonicals auto-référencées

Chaque page de locale doit se canonicaliser vers elle-même. John Mueller : « N'utilisez pas un rel=canonical entre langues/pays, utilisez-le uniquement par pays/langue. »

Doc Google : « Spécifiez une page canonique dans la même langue, ou la meilleure langue de substitution possible si une canonique n'existe pas pour la même langue. »

- [John Mueller: hreflang canonical](https://johnmu.com/hreflang-canonical/)
- [Google: Consolidate Duplicate URLs](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)

### Le canonical prime sur le hreflang

Mueller : « Si votre canonical pointe ailleurs, Google le suivra et ignorera votre annotation hreflang. » L'URL canonique doit être l'une des URL du set hreflang, sinon tout le markup hreflang est ignoré.

Google précise aussi : « Google préfère les URL faisant partie de clusters hreflang pour la canonicalisation » — quand les signaux s'alignent, le hreflang renforce la sélection du canonical.

- [John Mueller: hreflang canonical](https://johnmu.com/hreflang-canonical/)
- [SEJ: Hreflang Tags Are Hints](https://www.searchenginejournal.com/google-reminds-that-hreflang-tags-are-hints-not-directives/546428/)
- [Google: Consolidate Duplicate URLs](https://developers.google.com/search/docs/crawling-indexing/consolidate-duplicate-urls)

### Variantes régionales quasi-dupliquées

Mueller (Office Hours 2023) : « Si le contenu est complètement identique, et qu'on ne peut faire aucune différence, alors pour la simplicité et l'expérience utilisateur on peut n'afficher qu'une version — même si le hreflang est présent. »

La détection de doublons de Google s'exécute AVANT l'évaluation du hreflang. Pour garder les deux versions indexées, il faut des différences de contenu substantielles au-delà des symboles de devise.

- [International Web Mastery: Same-Language Duplicate Pages](https://internationalwebmastery.com/blog/how-google-handles-canonicalization-of-same-language-duplicate-near-duplicate-pages/)
- [Google: Managing Multi-Regional Sites](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)

### Pagination selon les locales

Google : « N'utilisez pas la première page d'une séquence paginée comme page canonique. Donnez plutôt à chaque page sa propre URL canonique. » Chaque page paginée de chaque locale reçoit un canonical auto-référencé. `rel="next/prev"` déprécié en mars 2019.

- [Google: Pagination Best Practices](https://developers.google.com/search/docs/specialty/ecommerce/pagination-and-incremental-page-loading)

---

## Sitemaps internationaux

### Structure

Chaque entrée `<url>` inclut des alternates `<xhtml:link>` pour chaque locale. Requiert le namespace `xmlns:xhtml="http://www.w3.org/1999/xhtml"`.

Découpez les sitemaps par type de contenu, pas par locale. Découper par locale crée des problèmes de maintenance car chaque sitemap de locale doit référencer toutes les autres locales (exigence de réciprocité).

- [Google Search Central: Localized Versions](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Lumar: How Google Handles Hreflang](https://www.lumar.io/office-hours/hreflang/)

### Limites de taille

50 000 URL / 50 Mo décompressés par sitemap. Seuls les éléments `<loc>` comptent dans la limite de 50K. Mais avec 20 alternates hreflang par entrée, la limite de taille de fichier de 50 Mo devient le goulot d'étranglement. Prévoyez 2 000 à 5 000 URL par sitemap avec hreflang complet.

- [Google: Build and Submit a Sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)
- [SERoundtable: Sitemap 50,000 Limit](https://www.seroundtable.com/google-sitemap-50-000-limit-based-on-location-urls-not-alternative-urls-33843.html)

### Soumission

Soumettez l'index de sitemap dans la Search Console ET référencez-le dans le robots.txt. Les sitemaps enfants individuels peuvent être soumis séparément pour un reporting par sitemap.

- [Google: Build and Submit a Sitemap](https://developers.google.com/search/docs/crawling-indexing/sitemaps/build-sitemap)

### Précaution Next.js

`alternates.languages` de Next.js n'inclut PAS automatiquement un `<xhtml:link>` auto-référencé pour l'URL `<loc>`. Vous devez inclure explicitement la langue de l'URL `<loc>` elle-même dans l'objet `languages`.

- [Next.js Docs: sitemap.xml](https://nextjs.org/docs/app/api-reference/file-conventions/metadata/sitemap)

---

## Structure des URL

### Comparaison des stratégies

Google traite les sous-répertoires et les sous-domaines de façon équivalente. Mueller : « De notre point de vue... on dit que les sous-domaines et les sous-répertoires sont essentiellement équivalents. »

Les paramètres d'URL (`?lang=en`) sont explicitement « Non recommandés » selon la doc Google.

- [Google: Managing Multi-Regional Sites](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)

### Langue par défaut

Mueller recommande : définir `/` comme x-default, mettre chaque langue dans son propre préfixe. Sans marquer `/` comme x-default, « pour Google, '/' peut ressembler à une page distincte des autres. »

- [Google Blog: x-default](https://developers.google.com/search/blog/2023/05/x-default)
- [Google Blog: Creating the Right Homepage](https://developers.google.com/search/blog/2014/05/creating-right-homepage-for-your)

### Négociation de contenu / redirections IP

Google déconseille fortement les pages adaptatives à la locale. Googlebot crawle depuis des IP US et n'envoie pas d'en-têtes Accept-Language. Des URL séparées + hreflang sont requises.

- [Google: Locale-Adaptive Pages](https://developers.google.com/search/docs/specialty/international/locale-adaptive-pages)

### Cohérence du slash final

Mueller : le slash final est « une partie significative de l'URL et change l'URL selon qu'il est présent ou non. » Choisissez un seul format pour tous les chemins de locale, liens internes, canonicals, hreflang et sitemaps.

Mueller (2025) : « La cohérence est le plus grand facteur de SEO technique. »

- [SERoundtable: Consistency Is The Biggest Technical SEO Factor](https://www.seroundtable.com/google-consistency-seo-40427.html)

### Geotargeting Search Console

Le rapport International Targeting est déprécié. Google s'appuie désormais entièrement sur le hreflang, l'analyse de la langue du contenu et les schémas de liens. Vous pouvez ajouter des propriétés de sous-répertoire pour un reporting par locale.

- [Google Support: International Targeting Deprecated](https://support.google.com/webmasters/answer/12474899?hl=en)

### Modes de locale des frameworks

Utilisez `localePrefix: 'always'` (next-intl) ou équivalent. Ne cachez jamais la locale des URL — Google a besoin d'URL uniques par langue. Le mode `'never'` désactive entièrement les liens alternate.

- [next-intl: Routing Configuration](https://next-intl.dev/docs/routing/configuration)
- [Next.js Discussion #18419](https://github.com/vercel/next.js/discussions/18419)

---

## Qualité du contenu selon les locales

### Contenu auto-traduit (position 2025)

Google a retiré mi-2025 sa consigne de longue date déconseillant le contenu auto-traduit. Position actuelle : « Nos politiques ne définissent pas strictement comme spam le contenu traduit par IA. » La politique « scaled content abuse » mentionne la traduction comme vecteur possible, mais ne l'interdit pas.

Reddit a fait passer ses traductions IA à 35+ langues au su de Google. La distinction clé est l'intention et la qualité, pas la méthode.

- [Google Spam Policies](https://developers.google.com/search/docs/essentials/spam-policies)
- [Glenn Gabe: Auto-Translating Content](https://www.gsqi.com/marketing-blog/auto-translating-content-google-scaled-content-abuse/)
- [SE Land: Reddit AI Translations](https://searchengineland.com/google-comments-on-reddits-use-of-ai-to-translate-its-pages-456908)

### Pages de locale légères

Google : « Les versions localisées d'une page ne sont considérées comme des doublons que si le contenu principal de la page reste non traduit. » Les pages avec seulement du boilerplate traduit sont regroupées comme doublons.

N'utilisez PAS noindex pour les pages de locale non désirées (gaspille le crawl budget). Ne canonicalisez PAS inter-locale (entre en conflit avec le hreflang). Meilleure approche : ne pas créer de pages de locale que vous ne pouvez pas rendre réellement utiles.

- [Google: Localized Versions](https://developers.google.com/search/docs/specialty/international/localized-versions)
- [Google: Crawl Budget Management](https://developers.google.com/search/docs/crawling-indexing/large-site-managing-crawl-budget)

### Impact du système Helpful Content

Fusionné dans le classement central en mars 2024. Signal à l'échelle du site : « tout contenu — pas seulement le contenu peu utile — sur des sites jugés comme ayant des quantités relativement élevées de contenu peu utile dans l'ensemble a moins de chances de bien performer dans Search. »

Des pages traduites de faible qualité peuvent plomber tout le site. C'est l'argument le plus fort contre la création de pages de locale qui ne sont pas réellement utiles.

- [Google Blog: Helpful Content Update](https://developers.google.com/search/blog/2022/08/helpful-content-update)
- [Amsive: What Changed in 2024](https://www.amsive.com/insights/seo/googles-helpful-content-update-ranking-system-what-happened-and-what-changed-in-2024/)

### Traduction partielle

Google : « Traduire seulement le texte boilerplate de vos pages tout en gardant l'essentiel de votre contenu dans une seule langue... peut créer une mauvaise expérience utilisateur. » Google utilise le contenu visible (pas l'attribut lang) pour déterminer la langue de la page.

Traduisez TOUT le contenu d'une page si vous créez une version de locale. Des métadonnées non traduites (titre, description) dans la mauvaise langue réduisent le CTR.

- [Google: Managing Multi-Regional Sites](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)

### Crawl budget

Une préoccupation seulement pour 1M+ pages ou 10K+ pages changeant quotidiennement. Mais les URL alternate (cibles hreflang) consomment du crawl budget. Les liens hreflang cassés gaspillent du budget ET invalident les signaux.

- [Google: Crawl Budget Management](https://developers.google.com/search/docs/crawling-indexing/large-site-managing-crawl-budget)
- [Google Blog: Crawl Budget](https://developers.google.com/search/blog/2017/01/what-crawl-budget-means-for-googlebot)

### Signaux propres à la locale

Google identifie l'audience via : « les adresses et numéros de téléphone locaux sur les pages, l'usage de la langue et de la devise locales, les liens depuis d'autres sites locaux, ou les signaux de votre Business Profile. »

- [Google: Managing Multi-Regional Sites](https://developers.google.com/search/docs/specialty/international/managing-multi-regional-sites)
