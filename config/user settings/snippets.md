---
title: Snippets
sidebar_position: 7
---

Les `snippets` sont des dés réutilisables qui ne sont pas liés à un personnage ou à un modèle spécifique. Ils peuvent être créés et utilisés par les utilisateurs pour simplifier les jets de dés fréquents, sans pour autant avoir besoin de configurer un modèle.

# Création de snippets (`/user_config snippets créer`)

:::usage
**`/user_config snippets créer [nom] [dé]`**
- `nom` : Nom du snippet
- `dé` : Dé qui sera lancé (ex : `1d20+5`)
:::

:::important
Les statistiques ne sont pas prises en charge dans les snippets, car ils ne sont pas liés à un personnage.
:::

Si le snippet existe déjà, alors le dé sera mis à jour avec la nouvelle valeur.

![create_snippet](../../assets/snippets/create.png)

# Suppression (`/user_config snippets supprimer`)

:::usage
**`/user_config snippets supprimer [*nom]`**
- `*nom` : Nom du snippet à supprimer
:::

Permet de supprimer un snippet existant à partir de la liste.

![delete_snippet](../../assets/snippets/delete.png)

# Liste des snippets (`/user_config snippets lister`)

:::usage
**`/user_config snippets lister`**
:::

Affiche la liste des snippets existants pour l'utilisateur.

![list_snippet](../../assets/snippets/list.png)

# Exporter les snippets (`/user_config snippets export`)

:::usage
**`/user_config snippets export`**
:::

Permet d'exporter tous les snippets de l'utilisateur au format JSON, afin de les sauvegarder ou de les partager ailleurs.

![export_snippet](../../assets/snippets/export.png)

# Importer des snippets (`/user_config snippets import`)

Import des snippets à partir d'un fichier JSON, permettant aux utilisateurs de transférer ou partager facilement des données entre différents serveurs ou compte.

:::usage
**`/user_config snippets import [fichier] (?écraser)`**
- `fichier` : Données JSON des snippets à importer
- `?écraser` : Permet d'écraser les données plutôt que de les fusionner avec les anciennes.
:::

Par défaut, les données seront fusionnées mais si deux snippets ont le même nom, le nouveau écrasera l'ancien.

Les snippets seront vérifiés durant l'import et seuls ceux valides seront ajoutés.

![import_snippet](../../assets/snippets/import_cmd.png)
![import_snippet_2](../../assets/snippets/import.png)
