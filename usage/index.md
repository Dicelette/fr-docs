---
title: Commandes de base
sidebar_position: 1
aliases:
  - commande de base
---

## Lancer de dés

:::usage
**`/roll [dé] (succès_critique) (échec_critique) (commentaire) (?caché)`**
- `dé` : Expression à lancer (ex : `1d20+3`, ou voir [Notations des dés](./../introduction/expression.mdx))
- `succès_critique` : Écrase la valeur de succès critique. Nécessite d'être écrit avec son signe (`>=, <=, ==`, etc.). Écrasera la valeur de succès critique si elle est définie [avec la syntaxe associée](../introduction/expression.mdx#Succès-et-échecs-critiques).
- `échec_critique` : Comme ci-dessus mais pour les échecs critiques.
- `commentaire` : Commentaires facultatifs qui remplaceront les commentaires (éventuellement) présents dans la valeur du `dé`.
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

## Karma

Le bot va automatiquement compter les jets réussis et ratés dans le serveur par utilisateur. <mark>Cela ne fonctionne que pour les dés lancés avec le bot avec une comparaison</mark>, avec l'indication `Échec` ou `Réussite` dans le message. Les critiques sont aussi comptés.

Cette commande permet d'obtenir :
- Un leaderboard des joueurs les plus (ou moins !) chanceux du serveur,
- Les mesures d'un joueur en particulier.
- Des statistiques globales du serveur.

:::usage
**`/karma bilan (@utilisateur)`**
- `@utilisateur` : Optionnel, permet d'obtenir les statistiques d'un utilisateur en particulier.
:::

:::usage
**`/karma classement (type)`**
- `type` : Permet de choisir le type de dés à afficher. Choix entre `Succès`, `Échecs`, `Succès critique`, `Échec critique` et `Total`.
Sans type choisi, affiche les statistiques du serveur, ainsi que le classement pour chaque type.
:::

:::usage
**`/karma serveur`**
Affiche les statistiques globales du serveur.
:::

:::usage
**`/karma reset (@user) (everyone)`**
Permet de réinitialiser le classement.

Les options sont réservées aux administrateurs du serveur.
- `@user` : Optionnel, permet de réinitialiser les statistiques d'un utilisateur en particulier.
- `everyone` : Optionnel, réinitialise les statistiques de tous les utilisateurs du serveur
:::

:::warning
De manière évidente, le karma ne fonctionne que pour les dés lancés avec le bot, et ne fonctionne pas avec les critiques personnalisés qui ne correspondent pas aux textes standards `Échec`, `Réussite`, etc.
:::

## Choisir
:::usage
**`/choisir [liste] (combien)`**
- `liste` : Liste des options séparées par des points-virgules, virgule ou espace.
- `combien` : Nombre d'options à sélectionner (par défaut 1).
:::

Cette commande permet de choisir aléatoirement une ou plusieurs options parmi une liste fournie.


## Aide

Il existe plusieurs commandes d'aide, en fonction de ce dont vous avez besoin :
- `/aide info` : Affiche les infos générales sur le bot, notamment comment lancer un dé ou créer une scène.
- `/aide admin` : Affiche les commandes d'administration, comme pour [logs](../config/logs.md) ou [result_channel](../config/threads.md#configurer-lenvoi-des-résultats).
- `/aide enregister` : Affiche l'aide spécifique pour enregistrer un modèle de serveur et les fiches de personnages et vous dirige vers [la documentation](../sheet/model/index.md).
- `/aide bug` : Affiche un lien pour créer un rapport de bug.
- `/aide suggestion` : Affiche un lien pour faire une suggestion.
- `/info` : Affiche les statistiques générales du bot (nombre de serveur, version, uptime…) ainsi que des liens utiles.

<small>Pour la description complète des champs de commandes : [voir la syntaxe](../introduction/format.mdx).</small>