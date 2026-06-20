---
title: Formule personnalisée
sidebar_position: 7
---

Cette commande permet de créer une formule personnalisée [Mathjs](https://mathjs.org/), qui sert de "modèle". Ce modèle va automatiquement remplacer les valeurs entre crochet `[]`.

Les formules personnalisées peuvent être créé de deux manières :
- Soit par un utilisateur pour chaque serveur, via la commande `/user_config formule_personnalisée`
- Soit par un administrateur pour le serveur, via la commande `/config formule_personnalisée`

:::info
Si une formule personnalisée est créée par un administrateur pour le serveur, elle sera prioritaire sur celle créée par un utilisateur.
:::

## Syntaxe

La formule personnalisée doit être une formule valide Mathjs. Pour symboliser le remplacement d'une valeur, il faut utiliser le symbole `$` comme pour les dés types.

Une fois la formule créé, la valeur qui sera "remplacée" dans le `$` devra être entre crochet `[]`. Par exemple, si la formule est `$ + 2`, alors le dé lancé devra être écrit comme `1d6 + [2]`.

:::example
- <u>Formule personnalisée</u> : `$ + 2`
- <u>Dé lancé</u> : `1d6 + [2]`
- <u>Résultat</u> : Si le dé fait `4`, alors le résultat final sera `4 + 2 = 6`.
:::

:::example[Plus complexe]
- <u>Formule personnalisée</u> : `$>85?85{cs:>=5+($-85)}:$`
- <u>Dé lancé</u> : `1d100>=[$dextérité+$force+$pugilat]`
- <u>Résultat</u> : `1d100>={{$dextérité+$force+$pugilat>85?85{cs:>=5+($-85)}:$dextérité+$force+$pugilat}}` (*oui, ceci est une formule valide*)
:::

Les dés peuvent être utilisés à la fois dans la formule personnalisée que dans le dé lancé. Par exemple, si la formule est `$ + 2d6`, alors le dé lancé devra être écrit comme `1d6 + [2]`. Le résultat final sera donc la somme du dé lancé et de deux dés à six faces.

## Configuration

:::usage
**`/user_config formule_personnalisée configurer (formule)`**
- `formule` : La formule personnalisée à utiliser. Elle doit être une formule valide Mathjs, avec le symbole `$` pour représenter la valeur entre crochet `[]`.
:::

Si l'option `formule` est laissée vide, la formule personnalisée sera supprimée pour l'utilisateur ou le serveur.

Lors de la configuration, les formules sont vérifiées contre les règles de Mathjs. Si la formule n'est pas valide, un message d'erreur sera affiché.

:::tip
La commande administrative `/config formule_personnalisée` fonctionne de la même manière.
:::

## Affichage

:::usage
**`/user_config formule_personnalisée afficher`**
:::

Permet d'afficher la formule personnalisée actuellement configurée pour l'utilisateur ou le serveur. Si aucune formule n'est configurée, un message d'erreur sera affiché.

:::tip
Son alter-égo administratif `/config formule_personnalisée afficher` fonctionne de la même manière.
:::