---
title: Auto-rôle
sidebar_position: 3
---

:::usage
**`/config auto_role dé (@role)`**  
**`/config auto_role stats (@role)`**
- `@role` : Rôle à attribuer lors de la validation des statistiques/ ajout d’un dé.
:::

Permet d’ajouter automatiquement des rôles lors de certaines actions :
- Ajout d’un dé (`/config auto_role dé`)
- Validation de statistiques (`/config auto_role stats`)

Cela permet notamment de restreindre l’utilisation de `/dbd` et `/dbroll` à certains rôles.

Si le rôle n’est pas fourni, l’auto-rôle sera désactivé.

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.md).</small>
