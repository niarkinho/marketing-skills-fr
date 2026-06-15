# Planification budgétaire — Méthodes scientifiques pour fixer le budget marketing

Le problème avec la plupart des budgets marketing SaaS, c'est qu'ils sont sortis du chapeau — un chiffre qui, on l'espère, ne contraindra pas trop la croissance, mais qui ne s'ancre pas non plus dans l'économie d'acquisition client. Résultat : quand quelqu'un demande « pourquoi ce chiffre ? », il n'y a pas de réponse.

Deux méthodes scientifiques résolvent ça. Utiliser l'une (pas les deux) en Section 8 (Revenu) et Section 10 (perspective 12 mois) de chaque plan.

Extrait et adapté de *Founding Marketing* de Corey Haines.

## Méthode 1 — Basée sur le revenu (5–40 % du revenu annuel)

**Direction :** budget → objectif de revenu.

On part de ce que l'entreprise peut dépenser confortablement en marketing, puis on prévoit le revenu que cette dépense peut plausiblement générer.

### Les fourchettes

| Posture | % de l'ARR | Quand l'utiliser |
|---|---|---|
| **Conservatrice (préservation du profit)** | 5 % | Business établi axé sur la distribution de profit ; bootstrappé ; base clients financée par le fondateur |
| **Croissance standard** | 15–25 % | La plupart des SaaS sains dans la fourchette seed-à-Série-A |
| **Croissance agressive (déploiement de capital levé)** | jusqu'à 40 % | Tour récemment financé, mandat de déployer vite, le board accepte le burn |

Pour référence : les entreprises SaaS cotées reportent régulièrement une dépense sales-and-marketing entre 20 % et 55 % du revenu (Zoom a historiquement tourné entre 20 % et 55 % selon les années).

### Le calcul (exemple conservateur)

Business à 1M$ d'ARR, allocation 5 % :

- Budget marketing annuel : **50 000 $**
- CAC blended : 100 $ → peut acquérir **500 nouveaux clients**
- ARPC : 50 $/mois → ajoute **300K$** à l'ARR
- Tenir compte de 15 % de churn annuel → 85 % × 300K$ = **+255K$ de net new ARR**
- Objectif de fin d'année : **1,255M$ d'ARR**

### Le calcul (exemple agressif)

Business à 1M$ d'ARR, allocation 40 % :

- Budget marketing annuel : **400 000 $**
- CAC blended : 100 $ → peut acquérir **4 000 nouveaux clients**
- ARPC : 50 $/mois → ajoute **2,4M$** à l'ARR
- Objectif de fin d'année : **3,4M$ d'ARR**

### Deux clés pour faire marcher cette méthode

1. **Connaître votre CAC blended** (voir « Calculer le CAC » plus bas)
2. **Faire correspondre le pourcentage d'allocation à votre ambition réelle.** Un fondateur qui tourne à 5 % d'allocation tout en disant au board qu'il compte tripler le revenu envoie deux signaux incompatibles.

## Méthode 2 — Basée sur l'objectif (rétro-ingénierée à partir de la cible de revenu)

**Direction :** objectif de revenu → budget.

On part de l'objectif de revenu et on remonte à travers les unit economics pour déduire le budget requis pour l'atteindre. Idéale pour :

- Les entreprises qui démarrent (pas encore de baseline CAC historique, on travaille depuis les premiers principes)
- Les entreprises anticipant un capital externe (besoin de défendre la demande)
- Les entreprises utilisant le revenue-based financing (Pipe, Capchase, Founderpath)

### La formule

```
Budget marketing = [(Nouvel ARR / (ARPC × 12)) × CAC] / taux de rétention annuel
```

### Exemple chiffré : 1M$ d'ARR → 2M$ d'ARR

Étape 1 — Combien de nouvel ARR par client ?
ARPC × 12 = 50 $ × 12 = **600 $ d'ARR par nouveau client**

Étape 2 — Combien de nouveaux clients faut-il ?
1 000 000 $ / 600 $ = **1 667 nouveaux clients**

Étape 3 — Quel est le coût d'acquisition brut ?
1 667 × 100 $ de CAC = **166 700 $**

Étape 4 — Tenir compte du churn (15 % annuel = 85 % de rétention)
166 700 $ / 0,85 = **196 118 $** (arrondi à **200K$**)

Quand quelqu'un demande comment vous êtes arrivé au budget, déroulez les quatre étapes. C'est défendable.

### Pourquoi cette formule et pas quelque chose de plus simple

Les quatre étapes correspondent chacune à une réalité économique :
- L'étape 1 convertit le langage MRR dans le langage ARR que parle un board
- L'étape 2 nomme le nombre de clients, qui est ce que le funnel doit réellement délivrer
- L'étape 3 ancre le budget dans le coût d'acquisition
- L'étape 4 reconnaît que les clients churnés ne comptent pas dans le net new ARR, donc le budget doit couvrir l'écart

### Buffer requis

**Toujours ajouter 10–20 % de « budget expérimental »** par-dessus la sortie de la formule. Le CAC est la dépendance principale ; si le CAC arrive 50 % plus haut qu'estimé, l'effet en cascade est de manquer l'objectif de revenu. Il est bien moins cher de surestimer le CAC que de le sous-estimer.

Le budget expérimental finance aussi les expériences qui trouvent votre prochain canal avant que l'actuel ne plafonne (voir `growth-patterns.md` — courbes en S des canaux).

## Le chemin de croissance VC (règle du 3-3-2-2-2)

Une fois qu'une entreprise a franchi 1M$ d'ARR et levé une Série A, le benchmark implicite attendu par les VC est :

| Année | Multiple d'ARR | ARR cumulé (depuis 1M$ de départ) |
|---|---|---|
| Année 0 | — | 1M$ |
| Année +1 | 3× | 3M$ |
| Année +2 | 3× | 9M$ |
| Année +3 | 2× | 18M$ |
| Année +4 | 2× | 36M$ |
| Année +5 | 2× | 72M$ |
| Année +6 | 2× | 144M$ |
| Année +7 | 2× | 288M$ |

C'est la règle du 3-3-2-2-2. Utile quand :

- Le plan doit mapper des jalons 12 mois et 36 mois aux attentes VC
- Le fondateur est en cours de levée et le board doit voir un chemin plausible vers le prochain tour
- La Section 10 (perspective 12 mois) a besoin d'être ancrée sur un benchmark sectoriel, pas seulement sur l'ambition interne

La plupart des entreprises le ratent. C'est normal. Connaître le benchmark donne à l'équipe une raison défendable de soit l'égaler, soit choisir explicitement de ne pas le faire.

## Calculer le CAC (blended, pas paid-only)

S'il n'y a pas de CAC historique, utiliser une baseline : **un an de revenu du plus petit plan payant.** Déployer le budget, capturer les données CAC réelles, remplacer la baseline par le chiffre mesuré pour le prochain cycle de planification.

Pour un calcul de CAC établi, **le CAC doit être blended.** Inclure :

- Salaires marketing (coût pleinement chargé, pas seulement le salaire de base)
- Dépense publicitaire
- Coûts de la marketing tech stack
- Coûts de production de contenu (rédacteurs, designers, monteurs vidéo)
- Retainers agence / contractors
- Salaires SDR / BDR si vous faites de l'outbound
- Outils (CRM, marketing automation, analytics)

Puis diviser par le nombre de nouveaux clients acquis sur la période. Ce chiffre blended est celui à utiliser dans l'une ou l'autre méthode de budgétisation.

L'erreur à éviter : calculer le CAC à partir de la seule dépense pub. Une entreprise qui « ne fait pas de pub » a quand même un CAC — il est juste caché dans l'équipe contenu, le temps du fondateur, le contractor SEO, le stand en conférence.

## Le reality check sur la prévision

Tout ce framework dérive un budget et un objectif de revenu — pas une prévision 12 mois mois-par-mois exacte au dollar près.

**Sauf si l'entreprise est cotée en bourse, toutes les prévisions sont des suppositions éclairées.** Aucune startup sous 100M$ d'ARR n'atteint de façon fiable ses prévisions au mois près. Le cadrage honnête pour le plan :

- L'objectif annuel est une direction-de-déplacement défendable
- Le budget est l'engagement de ressources qui rend l'objectif plausible
- La roadmap 90 jours (Section 9) est ce qui est actionnable maintenant
- La variance mois-à-mois est attendue ; la revue trimestrielle est le moment où le plan s'ajuste

Ce qui est actionnable : comment déployer le budget, quels mouvements concrets exécuter, quoi ajuster quand les vraies données arrivent.

Ce qui n'est pas actionnable : essayer de prévoir trafic, pipeline, courbes de rétention, taux de conversion et mix de canaux jusqu'à la décimale et attendre que cette prévision tienne. Les fondateurs qui sur-ingénierent la prévision tendent à passer la période du plan à expliquer la variance au lieu d'exécuter.

**Règle pour le plan :** le chiffre du budget est honnête. L'objectif annuel est honnête. La projection mois-par-mois est illustrative.

## Comment ça s'intègre dans le plan

| Section | Quoi inclure |
|---|---|
| **3 (État actuel)** | Dépense marketing mensuelle actuelle ventilée par ligne (paid, outils, contenu, effectifs, retainers). Calculer l'allocation actuelle en %-de-l'ARR. |
| **8 (Revenu)** | La table d'unit economics (CAC, ARPC, churn) qui alimente la méthode de budget retenue. |
| **10 (Perspective 12 mois)** | Appliquer la Méthode 1 ou la Méthode 2 pour dériver le budget 12 mois et l'objectif de revenu qui en résulte. Ancrer sur la règle du 3-3-2-2-2 si Série A+ et VC-backed. |
| **11 (Ops stack)** | Montrer l'allocation du budget entre les stades AARRR — quel % à l'Acquisition, à l'Activation, etc. Le mapping ops-stack informe quelles lignes croissent quand le prochain tier de financement se débloque. |
| **13 (Décisions ouvertes)** | Si le CAC est inconnu ou contesté, le flagger comme la décision ouverte la plus impactante — tout autre chiffre en dépend. |

## Quand choisir quelle méthode

- **Méthode 1 (Basée sur le revenu)** quand l'entreprise a des données CAC historiques, une posture profit/burn, et que la question est « compte tenu de notre posture, quel est un objectif plausible ».
- **Méthode 2 (Basée sur l'objectif)** quand l'entreprise a un objectif précis (mandat du board, jalon VC, cible de levée) et que la question est « quel budget nous faut-il pour l'atteindre ».

Pour la plupart des plans dans la fourchette seed-à-Série-A, la Méthode 2 est plus utile — elle force la conversation sur le fait de savoir si l'objectif est financé.
