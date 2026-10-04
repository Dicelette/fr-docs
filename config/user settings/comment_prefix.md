---
title: Préfixe des commentaires
sidebar_position: 4
---
Par défaut, il est possible de modifier le commentaire d'un jet de dés en répondant au message du résultat avec un commentaire préfixé par `///`. Ce préfixe peut être personnalisé par chaque utilisateur.

:::usage
**`/settings commentaire_prefixe configurer (prefixe)`**
- `prefixe` : Le préfixe à utiliser pour modifier les commentaires. Il peut être n'importe quelle chaîne de caractères. Les regex sont supportés.
:::

Lorsque l'option `prefixe` est laissée vide, le préfixe de modification des commentaires sera réinitialisé à la valeur par défaut (`///`).

Les regex sont supportés avec la syntaxe suivante : `$/regex/flags$`.

:::example[ `$/\({2}(.*)\){2}/$` qui matchera `((commentaire))` et remplacera le commentaire par `commentaire` ]
:::

Si vous utilisez un regex, il y a deux possibilités :
- Dans le cas où vous capturez un groupe (`(.*)` dans l'exemple), le commentaire sera remplacé par le contenu du groupe capturé.
- Dans le cas où vous ne capturez pas de groupe, le commentaire sera remplacé par le texte détecté par le regex, en incluant donc le texte du regex. Par exemple, avec le regex `$/\({2}.*\){2}/$`, le commentaire sera remplacé par `((commentaire))` et non pas par `commentaire`.

## Affichage

Pour afficher le préfixe de modification des commentaires, vous pouvez utiliser la commande `/settings commentaire_prefixe afficher`.

:::tip
Pour simplifier l'affichage, le regex est affiché sans les délimiteurs de détection (`$` et `$`). Par exemple, le regex `$/\({2}(.*)\){2}/gm$` sera affiché comme `/\({2}(.*)\){2}/gm`.
:::
