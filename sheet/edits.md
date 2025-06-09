---
title: Modifier et supprimer un personnage
sidebar_position: 3
---

Une fois que l'utilisateur est validé, sa fiche sera automatiquement publiée dans un thread ou dans le canal choisi. Toutes les fiches suivront ce format :

![user embed](/assets/edit/user_embed.png)

Seul le modèle et l'utilisateur seront toujours présents, à moins qu'aucun dé-type et aucun succès/échec critique n'ont été enregistrés dans le modèle.

Si toutes les informations sont enregistrées, vous aurez accès à trois boutons :
- Modifier l'avatar de l'embed,
- Modifier les statistiques
- Modifier les dés enregistrés (qui permet d'enregistrer plusieurs nouveaux dés, mais shh...)
- Ajouter un nouveau dé.

## Suppression
:::usage
**`/supprimer_char [@joueur] (*personnage)`**
:::

La commande `supprimer_char` permet de supprimer un personnage ou un joueur de la base de données. 

Elle demande :
- `[@joueur]` - Le nom du joueur
- `(*personnage)` - Et/ou le nom du personnage, en fonction de l'utilisateur sélectionné.

En l'absence de nom de personnage, cela supprimera toutes les données du joueur. Si vous voulez supprimer uniquement le "personnage sans nom" d'un joueur, vous pouvez le faire en choisissant "défaut" dans la liste du nom du personnage.

## Edition
### Modifier les données d'utilisateur

![fr_edit](/assets/edit/french/user.png)

Les commandes du menu déroulant permettent de modifier les données correspondantes.
Si vous utilisez une ancienne version, vous devez utiliser les commandes listés.

#### Modification de l'image

![edit image](/assets/edit/image.png)

:::warning
Les images stockés sur discord ne peuvent être utilisés car leurs liens changent régulièrement. Il est donc obligatoire d'utiliser des liens externes, par exemple, en utilisant [imgur](https://imgur.com/).

[Regardez ici pour plus d'information](https://kulturegeek.fr/news-298973/discord-passe-liens-temporaires-lhebergement-fichiers).
:::

:::usage[commande]
**`/edit avatar [lien] (@joueur) (*personnage)`**
:::
Par défaut, la commande modifiera l'image de la personne ayant utilisé la commande. Seuls les modérateurs peuvent modifier l'image d'un autre joueur.

#### Renommer un personnage
![rename](/assets/edit/french/rename.png)

Tout comme la commande listée plus haut, elle ne permet pas d'avoir des personnages ayant les mêmes noms pour un même utilisateur. Dans le cas contraire, l'action sera annulée et une erreur s'affichera.

:::usage[commande]
**`/edit rename [nouveau_nom] (@joueur) (*personnage)`**
:::

#### Déplacer à un nouvel utilisateur
![move](/assets/edit/french/move.png)

Cela **déplacera** le personnage à un nouvel utilisateur, supprimant les données du joueur précédent. 
Dans le cas où l'utilisateur "receveur" a un personnage du même nom, l'action sera annulée et une erreur s'affichera.

:::usage[commande]
**`/edit user [@utilisateur] (@joueur) (*personnage)`**
:::

### Modification des statistiques

![edit stats](/assets/edit/stats.png)

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

### Modification des dés

Tout comme pour les statistiques, le modal sera pré-rempli par une liste comme suit :
```md
- NOM : dés
```

Tout comme lors de l'enregistrement, les dés seront évalués pour vérifier leur validité. De plus, vous pouvez ajouter autant de dés que vous le souhaitez !

Comme pour les statistiques, il est essentiel de respecter la liste et sa syntaxe. Vous pouvez supprimer des champs en remplaçant la valeur par "X" ou "0".

![edit dice](/assets/edit/dice.png)

### Ajout d'un nouveau dé

L'ajout d'un dé fonctionne exactement comme lors de l'enregistrement d'un personnage.
