---
title: "Import et export de données"
sidebar_position: 3
---

Les commandes suivantes permettent d'importer et d'exporter des données depuis et vers un fichier CSV.
:::tip Au sujet des dés
Il est tout à fait possible d'importer des dés spécifiques pour la commande [`/dbd`](../usage/model.mdx#dbd-dbd), mais vous devez remplir les cases de la colonne `dice` sous la forme suivante :
```md
- [dé] : [valeur]
```
Par exemple :
```md
'- Athlétisme : 1d20+Force
- Discrétion : 1d20+Dextérité
```
:::

:::important À propos d'Excel
- Excel n'aime pas les cases dont le contenu comme par `-` et peut les interpréter comme des formules. Si tel est le cas, vous devez ajouter `'` devant le `-`.
- Excel peut avoir des problèmes en lisant et exportant les textes contenant des accents. Il est recommandées d'enregistrer le fichier en UTF-8-BOM, en utilisant par exemple Notepad++ ou VSCode.
- Tout comme la liste des dés, si vous utiliser l'ID du joueur, il faudra ajouter `'` devant (comme `'123456789012345678`) pour éviter que Excel ne le transforme en nombre.

Il est vivement conseiller de désactiver les conversions automatiques d'Excel: 
![Excel](/assets/csv/EXCEL_FR_disable.png)

Et de désactiver la règle de vérification des erreurs "Nombres mis en forme en tant que texte ou précédés d'une apostrophe" dans les options de vérification des erreurs (Formules > Règle de vérification des erreurs) :
![](/assets/csv/FR_disable_nb.png)

:::

![Example](/assets/csv/example.png)

## Import

:::usage
**`/import [csv]`**
:::

La commande `/import` permet d'importer des données depuis un fichier CSV. Vous pouvez télécharger le modèle en utilisant la commande `/csv` et le remplir avec les personnages et statistiques que vous souhaitez importer.

:::important
- Les données importées écraseront les données existantes, mais ne supprimerons pas les personnages non présents dans le fichier. De plus, si le personnage du joueur existe déjà, ses données seront écrasées dans la base de donnée mais le message du personnage ne sera pas supprimé : vous devrez le faire manuellement.
- Le minimum, maximum ainsi que le total de points n'est pas vérifiés (afin de permettre l'import de personnages ayant acquis de l'expérience ou qui sont différents des autres, comme des monstres).
- Les combinaisons ne doivent pas être rentrée telles quelles mais doivent être directement calculées. Par exemple, si la colonne PV est une combainaison de `Constitution` et `Endurance` vous devez rentrer le résultat des colonnes directement. Il n'y a pas de problème à utiliser des formules dans un CSV, car l'exportation du fichier incluera seulement le résultat !
:::

Les colonnes suivantes sont nécessaires pour l'import :
- `user` : L'ID Discord du joueur ou son nom d'utilisateur (sans le `@`).
- `charName` : En fonction de votre modèle, peut être obligatoire. C'est le nom du personnage.
- `isPrivate` : `true` ou `false` pour définir si la fiche est privée ou non. Si votre modèle n'utilise pas de fiche privée, vous pouvez laisser cette colonne vide.
- Les colonnes suivantes doivent être les statistiques de votre modèle.

Les colonnes suivantes sont facultatives :
- `avatar` : Le lien vers l'avatar du personnage. Si vous n'utilisez pas d'avatar, vous pouvez laisser cette colonne vide. L'avatar utilisé dans l'affichage sera celui du joueur.
- `channel`: Permet de définir un channel (prend également en charge les fils et les forums[^1]), où sera envoyée la fiche, plutôt que d'utiliser les channels par défaut définis lors de l'enregistrement du modèle.
- `dice` : Les dés spécifiques pour la commande `/dbd`. Si vous n'utilisez pas cette commande, vous pouvez laisser cette colonne vide, voire la supprimer. 


## Exporter des données

:::usage
**`/export [csv] (fiche_privée_uniquement)`**
:::

Cette commande permet d'exporter la liste des personnages et des statistiques dans un fichier CSV. 
En fonction de l'option `private`, la liste fournie sera différente : 
- Si `false`, elle incluera **uniquement** les personnages dont la fiche est **publique**.
- Si `true`, elle incluera **uniquement** les personnages dont la fiche est **privée**.
- Si elle est omise, elle inclura **tous** les personnages, quelque soit le statut de la fiche.

Le fichier CSV exporté utilise le point virgule comme séparateur.

[^1]: Il est possible d'utiliser un forum, qui créera automatiquement un post pour le personnage. Le joueur (ainsi que les administrateurs) seront mentionnés dans le post. 