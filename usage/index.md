---
title: Commandes de base
sidebar_position: 1
---

## Lancer de dés

:::usage
**`/roll (dice) (?caché)`**
- `dice` : Expression à lancer (ex : `1d20+3`, ou voir [Notations des dés](./../introduction/expression.mdx))
- `?caché` : Option pour rendre le jet invisible (voir [Jets invisibles](../config/threads.md#jets-invisibles))
:::

Pour comprendre toutes les notations de dés utilisables avec le bot (notation directe, indirecte, semi-directe), consultez la page [Notations des dés](./message.md).

![Roll](/assets/rolls/slash-commands.gif)

## Créer une nouvelle scène

:::usage
**`/scene [nom] (tempo)`**
- `nom` : Nom de la scène à créer
- `tempo` : Crée une bulle temporelle (le salon sera préfixé par une horloge et nommé par défaut à la date du jour)
:::

Le bot créera alors un nouveau fil de discussion, préfixé par `🎲`, où il enverra les logs des dés. Ce fil de discussion prendra le nom de la `scène`, et tous les autres fils de discussion préfixés par `🎲` seront archivés.

![Scene](/assets/rolls/scene.gif)

## Baromètre de chances

Le bot va automatiquement compter les jets réussis et ratés dans le serveur par utilisateur. <mark>Cela ne fonctionne que pour les dés lancés avec le bot avec une comparaison</mark>, avec l'indication `Échec` ou `Réussite` dans le message. Les critiques sont aussi comptés.

Cette commande permet d'obtenir :
- Un leaderboard des joueurs les plus (ou moins !) chanceux du serveur,
- Les mesures d'un joueur en particulier.
- Des statistiques globales du serveur.

:::usage
**`/barometre_chance (@utilisateur)`**
- `@utilisateur` : Optionnel, permet d'obtenir les statistiques d'un utilisateur en particulier.
:::

:::usage
**`/barometre_chance classement [type]`**
- `type` : Obligatoire, permet de choisir le type de dés à afficher. Choix entre `Succès`, `Échecs`, `Succès critique` et `Échec critique`.
:::

:::usage
**`/barometre_chance moyenne`**
Affiche les statistiques globales du serveur.
:::

:::warning
De manière évidente, le baromètre de chance ne fonctionne que pour les dés lancés avec le bot, et ne fonctionne pas avec les critiques personnalisés qui ne correspondent pas aux textes standards `Échec`, `Réussite`, etc.
:::

## Aide

Il existe plusieurs commandes d'aide, en fonction de ce dont vous avez besoin :
- `/aide info` : Affiche les infos générales sur le bot, notamment comment lancer un dé ou créer une scène.
- `/aide admin` : Affiche les commandes d'administration, comme pour [logs](../config/logs.md) ou [result_channel](../config/threads.md#configurer-lenvoi-des-résultats).
- `/aide enregister` : Affiche l'aide spécifique pour enregistrer un modèle de serveur et les fiches de personnages et vous dirige vers [la documentation](../sheet/model/index.md).
- `/aide bug` : Affiche un lien pour créer un rapport de bug.
- `/aide suggestion` : Affiche un lien pour faire une suggestion.

<small>Pour la description complète des champs de commandes : [voir la syntaxe](../introduction/format.mdx).</small>