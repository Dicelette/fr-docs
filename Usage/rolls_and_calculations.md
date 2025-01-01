---
title: Jets de dés et calculs
---

## Expressions Mathématiques avec MathJS

Le bot utilise la bibliothèque [mathjs](https://mathjs.org/) pour évaluer les expressions mathématiques. Vous pouvez utiliser des expressions mathématiques complexes lorsqu'elles sont entre `{{` et `}}`.

### Exemples d'Expressions Mathématiques

- `1d6 + {{ceil($ / 2)}}`
- `1d6 > {{ceil($ / 2)}}`

## Jets Uniques Partagés (Réutilisation de Résultats)

Il est possible d'utiliser la syntaxe `dé;&+x;µ*y` pour lancer un seul dé et appliquer différentes formules sur ce même dé, de façon à afficher le résultat de chaque formule. Le `&` symbolise le résultat du dé.

:::warning[Attention]
Vous devez obligatoirement ne pas avoir d'espace avant et après la séparation entre les formules, sinon le bot considérera la suite comme des commentaires.
:::

:::example
```
/roll 1d20;&+5;&*2
```
Affichera comme résultat :
```
  ※ `1d20` ⟶ `[10]` = ` 10 `
  ◈ `[1d20]+5` ⟶ `[10]+5` = ` 15 `
  ◈ `[1d20]×2` ⟶ `[10]×2` = ` 20 `
```
:::

::::tip
Il est possible d'utiliser des dés dans les formules, mais seul le premier dé sera sauvegardé et réutilisé.
:::example[ `1d20;&+1d4;&*2`]
```
  ※ `1d20` ⟶ `[7]` = ` 7 `
  ◈ `[1d20]+1d4` ⟶ `7+[1]` = ` 8 `
  ◈ `[1d20]×2` ⟶ `[7]×2` = ` 14 `
```
:::
::::

Pour commenter entre chaques jets, il faut utiliser la syntaxe `[commentaire]`. Un commentaire global devra utiliser la syntaxe du `# commentaire` à la fin des dés. 
:::example[`1d20;&-2[perte pv]`]
  ※ `1d20` ⟶ `[2]` = ` 2 `
  ◈ <u>perte pv</u> — `[1d20]-2` ⟶ `[2]-2` = ` 0 `
:::

Enfin, il est possible de cacher le premier dé avec la syntaxe `(dé)` :
:::example[`(1d20);&>100;&+2`]
  **Échec** — `[1d20]>100` ⟶ `[12]>100` = ` 12<100 `
  ◈ `[1d20]+2` ⟶ `[12]+2` = ` 14 `
:::

:::danger[Il n'est pas possible d'utiliser les dés en masse dans cette syntaxe.]
:::

## Lancers en Masse (Bulk Rolls)

Le bot prend également en charge la notation `x#(dés)` pour les lancers "en masse" (bulk roll), vous permettant ainsi de gagner du temps lors de vos sessions de jeu.
