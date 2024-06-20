---
title: Commandes administratives
sidebar_position: 2
---

Toutes les commandes suivantes sont restreintes par défaut aux membres ayant la permission `Gérer les rôles`.

Vous pouvez voir la configuration actuelle du serveur avec la commande `/config`.

## Configuration

Les commandes suivantes sont réunies dans la commandes `/config` et permettent de configurer le bot pour votre serveur.

### Logs

:::usage
**`/config logs (#channel)`**
:::

La commande `logs` offre la possibilité de d'enregister un channel afin de : 
- Rapporter toutes les erreurs,
- Enregistrer toute modification apportée à un personnage.

Renvoyer la commande sans l'argument `#channel` permet de supprimer l'envoi des logs.

### Changer le canal de résultats

:::usage
**`/config result_channel (#channel)`**
:::

La commande `/config result_channel` permet de définir un canal pour recevoir les résultats des jets de dés, plutôt que d'utiliser un fil de discussion à chaque fois. L'ID du canal sera alors enregistré dans la base de données de la même manière que la commande `logs`.

Renvoyer la commande sans l'argument "channel" permet de supprimer le canal de résultats à l'instar de la commande `logs`.

### Supprimer l'auto-création des threads

:::usage
**`/config désactiver_threads [true/false]`**
:::

Si l'option est sur **true**, désactive la création, par défaut, des threads pour les jets de dés. Tout sera donc envoyé (sans suppression) dans le channel où la commande a été effectuée.

Les channels et fils préfixés par `🎲` ne recevront plus les logs non plus.

Elle désactive aussi l'envoie dans le channel éventuellement configuré par la commande `/config result_channel`.

L'option sur **faux** réactive le comportement normal du bot.

### Délai avant suppression des messages

:::usage
**`/config supprimer_après [temps]`**
:::

Par défaut, les messages de résultats des jets de dés sont supprimés après **3** minutes. Cette commande permet de changer le délais (jusqu'à 60 minutes) avant suppression des messages.

Si la valeur est mise à **0**, les messages ne seront plus supprimés.

Cette option est désactivée si `/config désactiver_threads` est activée.

:::tip
Cette commande permet d'avoir à la fois les logs dans un channels dédiés, tout en gardant le résultat indéfiniment dans le channel où le jet a été effectué.
:::

## Modèle et fiche de personnages
### Supprimer un personnage/joueur 

:::usage
**`/supprimer_char [@joueur] (*personnage)`**
:::

La commande `supprimer_char` permet de supprimer un personnage ou un joueur de la base de données. 

Elle demande :
- `[@joueur]` - Le nom du joueur
- `(*personnage)` - Et/ou le nom du personnage, en fonction de l'utilisateur sélectionné.

En l'absence de nom de personnage, cela supprimera toutes les données du joueur. Si vous voulez supprimer uniquement le "personnage sans nom" d'un joueur, vous pouvez le faire en choisissant "défaut" dans la liste du nom du personnage.

### Auto-Role

:::usage
- **`/config auto_role dé (@role)`**
- **`/config auto_role stats (@role)`**
:::

Ces commandes permettent d'ajouter automatiquement des rôles lorsque :
- Un dé est ajouté (`/config auto_role dé`)
- Des statistiques sont validées (`/config auto_role stats`)

Cela permet, notamment, d'autoriser l'usage de `/dbd` et `/dbroll` aux utilisateurs qui ont, effectivement, la possibilité d'utiliser ses deux commandes.

Si le rôle n'est pas fourni, l'option sera désactivée.

## Lancer de dés "maître de jeu"

:::info
Les deux commandes suivantes permettent aux maîtres de jeu de lancer des dés pour tous les joueurs enregistrés.
:::

:::usage
- **`/mj dbroll [@Joueur] [statistique] (*personnage)`**
- **`/mj dbd [@Joueur] [*nom du dé] (*personnage)`**
:::

Les deux commandes sont similaires à [dbroll](./model#dbroll-dbroll) et [dbd](./model#dbd-dbd), mais nécessite en plus de spécifier le joueur pour lequel le jet est effectué. Comme les autres commandes, il est possible de choisir un personnage appartenant à ce joueur ou de laisser le choix par défaut.

## Import et export de données

Les commandes suivantes permettent d'importer et d'exporter des données depuis et vers un fichier CSV.
:::tip Au sujet des dés
Il est tout à fait possible d'importer des dés spécifiques pour la commande [`/dbd`](./model.mdx#dbd), mais vous devez remplir les cases de la colonne `dice` sous la forme suivante :
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

### Import

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
- `channel` : Permet de définir un channel où envoyé la fiche, plutôt que d'utiliser les channels par défaut définis lors de l'enregistrement du modèle.
- `dice` : Les dés spécifiques pour la commande `/dbd`. Si vous n'utilisez pas cette commande, vous pouvez laisser cette colonne vide, voire la supprimer. 


### Exporter des données

:::usage
**`/export [csv] (fiche_privée_uniquement)`**
:::

Cette commande permet d'exporter la liste des personnages et des statistiques dans un fichier CSV. 
En fonction de l'option `private`, la liste fournie sera différente : 
- Si `false`, elle incluera **uniquement** les personnages dont la fiche est **publique**.
- Si `true`, elle incluera **uniquement** les personnages dont la fiche est **privée**.
- Si elle est omise, elle inclura **tous** les personnages, quelque soit le statut de la fiche.

Le fichier CSV exporté utilise le point virgule comme séparateur.