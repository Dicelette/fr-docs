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

## Pitié

:::usage
**`/config pitié (seuil)`**
- `(seuil)` : Nombre d'échecs consécutifs avant l'activation de la pitié (min : 2).
:::
Active la pitié sur les jets de dés : après un certain nombre d'échecs d'affilée, le bot garantit un succès automatique au jet suivant.

Le fonctionnement : plus on se rapproche du seuil, plus la probabilité d'activation augmente dès 75%. Une fois le seuil atteint (100%), la pitié se déclenche automatiquement.[^1]

:::tip
La "pitié" est en réalité une relance du dé (jusqu'à 100 fois maximum) jusqu'à obtenir un succès. Elle s'applique uniquement aux jets contenant une comparaison (`XdY+Z>A`).
:::

:::warning
Pour éviter la triche, le compteur d'échecs successifs est mis en cache pour les comparaisons dites "triviales", avec horodatage pour repérer les échecs consécutifs. Une comparaison triviale est toujours gagnée ou perdue, quel que soit le résultat du dé (ex. : `1d20 > 100` est toujours un échec).

Il est toutefois possible que des comparaisons triviales soient comptabilisées si le message n'est pas détecté dans le délai imparti (une minute). Ce cas reste rare, mais il est recommandé de :
- Ne pas abuser des comparaisons triviales.
- Augmenter le seuil de pitié pour limiter les risques de triche.
:::

Pour supprimer le système de pitié, il suffit de rentrer la commande sans paramètre.

<small>Pour plus d'informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>

[^1]: Il est possible de retrouver le code de probabilité [ici](https://github.com/Dicelette/discord-dicelette/blob/07e3be0ac67a4c6971f0b553d69d53026428691f/packages/bot/src/commands/admin/configuration/pity.ts#L37-L64).