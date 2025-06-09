---
title: Autres
sidebar_position: 3
---

Les deux commandes suivantes acceptent :
- `(@joueur)` : Le nom du joueur
- `(*personnage)` : Et/ou le nom du personnage

## Afficher

:::usage
**`/afficher (@joueur) (*personnage)`**
- `(@joueur)` : Nom du joueur (optionnel)
- `(*personnage)` : Nom du personnage (optionnel)
:::

La commande `afficher` permet de consulter les statistiques et les dés d'un personnage enregistré dans la base de données.

![afficher](/assets/rolls/db/display_ex.png)

## Graphique (`/graph`)

:::usage
**`/graph (@joueur) (*personnage) (ligne) (fond) (min) (max)`**
- `(@joueur)` : Nom du joueur (optionnel)
- `(*personnage)` : Nom du personnage (optionnel)
- `(ligne)` : Couleur des lignes (défaut : `#0e47b2`)
- `(fond)` : Couleur du fond (défaut : `#0e47b2`)
- `(min)` : Minimum de l’axe (optionnel)
- `(max)` : Maximum de l’axe (optionnel)
:::

La commande `/graph` génère un graphique à partir des statistiques d'un personnage.  
Vous pouvez personnaliser la couleur des lignes et du fond (hexadécimal ou RGB, ex : `#FF0000` ou `255,0,0`).

Par défaut :
- Le minimum est calculé selon le modèle de serveur (si existant).
- Le maximum est déterminé de différentes manières :
   - Si un maximum est défini par la template, il sera utilisé.
   - Sinon, il sera basé sur la valeur du succès critique.
   - Si aucune des deux options précédentes n'est disponible, il sera basé sur la valeur du dé (par exemple, si `1d20`, la valeur sera 20).
   - En dernier recours, il sera automatiquement calculé en fonction des statistiques de l'utilisateur.

![graph](/assets/graph.jpg)

Pour la description de la syntaxe des champs et l’auto-complétion, voir [la page dédiée](../../introduction/format.md).
