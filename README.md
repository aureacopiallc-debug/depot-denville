# Dépôt de Danviller

Commandes au fournil, invendus du soir et contrôle de caisse pour le
dépôt de pain. Une page, un code par vendeuse, aucun compte à créer.

## Le principe

Chaque jour, la boutique commande pour le lendemain, en deux créneaux :
livraison du matin, livraison de l'après-midi. La commande part sur
WhatsApp ou Telegram d'un appui, déjà rédigée.

Le soir, la vendeuse compte ce qui reste. L'application en déduit ce qui
a été vendu et la recette que la caisse devrait afficher. L'écart entre
cette recette et la caisse réelle est le contrôle.

## Données

Collections Firestore, partagées avec le Cahier du Labo :

- `depot_acces` — `nom`, `code`, `role` (`direction` ou `vente`), `ordre`
- `depot_produits` — `nom`, `prix`, `ordre`
- `depot_jours/<date>` — `d`, `cmd_matin`, `cmd_aprem`, `livre`,
  `invendu` (chacun une table produit → quantité), `caisse`
- `depot_reglages/general` — `telWa`, `nomDepot`
