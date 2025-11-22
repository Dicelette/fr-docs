---
title: Snippets
sidebar_position: 7
---

Les `snippets` sont des dés réutilisables qui ne sont pas liés à un personnage ou à un modèle spécifique. Ils peuvent être créés et utilisés par les utilisateurs pour simplifier les jets de dés fréquents, sans pour autant avoir besoin de configurer un modèle.

## Création de snippets (`/user_config snippets créer`)

:::usage
**`/user_config snippets créer [nom] [dé]`**
- `nom` : Nom du snippet
- `dé` : Dé qui sera lancé (ex : `1d20+5`)
:::

:::important
Les statistiques ne sont pas prises en charge dans les snippets, car ils ne sont pas liés à un personnage.
:::

Si le snippet existe déjà, alors le dé sera mis à jour avec la nouvelle valeur.

![create_snippet](../assets/snippets/create.png)

## Suppression (`/user_config snippets supprimer`)

:::usage
**`/user_config snippets supprimer [*nom]`**
- `*nom` : Nom du snippet à supprimer
:::

Permet de supprimer un snippet existant à partir de la liste.

![delete_snippet](../assets/snippets/delete.png)

## Liste des snippets (`/user_config snippets lister`)
:::usage
**`/user_config snippets lister`**
:::

Affiche la liste des snippets existants pour l'utilisateur.

![list_snippet](../assets/snippets/list.png)