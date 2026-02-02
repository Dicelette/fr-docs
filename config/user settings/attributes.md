---
title: Attributs
---
Les ==attributs== permettent à chaque utilisateur de définir et gérer des attributs numériques spécifiques à un serveur, sans la nécessité de configurer un modèle ou en accompagnement du modèle.

:::warning
Dans les cas où une fiche de personnage possède des statistiques, les attributs seront fusionnés à ces données mais la valeur des statistiques écrasera toujours la valeur d'un attributs si les noms sont identiques.
:::

## Usage

Contrairement aux [snippets](snippets.md), les attributs ne sont pas utilisables tels quels mais agissent comme des raccourcis (de la même manière que les statistiques) sous forme de clé. Ainsi, cela permet d'utiliser directement le **nom** de l'attributs dans le dé, préfixé par le symbole `$`.

:::example[`1d$force`]
Si `force` est défini comme égal à `12` le dé sera transformé tel que `1d12`
:::

Cette syntaxe est utilisable :
- Dans les commandes de jets `/roll`
- Dans la [notation directe](../../usage/message.md)
- Dans les commandes de jets liés aux fiches `/dbroll`, `/macro` ainsi que leur équivalent dans `/mj`.
- Dans les commandes `/calc` et `/math` (uniquement dans un serveur)

:::tip
Tout comme les snippets, chaque clé doit être unique. Il est conseillé d'utiliser :
- Des noms courts,
- Sans espace (bien que dans le cas où un espace est utilisé, la valeur peut être retrouvé en remplaçant les espace par des `-`.)
:::

:::warning
Les attributs sont enregistrés de manière globale par serveur, et sont donc communs à chaque personnage enregistré pour un même joueur !
:::

