# Référence de bibliothèque d'événements

Liste exhaustive des événements à tracker par type d'activité et par contexte.

## Sommaire
- Événements de site marketing (navigation & engagement, interactions CTA & formulaire, événements de conversion)
- Événements produit/app (onboarding, usage cœur, erreurs & support)
- Événements de monétisation (pricing & checkout, gestion d'abonnement)
- Événements e-commerce (navigation, panier, checkout, post-achat)
- Événements spécifiques B2B / SaaS (équipe & collaboration, événements d'intégration, événements de compte)
- Propriétés des événements (paramètres)
- Séquences d'événements de funnel

## Événements de site marketing

### Navigation & engagement

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| page_view | Page chargée (enrichie) | page_title, page_location, content_group |
| scroll_depth | L'utilisateur a scrollé jusqu'à un seuil | depth (25, 50, 75, 100) |
| outbound_link_clicked | Clic vers un site externe | link_url, link_text |
| internal_link_clicked | Clic au sein du site | link_url, link_text, location |
| video_played | Vidéo démarrée | video_id, video_title, duration |
| video_completed | Vidéo terminée | video_id, video_title, duration |

### Interactions CTA & formulaire

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| cta_clicked | CTA cliqué | button_text, cta_location, page |
| form_started | L'utilisateur a commencé le formulaire | form_name, form_location |
| form_field_completed | Champ rempli | form_name, field_name |
| form_submitted | Formulaire envoyé avec succès | form_name, form_location |
| form_error | Validation du formulaire échouée | form_name, error_type |
| resource_downloaded | Ressource téléchargée | resource_name, resource_type |

### Événements de conversion

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| signup_started | Inscription initiée | source, page |
| signup_completed | Inscription terminée | method, plan, source |
| demo_requested | Formulaire de démo soumis | company_size, industry |
| contact_submitted | Formulaire de contact envoyé | inquiry_type |
| newsletter_subscribed | Inscription à la liste email | source, list_name |
| trial_started | Free trial démarré | plan, source |

---

## Événements produit/app

### Onboarding

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| signup_completed | Compte créé | method, referral_source |
| onboarding_started | Onboarding commencé | - |
| onboarding_step_completed | Étape terminée | step_number, step_name |
| onboarding_completed | Toutes les étapes faites | steps_completed, time_to_complete |
| onboarding_skipped | L'utilisateur a sauté l'onboarding | step_skipped_at |
| first_key_action_completed | Moment « aha » atteint | action_type |

### Usage cœur

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| session_started | Session de l'app commencée | session_number |
| feature_used | Interaction avec une fonctionnalité | feature_name, feature_category |
| action_completed | Action cœur réalisée | action_type, count |
| content_created | L'utilisateur a créé du contenu | content_type |
| content_edited | L'utilisateur a modifié du contenu | content_type |
| content_deleted | L'utilisateur a supprimé du contenu | content_type |
| search_performed | Recherche dans l'app | query, results_count |
| settings_changed | Paramètres modifiés | setting_name, new_value |
| invite_sent | L'utilisateur a invité d'autres personnes | invite_type, count |

### Erreurs & support

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| error_occurred | Erreur rencontrée | error_type, error_message, page |
| help_opened | Aide consultée | help_type, page |
| support_contacted | Demande de support faite | contact_method, issue_type |
| feedback_submitted | Retour utilisateur donné | feedback_type, rating |

---

## Événements de monétisation

### Pricing & checkout

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| pricing_viewed | Page de pricing vue | source |
| plan_selected | Offre choisie | plan_name, billing_cycle |
| checkout_started | Checkout commencé | plan, value |
| payment_info_entered | Paiement soumis | payment_method |
| purchase_completed | Achat réussi | plan, value, currency, transaction_id |
| purchase_failed | Achat échoué | error_reason, plan |

### Gestion d'abonnement

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| trial_started | Trial commencé | plan, trial_length |
| trial_ended | Trial expiré | plan, converted (bool) |
| subscription_upgraded | Offre upgradée | from_plan, to_plan, value |
| subscription_downgraded | Offre downgradée | from_plan, to_plan |
| subscription_cancelled | Annulé | plan, reason, tenure |
| subscription_renewed | Renouvelé | plan, value |
| billing_updated | Moyen de paiement changé | - |

---

## Événements e-commerce

### Navigation

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| product_viewed | Page produit vue | product_id, product_name, category, price |
| product_list_viewed | Catégorie/liste vue | list_name, products[] |
| product_searched | Recherche effectuée | query, results_count |
| product_filtered | Filtres appliqués | filter_type, filter_value |
| product_sorted | Tri appliqué | sort_by, sort_order |

### Panier

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| product_added_to_cart | Article ajouté | product_id, product_name, price, quantity |
| product_removed_from_cart | Article retiré | product_id, product_name, price, quantity |
| cart_viewed | Page panier vue | cart_value, items_count |

### Checkout

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| checkout_started | Checkout commencé | cart_value, items_count |
| checkout_step_completed | Étape terminée | step_number, step_name |
| shipping_info_entered | Adresse saisie | shipping_method |
| payment_info_entered | Paiement saisi | payment_method |
| coupon_applied | Coupon utilisé | coupon_code, discount_value |
| purchase_completed | Commande passée | transaction_id, value, currency, items[] |

### Post-achat

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| order_confirmed | Confirmation vue | transaction_id |
| refund_requested | Remboursement initié | transaction_id, reason |
| refund_completed | Remboursement traité | transaction_id, value |
| review_submitted | Produit noté/évalué | product_id, rating |

---

## Événements spécifiques B2B / SaaS

### Équipe & collaboration

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| team_created | Nouvelle équipe/org créée | team_size, plan |
| team_member_invited | Invitation envoyée | role, invite_method |
| team_member_joined | Membre accepté | role |
| team_member_removed | Membre retiré | role |
| role_changed | Permissions mises à jour | user_id, old_role, new_role |

### Événements d'intégration

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| integration_viewed | Page d'intégration vue | integration_name |
| integration_started | Configuration commencée | integration_name |
| integration_connected | Connectée avec succès | integration_name |
| integration_disconnected | Intégration retirée | integration_name, reason |

### Événements de compte

| Nom de l'event | Description | Propriétés |
|------------|-------------|------------|
| account_created | Nouveau compte | source, plan |
| account_upgraded | Upgrade d'offre | from_plan, to_plan |
| account_churned | Compte fermé | reason, tenure, mrr_lost |
| account_reactivated | Client revenu | previous_tenure, new_plan |

---

## Propriétés des événements (paramètres)

### Propriétés standard à inclure

**Contexte utilisateur :**
```
user_id: "12345"
user_type: "free" | "trial" | "paid"
account_id: "acct_123"
plan_type: "starter" | "pro" | "enterprise"
```

**Contexte de session :**
```
session_id: "sess_abc"
session_number: 5
page: "/pricing"
referrer: "https://google.com"
```

**Contexte de campagne :**
```
source: "google"
medium: "cpc"
campaign: "spring_sale"
content: "hero_cta"
```

**Contexte produit (e-commerce) :**
```
product_id: "SKU123"
product_name: "Product Name"
category: "Category"
price: 99.99
quantity: 1
currency: "EUR"
```

**Timing :**
```
timestamp: "2024-01-15T10:30:00Z"
time_on_page: 45
session_duration: 300
```

---

## Séquences d'événements de funnel

### Funnel d'inscription
1. signup_started
2. signup_step_completed (email)
3. signup_step_completed (password)
4. signup_completed
5. onboarding_started

### Funnel d'achat
1. pricing_viewed
2. plan_selected
3. checkout_started
4. payment_info_entered
5. purchase_completed

### Funnel e-commerce
1. product_viewed
2. product_added_to_cart
3. cart_viewed
4. checkout_started
5. shipping_info_entered
6. payment_info_entered
7. purchase_completed
