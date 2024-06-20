---
title: Conseil
sidebar_position: 5
---

- Évitez d'enregistrer tous les dés dans le modèle du serveur, surtout si leur nombre est important. En effet, bien qu'il n'y ait pas de limite au nombre de dés qui peuvent être enregistré, l'affichage de la liste et du filtre est limité à 25 (limité par discord). Il est préférable d'enregistrer spécifiquement, par joueur, uniquement les dés auxquels ils ont accès, tels que les armes qu'ils utilisent ou leurs compétences. Il n'est pas, par exemple, nécessaire qu'un archer ait accès à tous les dés de combat, mais seulement à ceux liés à son arc.

- Les fiches ne sont pas conçues pour recevoir les bonus et les malus temporaires ou d'équipement, qui doivent plutôt être utilisés directement dans la commande `/dbroll`. Le bot ne prend pas en charge les équipements, et vous ne pouvez pas créer de colonnes "bonus" ou "malus" pour chaque caractéristique. Cependant, il est possible de modifier les valeurs des statistiques enregistrées au besoin, notamment dans le cas de la distribution de points après avoir gagné un niveau.

- Bien que le bot vise à être aussi universel que possible, certaines [limitations](./register/limitation) peuvent faire en sorte qu'il ne vous convienne pas, notamment si vous utilisez un système basé sur de nombreuses compétences ou des dés spécifiques. Cela dit, vous n'êtes pas obligé d'enregistrer TOUS les dés spéciaux.

- La vérification des statistiques est minimale (elle ne vérifie que les valeurs numériques et, si elles existent, les valeurs minimales et maximales) : il est impératif que les MJ effectuent une vérification préalable, ansi que après les éditions. Si vous avez configuré les journaux (avec `/logs`), vous recevrez un message en cas de modification, accompagné d'une liste des modifications apportées.
