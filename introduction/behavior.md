---
title: Comportement
sidebar_position: 2
---

:::info
La [configuration](../admin/config/index.md) permet de modifier le comportement du bot. Ce document décrit le comportement par défaut.
:::

Le fonctionnement de ce bot repose sur l'utilisation de fils de discussion. Lors de son premier lancement, il recherchera un fil préfixé par `🎲` :

- Si aucun fil n'est trouvé, le bot en créera un nouveau et y dirigera tous les logs à venir.
- En revanche, s'il existe déjà un fil, le bot sélectionnera le plus récent et y enverra les logs.

:::note Remarque
En cas de découverte de plusieurs fils, le bot utilisera le plus récent et archivera les autres.
:::

Les commandes peuvent également être exécutées dans un fil existant. Dans ce cas, le bot y enverra simplement le résultat, accessible ensuite dans les canaux dont le nom commence par `🎲`.

Il est également possible de créer un nouveau fil en utilisant la commande [créer une nouvelle scène](../Usage/roll.md#créer-une-nouvelle-scène).

:::tip Astuce
Le bot fonctionne également dans les forums, mais avec quelques différences :
- Plusieurs logs peuvent coexister simultanément (sauf s'ils portent exactement le même nom).
- Les logs seront automatiquement nommés `🎲 [nom du sujet]`, avec l'ajout automatique du tag `🪡 Dice Roll` (créé s'il n'existe pas).
- Dans ce cas, il s'agit donc d'un message qui sera créé à la place d'un fil.
:::

Il est aussi possible, via la commande `/result_channel` de fixer un salon dans lequel sera envoyé tous les logs, plutôt que de passer par un thread ou un sujet de forum. 

## Canaux

Le bot enverra **aussi** le résultat dans le canal où la commande a été initialement envoyée. Ce message :

- Sera supprimé après 3 minutes (configurable avec `/config supprimer_après`).
- Contiendra un lien vers le message dans le log.

## Utilisation

Le bot peut être :

- Utilisé avec des commandes slash (voir [commandes](../Usage/roll.md)).
- Mais également directement sur le message.
