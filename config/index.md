---
title: Configuration générale
sidebar_position: 1
---
Toutes les commandes d'administration sont restreintes par défaut aux membres ayant la permission `Gérer les rôles`.

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

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
