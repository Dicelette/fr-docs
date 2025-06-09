---
title: Dés
sidebar_position: 2
---

Il existe deux types de dés :

- Le dé utilisé avec `dbroll` (le **dé type**).
- Les dés enregistrés pour `dbd` (les **dés sauvegardés**).

Les deux types de dés suivent la syntaxe de [dice-roller](https://dice-roller.github.io/documentation/), mais prennent également en charge [des expressions et notations](../../introduction/expression.mdx).

Pour viser une statistique, la méthode diffère selon le type de dé :
- Pour un dé type, utilisez le mot-clé `$`. Ce symbole sera remplacé par la valeur de la statistique utilisée par `/dbroll`.
- Pour les dés enregistrés, utilisez simplement les noms des statistiques.

:::tip[Exemple]
- Pour un dé type : `1d6>$` ou `1d6+$`
- Pour un dé enregistré : `1d6 > Force` ou `1d6 + Force`

Pour un dé basé sur une formule :
- Pour un dé type : `1d6 + {{ceil($ / 2)}}`
- Pour un dé enregistré : `1d6 + {{ceil(Force / 2)}}`

Il est également possible de comparer contre une formule :
- Pour un dé type : `1d6 > {{ceil($ / 2)}}`
- Pour un dé enregistré : `1d6 > {{ceil(Force / 2)}}`
:::

La présence du `$` rend la statistique obligatoire. Sinon, le dé pourra être lancé sans fiche sauvegardée.

## Dés enregistrés

Vous pouvez personnaliser les dés sauvegardés avec différentes syntaxes :

- **Critique personnalisé :** Si vous utilisez des critiques personnalisées avec `$`, le **nom du dé** doit inclure la **statistique entre parenthèses**, comme dans `Instinct Animal (Force)`. Consultez la section [Critiques personnalisées](./critics.md#les-critiques-personnalisées) pour plus de détails.
- **Nom de la statistique :** Permet de référencer une statistique directement dans le dé.

:::example

|           Titre           | Nom du dé               | Valeur remplacée                                         | Syntaxe       | Exemple    |
|:-------------------------:|-------------------------|----------------------------------------------------------|---------------|------------|
|  **Statistique précise**  | Force                   | `Force=20`                                               | `1d6 > Force` | `1d6 > 20` |
| **Critique personnalisé** | Instinct Animal (Force) | <li>`Force=20`</li><li>Critique personnalisé : `>$`</li> | `1d6`         | `1d6>20`   |

:::