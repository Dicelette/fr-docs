---
title: Dés de maître de jeu
sidebar_position: 4
---
:::info
Les deux commandes suivantes permettent aux maîtres de jeu de lancer des dés pour tous les joueurs enregistrés.
:::

:::usage
- **`/mj dbroll [@Joueur] [statistique] (*personnage) (?caché)`**
- **`/mj dbd [@Joueur] [*nom du dé] (*personnage) (?caché)`**
:::

Les deux commandes sont similaires à [dbroll](../Usage/model.mdx#dbroll) et [dbd](../Usage/model.mdx#dbd), mais nécessite en plus de spécifier le joueur pour lequel le jet est effectué. Comme les autres commandes, il est possible de choisir un personnage appartenant à ce joueur ou de laisser le choix par défaut.

L'option caché ne fonctionne que si les [jets invisibles](../admin/config/index.md#jets-invisibles-jet_invisible) sont activés. Si l'option est activée, le résultat sera envoyé en message éphémère, et utilisera le salon configuré (si existant) pour sauvegarder les résultats.