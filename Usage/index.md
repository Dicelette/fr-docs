---
title: Information générale
sidebar_position: 1
---

## Format

- Les champs obligatoires sont indiqués entre crochets : `[champs]`.
- Les champs facultatifs sont entre parenthèses : `(champs)`.
- Les champs auto-complétés seront marqués d'un `*` : `(*champs)`.
- Les champs demandant une mention seront marqués par `@` (`@champs`). Ces champs fonctionnent avec les noms (rôle ou utilisateur, en fonction de la commande) ou l'ID Discord. Si la mention ne s'affiche pas immédiatement, commencez à taper le début du nom pour l'auto-complétion.
- De manière similaire, les commandes demandant un salon sont précédé par `#` comme `#champs`.
- Les champs vrai/faux (`true` ou `false`) sont préfixés par `?` (`?champs`).

## Commandes auto-complétées

Dans plusieurs commandes, il est possible de combiner à la fois un nom d'utilisateur et personnage. 

Par défaut, les personnages affichés dans la liste sont ceux de l'utilisateur qui a tapé la commande. 

Si vous souhaitez afficher les personnages d'un autre joueur, vous devez mentionner le joueur en premier. 

:::warning
À cause de certaines limitations de l'API Discord, si vous souhaitez changer de joueur, vous devez retaper la commande en entier.
:::

Ce fonctionnement est étendue pour la commande `/mj dbd` car les dés listés seront basés sur le personnage, listé donc à partir du joueur. De fait, par défaut, les compétences sont listés à partir du joueur ayant fait la commande.


## Lancer de dés

:::usage
**`/roll (argument) (?caché)`**
:::

Vous pouvez également utiliser la notation "semi-directe" en ajoutant un commentaire dans l'argument : `/roll (dés commentaire)`. 

Veuillez noter que la notation "indirecte" n'est pas disponible dans ce mode.

![Roll](/assets/rolls/slash-commands.gif)

L'option `caché` ne fonctionne que si les [jets invisibles](../admin/config/index.md#jets-invisibles-jet_invisible) sont activés. Si l'option est utilisée, le résultat sera envoyé en message éphémère, et utilisera le salon configuré (si existant) pour sauvegarder les résultats.

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
- `/aide admin` : Affiche les commandes d'administration, comme pour [logs](../admin/config/index.md#administration-logs) ou [result_channel](../admin/config/index.md#sauvegarde-des-résultats-result_channel).
- `/aide enregister` : Affiche l'aide spécifique pour enregistrer un modèle de serveur et les fiches de personnages et vous dirige vers [la documentation](../admin/model/index.md).
- `/aide bug` : Affiche un lien pour créer un rapport de bug.
- `/aide suggestion` : Affiche un lien pour faire une suggestion.
