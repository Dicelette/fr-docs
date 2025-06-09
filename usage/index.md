---
title: Commandes de base
sidebar_position: 1
---

## Lancer de dés

:::usage
**`/roll (argument) (?caché)`**
- `(argument)` : Expression à lancer (ex : `1d20+3`, ou voir [Notations des dés](./message.md))
- `?caché` : Option pour rendre le jet invisible (voir [Jets invisibles](../config/threads.md#jets-invisibles))
:::

Pour comprendre toutes les notations de dés utilisables avec le bot (notation directe, indirecte, semi-directe), consultez la page [Notations des dés](./message.md).

![Roll](/assets/rolls/slash-commands.gif)

## Créer une nouvelle scène

:::usage
**`/scene [nom] (tempo)`**
- `[nom]` : Nom de la scène à créer
- `(tempo)` : Crée une bulle temporelle (le salon sera préfixé par une horloge et nommé par défaut à la date du jour)
:::

Le bot créera alors un nouveau fil de discussion, préfixé par `🎲`, où il enverra les logs des dés. Ce fil de discussion prendra le nom de la `scène`, et tous les autres fils de discussion préfixés par `🎲` seront archivés.

![Scene](/assets/rolls/scene.gif)

## Aide

Il existe plusieurs commandes d'aide, en fonction de ce dont vous avez besoin :
- `/aide info` : Affiche les infos générales sur le bot, notamment comment lancer un dé ou créer une scène.
- `/aide admin` : Affiche les commandes d'administration, comme pour [logs](../config/logs.md#journalisation-des-modifications-et-des-erreurs--config-logs) ou [result_channel](../config/logs.md#sauvegarde-des-résultats-result_channel).
- `/aide enregister` : Affiche l'aide spécifique pour enregistrer un modèle de serveur et les fiches de personnages et vous dirige vers [la documentation](../sheet/model/index.md).
- `/aide bug` : Affiche un lien pour créer un rapport de bug.
- `/aide suggestion` : Affiche un lien pour faire une suggestion.

Pour la description complète des champs de commandes : [voir la syntaxe](../introduction/format.md).