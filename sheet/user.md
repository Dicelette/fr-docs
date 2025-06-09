---
sidebar_position: 2
title: Enregistrer un utilisateur
---

Maintenant que le modèle est créé, vous pouvez enregistrer des utilisateurs. Comme vu précédemment, l'embed du modèle contient un bouton **"Enregistrer un personnage"**.

Une fois ce bouton activé, vous aurez une série de formulaires à remplir.

:::info
Le nom d'utilisateur est le nom d'utilisateur Discord (pas le nom d'affichage). C'est celui que vous avez peut-être dû changer lorsque Discord a supprimé les numéros après les pseudonymes...
:::

## Formulaire principal

Le premier formulaire est toujours identique, quel que soit le modèle :

- **Nom du personnage** (*obligatoire ou facultatif selon le modèle*)  
- **Nom d'utilisateur** (*obligatoire si modération[^2]*) : ID Discord ou nom d'utilisateur. Pré-rempli avec le nom de la personne qui clique.  
- **Fiche privée** (*optionnel*) : Si l'option est activée (voir [fiche privée](./model/index.md#prochaines-étapes)), permet de choisir si la fiche doit être privée (`x` si oui, vide sinon).  
- **Avatar** (*optionnel*) : Lien vers l'image à utiliser pour la fiche. Si vide, l'avatar du joueur sera utilisé.
- **Salon d'affichage** (*optionnel*) : Permet d'envoyer la fiche dans un salon différent de ceux définis par le modèle (`private_channel` ou `public_channel`). Laisser vide pour utiliser les salons par défaut.

:::warning
La fiche ne peut être masquée **que** si l'option des fiches privées est activée : même si la fiche est envoyée dans un salon inaccessible aux autres, ils pourront l'afficher si cette option n'est pas activée.
:::

![Page_1](/assets/register/register_user_P1.png)

## Formulaire des statistiques

Le ou les formulaires suivants dépendent du modèle :  
- Si plus de cinq caractéristiques sont présentes, plusieurs pages seront affichées.
- À chaque étape, saisissez simplement la valeur de la statistique demandée (contrôles min/max et nombre).

![fin embed](/assets/register/fin_stat.png)

## Dés enregistrés

Une fois l'enregistrement terminé (toutes les statistiques remplies), il est possible d'ajouter des dés spécifiques pour ce personnage.

![modal_dice](/assets/register/add_dice.png)

Chaque dé doit être enregistré manuellement.

![fin](/assets/register/fin_embed.png)

## Validation

Cliquez sur **"Valider"** pour finaliser la fiche.  
La fiche sera alors envoyée dans le salon choisi (ou dans un thread nommé `📝 • [STATS]` si aucun salon n'est défini ou accessible).

## Rappels importants

- [Syntaxe des champs de formulaire et auto-complétion](../introduction/format.md)
- Si l'[auto-enregistrement](../config/self_registration.md) est autorisé et qu'un non-modérateur clique sur le bouton, il ne pourra enregistrer qu'un personnage pour lui-même.

[^1]: Il est possible d'utiliser un forum, qui créera automatiquement un post pour le personnage. Le joueur (ainsi que les administrateurs) seront mentionnés dans le post. 
[^2]: Le champ "nom d'utilisateur" n'est pas présent si l'[auto_enregistrement](../config/self_registration.md) est autorisé et qu'un non-modérateur a cliqué sur le bouton.
