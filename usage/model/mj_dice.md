---
title: Dés de maître de jeu
sidebar_position: 4
---

:::info
Les trois commandes suivantes permettent aux maîtres de jeu de lancer des dés ou faire des calculs pour tous les joueurs enregistrés.
:::

:::usage
- **`/mj dbroll [@Joueur] [statistique] (... autres options) (*personnage) (?caché)`**
- **`/mj dbd [@Joueur] [*nom du dé] (... autres options) (*personnage) (?caché)`**
- **`/mj calc [@joueur] [statistique] [signe] [expression]  (... autres options) (*personnage) (?caché)`**
:::

Toutes les commandes fonctionnent de manière similaire à [dbroll](./dice.mdx#dbroll-dbroll), [dbd](./dice.mdx#dbd-dbd) et [calc](./calc.mdx#basé-sur-des-statistiques-calc), mais demandent en plus de spécifier le joueur pour lequel le jet est effectué. Comme pour les autres commandes, il est possible de choisir un personnage appartenant à ce joueur ou de laisser le choix par défaut.

L'option `?caché` ne fonctionne que si les [jets invisibles](../../config/threads.md#jets-invisibles) sont activés. Si l'option est utilisée, le résultat sera envoyé en message éphémère, et utilisera le salon configuré (si existant) pour sauvegarder les résultats.

<small>Pour la syntaxe complète des champs et l’auto-complétion des personnages, voir [Syntaxe des commandes](../../introduction/format.mdx).</small>
