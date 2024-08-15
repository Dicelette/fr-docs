---
sidebar_position: 2
title: Enregistrer un utilisateur
---

Maintenant que le modèle est créé, vous pouvez enregistrer des utilisateurs. Comme nous l'avons vu précédemment, l'embed du modèle contient un bouton "Enregistrer un personnage".

Une fois que le bouton est activé, vous aurez une série de formulaire à remplir.

:::info
Le nom d'utilisateur est le nom d'utilisateur, pas le nom d'affichage. Celui que vous avez peut-être été contraint de changer lorsque Discord a supprimé les numéros après les pseudonymes...
:::

Le premier formulaire sera toujours identique quel que soit le modèle :
- Il vous demandera le nom du personnage (obligatoire ou facultatif, selon les paramètres du modèle)
- Le nom de l'utilisateur, qui doit être soit son ID, soit son nom d'utilisateur. Cette donnée est obligatoire et sera pré-remplie par le bot avec le nom d'utilisateur de la personne qui a cliqué.
- Si vous avez activé l'utilisation des fiches privées (voir [ici](../admin/model/index.md#prochaine-étape)), vous aurez un troisième champ pour choisir si la fiche doit être privée ou non. Si la fiche est privée, mettez simplement `x` dans le champ. Laissez vide sinon !
- Vous pouvez fournir un lien vers une image (un avatar) qui servira comme image dans l'embed de la fiche. Si laissé vide, l'image utilisé sera l'avatar du joueur.
- Enfin, il est possible d'envoyer la fiche de personnage dans un salon différent que ceux définis dans le modèle par `private_channel` et `public_channel`.[^1] Si vous ne voulez pas envoyer la fiche dans un salon spécifique, laissez le champ vide.

	:::warning
	La fiche ne peut être masqué **que** si la fiche est l'utilisation des fiches privées est activé. Même si la fiche est envoyé dans un salon inaccessibles pour les autres utilisateurs, ils seront capables de l'afficher en l'absence de cette option.
	:::


![Page_1](/assets/register/register_user_P1.png)

Le deuxième formulaire dépendra du modèle : s'il y a plus de 5 caractéristiques enregistrées, vous aurez plusieurs pages à remplir. À chaque fois, vous devrez simplement entrer la valeur de la statistique. Ces valeurs seront ensuite vérifiées (min/max et si ce sont bien des nombres). Malheureusement, pour le moment, Discord ne permet pas de vérifier cela directement dans le modal, il faudra donc attendre la fin pour savoir si tout est correct.

![fin embed](/assets/register/fin_stat.png)

Une fois l'enregistrement terminé (c'est-à-dire que toutes les statistiques ont été remplies), les modérateurs ont la possibilité de valider ou d'enregistrer des dés.

![modal_dice](/assets/register/add_dice.png)

Chaque dé doit être enregistré manuellement.

![fin](/assets/register/fin_embed.png)

Une fois tout cela fait, il suffit de cliquer sur "Valider" et la fiche sera repostée dans le salon choisi lors de l'enregistrement (ou dans un thread nommé `📝 • [STATS]` si aucun salon n'a été choisi lors de l'enregistrement du modèle, ou que celui-ci est inaccessible).

[^1]: Il est possible d'utiliser un forum, qui créera automatiquement un post pour le personnage. Le joueur (ainsi que les administrateurs) seront mentionnés dans le post. 