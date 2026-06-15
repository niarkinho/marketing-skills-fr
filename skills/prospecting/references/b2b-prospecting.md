# Référence prospection B2B

Pour quand l'utilisateur vend à du B2B non-SaaS — services, agences, industriels, entreprises mid-market et grands comptes, cabinets de services professionnels.

---

## Signaux ICP qui comptent (branche B2B)

### Signaux firmographiques

- **Secteur / vertical** — codes NAICS ou SIC si la précision compte
- **Taille de l'entreprise** — tranche d'effectif, tranche de CA, nombre d'établissements
- **Géographie** — pertinente pour les fuseaux horaires, les réglementations, les exigences sur site
- **Business model** — service vs produit vs distribution ; B2B vs B2B2C
- **Actionnariat** — indépendant, détenu par un fonds, coté, familial — influe sur la motion d'achat

### Signaux d'achat

- **Trigger events** : nouvelle recrue C-level, acquisition ou cession récente, IPO/levée de fonds, ouverture d'un nouvel établissement, rebranding récent, annonce d'expansion
- **Signaux fournisseur** : appels d'offres (RFP) publiés publiquement, coûts de changement dans le dernier rapport trimestriel, fenêtres de renouvellement de contrat
- **Signaux opérationnels** : licenciements récents (pression sur les coûts) ou recrutement rapide (pression sur la capacité)
- **Mentions presse** : lancement d'une nouvelle initiative, entrée sur un nouveau marché, changement réglementaire forçant l'action
- **RP / presse** : tout ce qui signale « cette entreprise est en train de changer en ce moment »

### Signaux de déclin

- Faillites multiples ou activités siphonnées par un fonds
- Croissance négative + gros titres sur les réductions de coûts
- Stagnation de l'actionnariat (petite entreprise familiale, pas d'incitation à la croissance)
- Turnover des acheteurs (3+ directeurs marketing en 2 ans)

---

## Sources de découverte (branche B2B)

### Tier 1 — découverte principale

- **Apollo** : meilleure découverte firmographique + contacts B2B généralistes
- **ZoomInfo** : B2B grands comptes + signaux d'intention (mid-market et plus)
- **LinkedIn Sales Navigator** : recherche par secteur + fonction + signal ; la référence absolue pour la cartographie des décideurs (manuelle)
- **Clay** : quand il faut des lookups en waterfall custom (ex : enrichir des fiches Apollo avec Hunter + Clearbit)

### Tier 2 — annuaires sectoriels

- **Crunchbase / Pitchbook** : entreprises financées
- **D&B Hoovers** : données firmographiques B2B traditionnelles à grande échelle
- **Registres d'entreprises nationaux / régionaux** : pour des données d'immatriculation vérifiées
- **Annuaires de membres d'associations professionnelles** : les groupements sectoriels publient souvent leurs listes de membres
- **Listes d'exposants de salons professionnels** : signalent une participation active à un vertical
- **Bases de données achats** (Procore pour le BTP, par ex.) : signaux propres à un vertical

### Tier 3 — veille des trigger events

- **Google Alerts / Feedly** : mots-clés déclencheurs (« acquired », « hires », « expansion », « raises », « announces »)
- **PR Newswire / Business Wire** : annonces contrôlées par l'entreprise
- **Documents SEC** (entreprises cotées) : déclarations de changement matériel
- **Dépôts officiels** : création de nouvelle entité, dissolution

---

## Checklist de qualification (branche B2B)

- [ ] Secteur / vertical correspond à l'ICP (utiliser une classification reconnue si possible)
- [ ] Taille de l'entreprise dans la fourchette (effectif ou CA)
- [ ] Géographie compatible
- [ ] Au moins un trigger event dans les 90–180 derniers jours
- [ ] Une fonction de décideur existe (CEO, COO, VP Operations, Directeur de X — matcher le profil acheteur)
- [ ] Contact email vérifiable (fonction nominative > catchall info@)
- [ ] URL sources capturées pour les affirmations firmographiques
- [ ] Aucun critère disqualifiant (fermée, acquise-en-pause, faillites multiples, hors ICP)

---

## Colonnes de sortie (branche B2B)

Colonnes CSV recommandées :

```csv
score,company,domain,industry,naics_code,size_band,revenue_band,country,city,trigger_event,trigger_date,contact_name,contact_title,contact_email,email_status,linkedin_url,source_urls,why_prospect,confidence,verified_date,notes
```

Pour le tableau de chat, condenser à : Score | Entreprise | Secteur | Taille | Trigger | Contact | Statut email | Confiance.

---

## Sélection des cibles d'outreach prioritaires (B2B)

Prioriser, pour les 3 à 5 meilleurs leads chauds :

1. **Fraîcheur du trigger event** — 30 jours bat 6 mois
2. **Spécificité du trigger event** — l'arrivée d'un nouveau CMO sur la fonction de votre acheteur bat « l'entreprise est dans l'actualité »
3. **Accès au décideur** — un contact nominatif avec email vérifié + LinkedIn bat une fonction seule
4. **Précision du fit vertical** — un match NAICS exact bat « secteur adjacent »

La justification de chaque cible prioritaire nomme le trigger et le décideur : « A recruté un nouveau VP Marketing il y a 14 jours ; email vérifié ; industriel mid-market correspondant à l'ICP. »

---

## Erreurs fréquentes (B2B)

1. **Traiter le B2B comme du SaaS** — les levées de fonds comptent moins ; la détention par un fonds et l'activité d'acquisition comptent plus.
2. **Vouloir vérifier précisément le CA d'une entreprise privée** — la plupart des bases publiques approximent. Utiliser des tranches de taille, pas des estimations ponctuelles.
3. **Ignorer la complexité achats** à l'échelle grands comptes — votre liste de contacts peut ne pas inclure le véritable approbateur.
4. **Faire du cold email aux assistants de direction** — ce ne sont pas les acheteurs et ils signaleront votre outreach comme spam.
5. **Hygiène des URL sources** — sans traçabilité des sources, vous ne pourrez pas défendre un contact face à une demande d'accès RGPD (DSAR) ou un litige CAN-SPAM.
6. **S'arrêter à une seule source** — Apollo peut être fiable à 60 % sur les petites entreprises. Recouper avec LinkedIn ou le site de l'entreprise.
