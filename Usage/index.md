---
title: Information générale
sidebar_position: 1
---


## Commandes auto-complétées

Dans plusieurs commandes, il est possible de combiner à la fois un nom d'utilisateur et personnage. 

Par défaut, les personnages affichés dans la liste sont ceux de l'utilisateur qui a tapé la commande. 

Si vous souhaitez afficher les personnages d'un autre joueur, vous devez mentionner le joueur en premier. 

:::warning
À cause de certaines limitation de l'API Discord, si vous souhaitez changer de joueur, vous devez retaper la commande en entier.
:::

Ce fonctionnement est étendue pour la commande `/mj dbd` car les dés listés seront basés sur le personnage, listé donc à partir du joueur. De fait, par défaut, les compétences sont listés à partir du joueur ayant fait la commande.

## Format

- Les champs obligatoires sont indiqués entre crochets : `[champs]`.
- Les champs facultatifs sont entre parenthèses : `(champs)`.
- Les champs auto-complétés seront marqués d'un `*` : `(*champs)`.
- Les champs demandant une mention seront marqués par `@` (`@champs`). Ces champs fonctionnent avec les noms (rôle ou utilisateur, en fonction de la commande) ou l'ID Discord. Si la mention ne s'affiche pas immédiatement, commencez à taper le début du nom pour l'auto-complétion.
- De manière similaire, les commandes demandant un channel sont précédé par `#` comme `#champs`.

## Aide

Il existe plusieurs commandes d'aide, en fonction de ce dont vous avez besoin :
- `/aide info` : Affiche les infos générales sur le bot, notament comment lancer un dé ou créer une scène.
- `/aide admin` : Affiche les commandes d'administration, comme pour [logs](commands/administration#logs) ou [result_channel](commands/administration#result_channel).
- `/aide register` : Affiche l'aide spécifique pour enregistrer un modèle de serveur et les fiches de personnages et vous dirige vers [la documentation](model/register/).
- `/aide bug` : Affiche un lien pour créer un rapport de bug.
- `/aide suggestion` : Affiche un lien pour faire une suggestion.