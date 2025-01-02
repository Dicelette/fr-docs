---
title: Commandes de base
sidebar_position: 1
---

## Lancer de dés

:::usage
**`/roll (argument) (?caché)`**
:::

Vous pouvez également utiliser la notation "semi-directe" en ajoutant un commentaire dans l'argument : `/roll (dés commentaire)`. 

Veuillez noter que la notation "indirecte" n'est pas disponible dans ce mode.

![Roll](/assets/rolls/slash-commands.gif)

L'option `caché` ne fonctionne que si les [jets invisibles](../config/logs.md#jets-invisibles-jet_invisible) sont activés. Si l'option est utilisée, le résultat sera envoyé en message éphémère, et utilisera le salon configuré (si existant) pour sauvegarder les résultats.

## Créer une nouvelle scène

:::usage
**`/scene [nom] (tempo)`**
:::

Le bot créera alors un nouveau fil de discussion, préfixé par `🎲`, où il enverra les logs des dés. Ce fil de discussion prendra le nom de la `scène`, et tous les autres fils de discussion préfixés par `🎲` seront archivés.

![Scene](/assets/rolls/scene.gif)

L'argument `tempo` permet de créer une "bulle temporelle", qui créera un thread préfixé par une horloge et, par défaut, le nom du salon sera la date du jour.



## Aide

Il existe plusieurs commandes d'aide, en fonction de ce dont vous avez besoin :
- `/aide info` : Affiche les infos générales sur le bot, notament comment lancer un dé ou créer une scène.
- `/aide admin` : Affiche les commandes d'administration, comme pour [logs](../config/logs.md#journalisation-des-modifications-et-des-erreurs--config-logs) ou [result_channel](../config/logs.md#sauvegarde-des-résultats-result_channel).
- `/aide enregister` : Affiche l'aide spécifique pour enregistrer un modèle de serveur et les fiches de personnages et vous dirige vers [la documentation](../template/index.md).
- `/aide bug` : Affiche un lien pour créer un rapport de bug.
- `/aide suggestion` : Affiche un lien pour faire une suggestion.
