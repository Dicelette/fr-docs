---
title: Enregistrement d'un Modèle
sidebar_position: 2
---
# Enregistrement d'un Modèle

Pour commencer, vous devez **générer** un nouveau modèle. Utilisez `/register` suivi du nom du modèle. Vous pouvez aussi créer un modèle vide en utilisant `/générer` ou en utilisant le formulaire disponible [ici même](./form.mdx).

Cette commande vous permet de créer un fichier `JSON` avec les paramètres suivants (optionnels) :

- `nom` : Le nom des statistiques, séparées par des virgules. Si un nom contient un espace, entourez-le de guillemets.
- `dé` : Le type de dés à lancer, qui peut inclure une formule.
- `total` : Le nombre total de points que les joueurs peuvent répartir.
- `personnage` : Rendre obligatoire l'inscription d'un nom de personnage.
- `succès_critique` : La valeur considérée comme un succès critique.
- `échec_critique` : La valeur considérée comme un échec critique.
- `compétence` : Ajouter des champs pour des dés de compétences ou d'attaque.

Consultez les exemples de modèle dans les fichiers `template` [ici](https://github.com/Dicelette/discord-dicelette/tree/main/template).

:::info Remarque
Les statistiques et les dés sont facultatifs :
- Sans statistiques, vous ne pourrez pas utiliser la commande `/dbroll`.
- Sans dés, vous ne pourrez pas utiliser `/dbd`. 
:::

## Dés

Il y a deux types de dés :

- Le dé utilisé avec `dbroll` (le **dé type**).
- Les dés enregistrés pour `dbd` (les **dés sauvegardés**).

Les deux types de dés suivent la syntaxe de [dice-roller](https://dice-roller.github.io/documentation/). Vous pouvez utiliser des formules mathématiques complexes avec `{{` et `}}`.

Pour viser une statistique, cela est différent selon le type de dé :
- Pour un dé type, il faut utiliser `$`. Ce symbole sera utilisé par la valeur de la statistique utilisée par `/dbroll`.
- Pour les dés enregistrés, il suffit d'utiliser les noms des statistiques. 

:::tip[Exemple]
- Pour un dé type : `1d6>$` ou `1d6+$`
- Pour un dé enregistré : `1d6 > Force` ou `1d6 + Force`

Pour un dé basé sur une formule :
- Pour un dé type : `1d6 + {{ceil($ / 2)}}`
- Pour un dé enregistré : `1d6 + {{ceil(Force / 2)}}`

Il est également possible de comparer avec une formule :
- Pour un dé type : `1d6 > {{ceil($ / 2)}}`
- Pour un dé enregistré : `1d6 > {{ceil(Force / 2)}}`
:::

## Statistiques

Chaque statistique a un nom, une valeur minimale (`min`), une valeur maximale (`max`) et une option de combinaison (`combinaison`). 
- `min` et `max` correspondent à la minimale et/ou maximale que peut prendre cette valeur lors de l'enregistrement.
- `combinaison` correspond à une combinaison de plusieurs autres statistiques. L'utilisation de ce champ ne peut coexister avec `min` et `max` et les statistiques combinées ne seront pas décomptées du total de point alloué dans le champ `total`.

## Critiques

Il est possible de définir :
- Des critiques "basiques", qui sont liés aux dés naturels, et peuvent être configuré pour être un échec critique et un succès critique.
- Des critiques personnalisés, qui peuvent être sur des dés naturels ou des résultats totaux.  

Dans les deux cas, par défaut, les critiques ne sont qu'actifs que sur la commande `/dbroll`, et permettent d'afficher un message spécial selon le résultat.

### Les critiques basiques

Ils ne peuvent être liés qu'à une égalité avec le dé naturel. La valeur est paramétrable, mais pas le message affiché.
Ainsi, dans le cas où :
- Vous aurez une valeur de succès critique, le message affiché sera : `Succès critique`
- Dans le même cas, pour un échec critique, le message affiché sera `échec critique`.

Les messages peuvent être modifiés par les "critiques personnalisés"

### Les critiques personnalisés

Ces derniers permettent de créer une valeur pour lequel un message personnalisés sera affiché.
Les critiques personnalisés, contrairement aux critiques basiques, permettent de comparer à un total **ou** un dé naturel, et supportent les formules.
Il est possible d'avoir, en tout, jusqu'à 22 critiques personnalisés.

Cela permet, par exemple, de créer des critiques liés à la valeur d'une statistique, en utilisant `$` comme pour la comparaison avec les dés types. En outre, il est possible d'utiliser le nom d'une statistique ou encore de combiner avec d'autres dés.

:::example [Call of Cthulhu]
*Référence* : [Call of Cthulhu RPG Wiki](https://cthulhuwiki.chaosium.com/rules/combat.html)
Dans le cas de Call of Cthulhu, les succès sont basés sur la valeur de la statistique. Le dé type sera donc `1D100<=$`.
Les critiques personnalisés seront :
- "Succès Majeur" : `<=round($/2)`
- "Succès extrême" : `<=round($/5)`
:::

Enfin, il est possible d'affecter les critiques customisés et leur message avec les dés de compétences en cochant le bouton correspondant.


#### Dés de compétences et critiques customisé

Seuls les dés avec un comparateur seront affectés par les critiques personnalisé.


Dans le cas où un critique personnalisé utilise le symbole `$`, la valeur utilisé doit se trouver dsns le **nom** du dé de compétence, entre parenthèse. 

:::example
Pour un critique personnalisé dont la valeur est `<=$`, si le dé de compétence se nomme "Instinct Animal (Force)`, alors le `$` sera remplacé par la valeur statistique de force, si elle existe.
:::

Comme pour les autres types de comparaison, les dés et les formules sont acceptés.


<details>
  <summary>Modèle vide</summary>
  ```json
   {
	"$schema": "https://raw.githubusercontent.com/Dicelette/discord-dicelette/main/template/schema.json",
	"charName": false,
	"statistics": {
		"name": {
			"min": 1,
			"max": 20
		},
		"combinaison": {
			"combinaison": "2d6"
		}
	},
	"diceType": "1d20",
	"critical": {
		"failure": 1,
		"success": 20
	},
	"total": 80,
	"customCritical": {
		"name": {
			"sign": "=",
			"value": "15",
			"onNaturalDice": true,
			"affectSkill": true
            }
        }
    }
    ```
</details> 

## Prochaine étape

Une fois que le modèle est prêt, utilisez `/register [#channel] [fichier] (#user_chan) (#personnage_privé)`. 
- `#channel` est le canal où le modèle sera envoyée. Il sera ensuite utilisée pour la création de fiche.
- `fichier` est le fichier `JSON` créé précédemment.
- `#user_chan` est le canal où les fiches seront publiées.[^1]
- `#personnage_privé` est, de manière similaire à `#user_chan`, mais les fiches qui seront publiées dans ce salon seront uniquement visibles par l'utilisateur qui a enregistré la fiche, ou par ceux qui ont accès à ce salon (ainsi que les personnes ayant la permission `GÉRER LES RÔLES`). Si ce salon n'est pas défini, la fonction de fiche privée sera désactivée.
- `?mettre-à-jour` : Permet de mettre à jour toutes les anciennes fiches de personnages si elles existent.
- `?tout_supprimer` : Supprime toutes les anciennes fiches de personnages si elles existent.
:::warning À propos des fiches privées
Si la fiche n'est pas marquée comme privée mais est publiée dans un salon auquel les utilisateurs n'ont pas normalement accès, ils pourront tout de même voir la fiche avec les commandes `/afficher` et `/graph`.
:::

L'embed sera épinglé pour faciliter l'accès.

![embed](/assets/register/embed_template.png)

:::warning Attention
Vous devez réenregistrer le modèle si vous souhaitez modifier le canal par défaut pour les feuilles privées et publiques. Mais l'utilisateur enregistré n'a pas besoin d'être réenregistré car le canal et l'identifiant du message sont sauvegardés dans la base de données.
Si vous souhaitez déplacer toutes les feuilles vers un autre canal, vous devez utiliser la commande [`/export`](../config/import_export.md).
:::

[^1]: Il est possible d'utiliser un forum, qui créera automatiquement un post pour le personnage. Le joueur (ainsi que les administrateurs) seront mentionnés dans le post. 
