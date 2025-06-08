---
title: Syntaxe des commandes
---

- Les champs obligatoires sont indiqués entre crochets : `[champs]`.
- Les champs facultatifs sont entre parenthèses : `(champs)`.
- Les champs auto-complétés seront marqués d'un `*` : `(*champs)`.
- Les champs demandant une mention seront marqués par `@` (`@champs`). Ces champs fonctionnent avec les noms (rôle ou utilisateur, en fonction de la commande) ou l'ID Discord. Si la mention ne s'affiche pas immédiatement, commencez à taper le début du nom pour l'auto-complétion.
- De manière similaire, les commandes demandant un salon sont précédé par `#` comme `#champs`.
- Les champs vrai/faux (`true` ou `false`) sont préfixés par `?` (`?champs`).

## Commandes auto-complétées

Dans plusieurs commandes, il est possible de combiner à la fois un nom d'utilisateur et un personnage.

Par défaut, les personnages affichés dans la liste sont ceux de l'utilisateur qui a tapé la commande.

Si vous souhaitez afficher les personnages d'un autre joueur, vous devez mentionner le joueur en premier.

:::warning
À cause de certaines limitations de l'API Discord, si vous souhaitez changer de joueur, vous devez retaper la commande en entier.
:::

Ce fonctionnement est étendu pour la commande `/mj dbd` car les dés listés seront basés sur le personnage, listé donc à partir du joueur. De fait, par défaut, les compétences sont listées à partir du joueur ayant fait la commande.
