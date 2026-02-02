---
title: Statistiques
sidebar_position: 1
---

Chaque statistique possède :
- un **nom**,
- une **valeur minimale** (`min`),
- une **valeur maximale** (`max`)
- et éventuellement une **combinaison** (`combinaison`) de plusieurs autres statistiques.

`combinaison` ne peut coexister avec `min` et `max` et les statistiques combinées ne sont pas décomptées du total de points alloués dans le champ `total`.

Vous pouvez exclure certaines statistiques de la sélection lors d’un jet de dés, ce qui empêche leur utilisation dans les commandes.  
Cela est utile pour les statistiques uniquement utilisées dans des formules ou non destinées à des jets.

### Exemple de configuration

| Nom       | min | max | combinaison       | Exclure du jet |
|-----------|-----|-----|-------------------|:--------------:|
| Force     | 1   | 10  |                   |                |
| PV        |     |     | Constitution+Endu |       ✅        |
| Dextérité | 1   | 12  |                   |                |

Chaque statistiques doit être unique. Elle peut comporter tout type de caractère, sauf commencer par un `-`.

:::info
Dans le cas où la statistique contient un espace et qu'il est souhaité de l'utiliser comme raccourci dans [la notation directe](../../usage/message.md), les espaces doivent être remplacé par un n'importe quel caractère (`.`, `_`…)
:::
<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../../introduction/format.mdx).</small>