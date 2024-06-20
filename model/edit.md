---
title: Modifier une fiche
sidebar_position: 3
---
Une fois que l'utilisateur est validé, sa fiche sera automatiquement publiée dans un thread ou dans le canal choisi. Toutes les fiches suivront ce format :

![user embed](/assets/edit/user_embed.png)

Seul le modèle et l'utilisateur seront toujours présents, à moins qu'aucun dé-type et aucun succès/échec critique n'aient été enregistrés dans le modèle.

Si toutes les informations sont enregistrées, vous aurez accès à trois boutons :
- Modifier les statistiques
- Modifier les dés enregistrés (qui permet d'enregistrer plusieurs nouveaux dés, mais shh...)
- Ajouter un nouveau dé.

## Modification des Statistiques

![edit stats](/assets/edit/edit_stats.png)

Le modal sera pré-rempli par une liste comme suit :
```md
- NOM : valeur
- NOM : valeur
- NOM : COMBINAISON
```

:::warning
Il est impératif de conserver cette liste telle quelle pour que le bot puisse lire correctement les statistiques.
:::

Vous pouvez supprimer les valeurs en utilisant `X` ou en laissant vide, comme ceci :
```md
- NOM : X
```

Si des statistiques ont été supprimées du modèle, elles seront automatiquement retirées de la liste. De plus, elles seront automatiquement ajoutées dès leur ajout au modèle, avec une valeur par défaut de "0".

Il est possible de modifier les combinaisons.

Enfin, les valeurs ne seront pas vérifiées par rapport au total enregistré initialement dans le modèle. Les maîtres de jeu doivent donc vérifier les valeurs lors de l'édition.

:::note
Si les statistiques sont modifiées et que les logs sont activés, un message de modification sera envoyé dans le canal configuré dans les logs.
:::

## Modification des Dés

Tout comme pour les statistiques, le modal sera pré-rempli par une liste comme suit :
```md
- NOM : dés
```

Tout comme lors de l'enregistrement, les dés seront évalués pour vérifier leur validité. De plus, vous pouvez ajouter autant de dés que vous le souhaitez !

Comme pour les statistiques, il est essentiel de respecter la liste et sa syntaxe. Vous pouvez supprimer des champs en remplaçant la valeur par "X" ou "0".

![edit dice](/assets/edit/edit_dice.png)

## Ajout d'un Nouveau Dé

L'ajout d'un dé fonctionne exactement comme lors de l'enregistrement d'un personnage.