---
title: Modèle
sidebar_position: 1
---

Pour commencer, vous devez **générer** un nouveau modèle. Utilisez `/register` suivi du nom du modèle. Vous pouvez aussi créer un modèle vide en utilisant `/générer` ou en utilisant le formulaire disponible [ici même](../form.mdx).

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

## Prochaines étapes

Une fois que le modèle est prêt, utilisez `/register [#channel] [fichier] (#user_chan) (#personnage_privé)`. 
- `#channel` est le canal dans lequel le modèle sera envoyée. Il sera ensuite utilisée pour la création de fiche.
- `fichier` est le fichier `JSON` créé précédemment.
- `#user_chan` est le canal dans lequel les fiches seront publiées.[^1]
- `#personnage_privé` est, de manière similaire à `#user_chan`, mais les fiches qui seront publiées dans ce salon seront uniquement visibles par l'utilisateur qui a enregistré la fiche, ou par ceux qui ont accès à ce salon (ainsi que les personnes ayant la permission `GÉRER LES RÔLES`). Si ce salon n'est pas défini, la fonction de fiche privée sera désactivée.
- `?mettre-à-jour` : Permet de mettre à jour toutes les anciennes fiches de personnages si elles existent.
- `?tout_supprimer` : Supprime toutes les anciennes fiches de personnages si elles existent.

    :::warning À propos des fiches privées
    Si la fiche n'est pas marquée comme privée mais est publiée dans un salon auquel les utilisateurs n'ont pas normalement accès, ils pourront tout de même voir la fiche avec les commandes `/afficher` et `/graph`.
    :::

L'embed sera épinglé pour faciliter l'accès.

![embed](/assets/register/embed_template.png)

:::warning Attention
Vous devez réenregistrer le modèle si vous souhaitez modifier le canal par défaut pour les feuilles privées et publiques. Mais l'utilisateur enregistré n'a pas besoin d'être réenregistré, car le canal et l'identifiant du message sont sauvegardés dans la base de données.
Si vous souhaitez déplacer toutes les feuilles vers un autre canal, vous devez utiliser la commande [`/export`](../import_export.md).
:::

## TLDR
1. Créez le modèle avec le [formulaire](../form.mdx) ou la commande `/generate`.
2. Enregistrez le modèle avec `/register`.
3. Créer une fiche joueur en cliquant sur le bouton "Enregistrer un personnage"
4. Remplissez les informations du personnage et cliquez sur "Valider".
5. Modifier les droits d'accès aux commandes si nécessaire.



[^1]: Il est possible d'utiliser un forum, qui créera automatiquement un post pour le personnage. Le joueur (ainsi que les administrateurs) seront mentionnés dans le post.