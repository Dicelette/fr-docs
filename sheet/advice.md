---
title: Conseils et limitations
sidebar_position: 6
---

## Limitations

Voici les limitations à prendre en compte lors de l'enregistrement et de l'édition de modèles et de fiches :

- Un maximum de 25 statistiques et de dés sont pris en charge (causé par la limitation du nom de champ dans un embed discord).
- Il n'est pas possible de modifier des statistiques si elles n'existent pas dans le modèle original.
- Parfois, il est nécessaire de mettre à jour manuellement les fiches si le modèle est modifié. De plus, dans certains cas, les fiches doivent être entièrement réenregistrées. Si vous souhaitez modifier les emplacements des fiches et des fiches privées, il faudra faire `/export` puis `/import` pour les mettre à jour. Pour plus d'informations, [consultez la documentation](import_export.md).
- Lors de l'édition d'une fiche, les statistiques ne sont ni vérifiées par rapport au total ni par rapport à un maximum. De plus, il est impossible de contrôler les nombres de points dépensés par statistique dans les systèmes où 1 point dépensé dans une statistique n'est pas équivalent à 1 point de statistique.

## Conseils
- Évitez d'enregistrer tous les dés dans le modèle du serveur, surtout si leur nombre est important. En effet, il ne peut y avoir que 25 dés enregistrés, à cause de la limitation de l'affichage des champs sur les embeds utilisés. Il est préférable d'enregistrer spécifiquement, par joueur, uniquement les dés auxquels ils ont accès, tels que les armes qu'ils utilisent ou leurs compétences. Il n'est pas, par exemple, nécessaire qu'un archer ait accès aux dés d'utilisation d'une épée, mais seulement à ceux liés à son arc.

- Les fiches ne sont pas conçues pour recevoir les bonus et les malus temporaires ou d'équipement, qui doivent plutôt être utilisés directement dans la commande `/dbroll`. Le bot ne prend pas en charge les équipements, et vous ne pouvez pas créer de colonnes "bonus" ou "malus" pour chaque caractéristique. Cependant, il est possible de modifier les valeurs des statistiques enregistrées au besoin, notamment dans le cas de la distribution de points après avoir gagné un niveau.

- Bien que le bot vise à être aussi universel que possible, certaines [limitations](../sheet/advice.md#limitations) peuvent faire en sorte qu'il ne vous convienne pas, notamment si vous utilisez un système basé sur de nombreuses compétences ou des dés spécifiques. Cela dit, vous n'êtes pas obligé d'enregistrer TOUS les dés spéciaux.

- La vérification des statistiques est minimale (elle ne vérifie que les valeurs numériques et, si elles existent, les valeurs minimales et maximales) : il est impératif que les MJ effectuent une vérification préalable, ansi qu'après les éditions. Si vous avez configuré les journaux (avec `/config logs`), vous recevrez un message en cas de modification, accompagné d'une liste des modifications apportées. [Voyez ici pour plus d'information sur les journaux](../config/index.md).
