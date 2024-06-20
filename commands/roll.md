---
title: Lancer de dés et scènes
sidebar_position: 3
---

## Lancer de dés

:::usage
**`/roll (argument)`**
:::

Vous pouvez également utiliser la notation "semi-directe" en ajoutant un commentaire dans l'argument : `/roll (dés commentaire)`. 

Veuillez noter que la notation "indirecte" n'est pas disponible dans ce mode.

![Roll](/assets/rolls/slash-commands.gif)

## Créer une nouvelle scène

:::usage
**`/scene [nom] (tempo)`**
:::

Le bot créera alors un nouveau fil de discussion, préfixé par `🎲`, où il enverra les logs des dés. Ce fil de discussion prendra le nom de la `scène`, et tous les autres fils de discussion préfixés par `🎲` seront archivés.

![Scene](/assets/rolls/scene.gif)

L'argument `tempo` permet de créer une "bulle temporelle", qui créera un thread préfixé par une horloge et, par défaut, le nom du channel sera la date du jour.

