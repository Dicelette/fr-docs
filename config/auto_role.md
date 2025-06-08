---
title: Auto-rôle
sidebar_position: 3
---

:::usage
- **`/config auto_role dé (@role)`**
- **`/config auto_role stats (@role)`**
:::

Ces commandes permettent d'ajouter automatiquement des rôles lorsque :
- Un dé est ajouté (`/config auto_role dé`)
- Des statistiques sont validées (`/config auto_role stats`)

Cela permet, notamment, d'autoriser l'utilisation de `/dbd` et `/dbroll` aux utilisateurs ayant effectivement la possibilité d'utiliser ces deux commandes.

Si le rôle n'est pas fourni, l'option sera désactivée.

