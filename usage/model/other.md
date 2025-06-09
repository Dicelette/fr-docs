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
:::

La commande `afficher` permet de consulter les statistiques et les dés d'un personnage enregistré dans la base de données.

![afficher](/assets/rolls/db/display_ex.png)

## Graphique (`/graph`)

:::usage
**`/graph (@joueur) (*personnage) (ligne) (fond) (min) (max)`**
:::

La commande `/graph` génère un graphique à partir des statistiques d'un personnage.
En option, vous pouvez spécifier des couleurs avec :
- `ligne` : Pour les lignes (par défaut, `#0e47b2`).
- `fond` : Pour le fond (par défaut, `#0e47b2`).

Les couleurs peuvent être en hexadécimal ou en RGB. Par exemple, `#FF0000` ou `255,0,0`.

Enfin, il est possible de définir un minimum et un maximum pour les axes avec `min` et `max`.

Par défaut :
- Le minimum est calculé selon le modèle de serveur (si existant).
- Le maximum est déterminé de différentes manières :
   - Si un maximum est défini par la template, il sera utilisé.
   - Sinon, il sera basé sur la valeur du succès critique.
   - Si aucune des deux options précédentes n'est disponible, il sera basé sur la valeur du dé (par exemple, si `1d20`, la valeur sera 20).
   - En dernier recours, il sera automatiquement calculé en fonction des statistiques de l'utilisateur.

![graph](/assets/graph.jpg)

Pour la description de la syntaxe des champs et l’auto-complétion, voir [la page dédiée](../../introduction/format.md).
