---
title: Configuration générale
sidebar_position: 1
---
Toutes les commandes d'administration sont restreintes par défaut aux membres ayant la permission <mark>Gérer les rôles</mark>.

La commande `/config afficher` permet de voir la configuration actuelle du serveur.

:::usage
- **`/config afficher général`** : Affiche la configuration générale du serveur.
- **`/config afficher modèle`** : Affiche la configuration du modèle (liens, noms des statistiques et celles exclues, noms de dés globaux), si elle existe.
:::


## Changer la langue

:::usage
**`/config changer_langue [langue]`**
- `[langue]` : `fr` ou `en` (français ou anglais)
:::

Permet de modifier la langue du bot pour tout le serveur, prioritaire sur la langue du client.

Pour le moment, seules les langues française et anglaise sont disponibles.

## Éditer le bot

:::usage
**`/config éditer_moi (pseudo) (bio) (avatar) (bannière)`**
- `(pseudo)` : Nouveau pseudo du bot sur le serveur.
- `(bio)` : Nouvelle biographie du bot.
- `(avatar)` : Nouvelle image d'avatar du bot, sous forme de fichier.
- `(bannière)` : Nouvelle image de bannière du bot, sous forme de fichier.
:::

Permet de configurer un profil personnalisé sur le serveur pour le bot.

Lorsqu'une valeur n'est pas fournie, le champ correspondant sera réinitialisé à sa valeur par défaut.

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>