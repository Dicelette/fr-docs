---
title: Modèle
sidebar_position: 1
---

Pour commencer, vous devez **générer** un nouveau modèle. Vous pouvez créer un modèle vide en utilisant `/générer` ou en utilisant le formulaire disponible [ici même](../form.mdx).

:::usage
**`/generate (statistiques) (dé type) (total) (personnage) (succès_critique) (échec_critique) (compétence)`**
- `nom` : Le nom des statistiques, séparées par des virgules. Si un nom contient un espace, entourez-le de guillemets.
- `dé` : Le type de dés à lancer, qui peut inclure une formule.
- `total` : Le nombre total de points que les joueurs peuvent répartir.
- `personnage` : Rendre obligatoire l'inscription d'un nom de personnage.
- `succès_critique` : La valeur considérée comme un succès critique.
- `échec_critique` : La valeur considérée comme un échec critique.
- `compétence` : Ajouter des champs pour des dés de compétences ou d'attaque.
:::

Consultez les exemples de modèle dans les fichiers `template` [ici](https://github.com/Dicelette/discord-dicelette/tree/main/template).

:::info Remarque
Les statistiques et les dés sont facultatifs :
- `/dbroll` ne sera disponible que si vous **ne** spécifiez pas de dé type avec `$`. Dans le cas contraire, vous devrez enregistrer des statistiques pour pouvoir l'utiliser.
- Sans dés, vous ne pourrez pas utiliser `/dbd`. 
:::

## Prochaines étapes

Une fois que le modèle est prêt, enregistrez-le avec :

:::usage
**`/register [#channel] [fichier] (#user_chan) (#personnage_privé) (?mettre-à-jour) (?tout_supprimer)`**
- `#channel` : Canal dans lequel le modèle sera envoyé (utilisé pour la création de fiche).
- `[fichier]` : Fichier JSON créé précédemment.
- `#user_chan` : Canal où seront publiées les fiches.
- `#personnage_privé` : Canal pour les fiches privées (voir encadré ci-dessous).
- `?mettre-à-jour` : Met à jour toutes les anciennes fiches de personnages si elles existent.
- `?tout_supprimer` : Supprime toutes les anciennes fiches de personnages si elles existent.
:::

:::danger À propos des fiches privées
Si la fiche n'est pas marquée comme privée mais est publiée dans un salon auquel les utilisateurs n'ont pas normalement accès, ils pourront tout de même voir la fiche avec les commandes `/afficher` et `/graph`.
:::

L'embed sera épinglé pour faciliter l'accès.

![embed](/assets/register/embed_template.png)

:::danger
Vous devez réenregistrer le modèle si vous souhaitez modifier le canal par défaut pour les feuilles privées et publiques.  
Mais l'utilisateur enregistré n'a pas besoin d'être réenregistré, car le canal et l'identifiant du message sont sauvegardés dans la base de données.

Pour déplacer toutes les feuilles vers un autre canal, utilisez la commande [`/export`](../import_export.md).
:::

## TLDR
1. Créez le modèle avec le [formulaire](../form.mdx) ou la commande `/generate`.
2. Enregistrez le modèle avec `/register`.
3. Créez une fiche joueur en cliquant sur le bouton "Enregistrer un personnage".
4. Remplissez les informations du personnage et cliquez sur "Valider".
5. Modifiez les droits d'accès aux commandes si nécessaire.

Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../../introduction/format.mdx).

[^1]: Il est possible d'utiliser un forum, qui créera automatiquement un post pour le personnage. Le joueur (ainsi que les administrateurs) seront mentionnés dans le post.