---
title: Critiques
sidebar_position: 3
---

Il est possible de définir :
- des **critiques basiques**, liées au dé naturel (ex. 1 sur 1d20), pour représenter un succès ou échec critique ;
- des **critiques personnalisées**, qui s'appliquent au dé naturel ou au résultat total, et qui peuvent utiliser des formules ou la valeur d'une statistique.

Par défaut, les critiques ne sont actives que sur la commande `/dbroll` et permettent d'afficher un message spécial selon le résultat.

## Critiques basiques

Les critiques basiques ne concernent que l’égalité sur le dé naturel.  
Le message affiché est fixe :
- Succès critique : `Succès critique`
- Échec critique : `Échec critique`

**Exemple de configuration :**

| Type            | Dé naturel | Valeur | Message affiché      |
|-----------------|------------|--------|----------------------|
| Succès critique | 1d20       | 20     | Succès critique      |
| Échec critique  | 1d20       | 1      | Échec critique       |

## Critiques personnalisées

Les critiques personnalisées permettent de définir une valeur ou une formule pour afficher un message personnalisé.  
Elles peuvent s'appliquer sur le total ou le dé naturel, et supportent les formules mathématiques. Jusqu'à 22 critiques personnalisées sont possibles.

Vous pouvez utiliser le symbole `$` (comme pour les dés types), le nom d'une statistique ou des combinaisons de dés.

:::example[Appel de Cthulhu]
*Référence* : [Call of Cthulhu RPG Wiki](https://cthulhuwiki.chaosium.com/rules/combat.html)  
Dans l'Appel de Cthulhu, les succès sont basés sur la valeur de la statistique. Le dé type sera donc `1D100<=$`.  
Les critiques personnalisées seront :
- "Succès Majeur" : `<=round($/2)`
- "Succès Extrême" : `<=round($/5)`
:::

### Dés de compétence et critiques personnalisées

Seuls les dés avec un comparateur seront affectés par les critiques personnalisées.

Si un critique personnalisé utilise `$`, la valeur utilisée doit se trouver dans le **nom** du dé de compétence, entre parenthèses.

:::example
Pour une formule critique `<=$`, si le dé de compétence se nomme `Instinct Animal (Force)`, alors `$` sera remplacé par la valeur de Force (si elle existe).
Si le nom n'est pas trouvé, la comparaison ne sera pas utilisée et le dé sera jeté normalement.
:::

Vous pouvez aussi combiner différentes statistiques, formules ou jets de dés dans le nom du dé.

:::note
Si le nom contient lui-même un jet de dé, ce dernier sera affiché dans le commentaire du dé, et non dans le résultat.
:::

## À retenir

- Les critiques personnalisées ne fonctionnent que sur les dés avec comparateur.
- La valeur `$` est remplacée par la statistique du nom du dé (entre parenthèses).
- Jusqu'à 22 critiques personnalisées par modèle.

Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../../introduction/format.md).