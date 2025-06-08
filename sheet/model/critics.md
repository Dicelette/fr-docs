---
title: Critiques
sidebar_position: 3
---

Il est possible de définir :
- Des critiques "basiques", qui sont liées aux dés naturels et peuvent être configurées pour représenter un échec critique ou un succès critique.
- Des critiques personnalisées, qui peuvent s'appliquer aux dés naturels ou aux résultats totaux.

Dans les deux cas, par défaut, les critiques ne sont actives que sur la commande `/dbroll` et permettent d'afficher un message spécial selon le résultat.

## Les critiques basiques

Les critiques basiques ne peuvent être liées qu'à une égalité avec le dé naturel. La valeur est paramétrable, mais le message affiché est fixe.
Ainsi :
- En cas de succès critique, le message affiché sera : `Succès critique`.
- En cas d'échec critique, le message affiché sera : `Échec critique`.

## Les critiques personnalisées

Les critiques personnalisées permettent de définir une valeur pour laquelle un message personnalisé sera affiché. Contrairement aux critiques basiques, elles peuvent être basées sur un total **ou** un dé naturel et supportent les formules. De plus, elles peuvent être utilisées sur des dés de compétences. Il est possible de définir jusqu'à 22 critiques personnalisées.

Ils autorisent l'utilisation du symbole joker `$` (comme pour la comparaison avec les dés types) afin de comparer avec la statistique utilisée. Il est également possible d'utiliser le nom d'une statistique ou de combiner avec d'autres dés.

:::example[Call of Cthulhu]
*Référence* : [Call of Cthulhu RPG Wiki](https://cthulhuwiki.chaosium.com/rules/combat.html)  
Dans le cas de Call of Cthulhu, les succès sont basés sur la valeur de la statistique. Le dé type sera donc `1D100<=$`.
Les critiques personnalisées seront :
- "Succès Majeur" : `<=round($/2)`
- "Succès Extrême" : `<=round($/5)`
:::

### Dés de compétences et critiques personnalisées

Seuls les dés avec un comparateur seront affectés par les critiques personnalisées.

Si un critique personnalisé utilise le symbole `$`, la valeur utilisée doit se trouver dans le **nom** du dé de compétence, entre parenthèses.

:::example
Pour un critique personnalisé dont la valeur est `<=$`, si le dé de compétence se nomme `Instinct Animal (Force)`, alors le `$` sera remplacé par la valeur statistique de Force, si elle existe.
Si le nom n'est pas trouvé, alors la comparaison ne sera pas utilisée et le dé sera jeté normalement.
:::

Il est également possible de combiner dans le nom du dé différentes statistiques, ainsi que des formules ou des jets de dés.

:::note
Si le nom contient lui-même un jet de dé, ce dernier sera affiché non pas dans le résultat, mais dans le commentaire du dé, à la place de la formule.
:::