---
title: Auto-rôle
sidebar_position: 3
---

:::usage
**<mark>`/config auto_role dé`</mark> (@role)**  
**<mark>`/config auto_role stats`</mark> (@role)**
- `@role` : Rôle à attribuer lors de la validation des statistiques/ ajout d'un dé.
:::

Permet d'ajouter automatiquement des rôles lors de certaines actions :
- Ajout d'un dé (<mark>`/config auto_role dé`</mark>)
- Validation de statistiques (<mark>`/config auto_role stats`</mark>)

Cela permet notamment de restreindre l'utilisation de <mark>`/macro`</mark> et <mark>`/dbroll`</mark> à certains rôles.

Si le rôle n'est pas fourni, l'auto-rôle sera désactivé.

<small>Pour plus d'informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
