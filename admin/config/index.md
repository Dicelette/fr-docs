---
title: Configuration générale
sidebar_position: 2
---
Toutes les commandes d'administration sont restreintes par défaut aux membres ayant la permission `Gérer les rôles`.

La commande `/config afficher` pour voir la configuration actuelle du serveur.

Les commandes suivantes fonctionnent à la fois pour les dés lancés en texte seul et pour les dés lancés avec des slashcommands (que ce soit `/roll` que `/dbd` et `/dbroll`).
Sauf mention contraire, toutes les options sont, par défaut, désactivées.

## Format

- Les champs obligatoires sont indiqués entre crochets : `[champs]`.
- Les champs facultatifs sont entre parenthèses : `(champs)`.
- Les champs auto-complétés seront marqués d'un `*` : `(*champs)`.
- Les champs demandant une mention seront marqués par `@` (`@champs`). Ces champs fonctionnent avec les noms (rôle ou utilisateur, en fonction de la commande) ou l'ID Discord. Si la mention ne s'affiche pas immédiatement, commencez à taper le début du nom pour l'auto-complétion.
- De manière similaire, les commandes demandant un channel sont précédé par `#` comme `#champs`.

## Journalisation
### Administration: `logs`

##
La commande `logs` offre la possibilité de d'enregister un channel afin de : 
- Rapporter toutes les erreurs,
- Enregistrer toute modification apportée à un personnage.

Renvoyer la commande sans l'argument `#channel` permet de supprimer l'envoi des logs.

### Sauvegarde des résultats: `result_channel`

:::usage
**`/config result_channel (#channel)`**
:::

La commande `/config result_channel` permet de définir un canal pour recevoir les résultats des jets de dés, plutôt que d'utiliser un fil de discussion à chaque fois. L'ID du canal sera alors enregistré dans la base de données de la même manière que la commande `logs`.

Renvoyer la commande sans l'argument "channel" permet de supprimer le canal de résultats à l'instar de la commande `logs`.

### Désactiver l'auto-création des threads: `désactiver_threads`

:::usage
**`/config désactiver_threads [true/false]`**
:::


Si l'option est sur **true**, désactive la création, par défaut, des threads pour les jets de dés. Tout sera donc envoyé (sans suppression) dans le channel où la commande a été effectuée.

:::warning
Cette option prend le pas sur la commande `/config result_channel`. C'est à dire que dans le cas où elle est activée, les résultats des jets de dés ne seront pas envoyés dans le channel configuré par la commande `/config result_channel` si ce dernier est configuré.
:::

Les channels et fils préfixés par `🎲` ne recevront plus les logs non plus.


L'option sur **faux** réactive le comportement normal du bot.

## Affichages des résultats

Diverses options permettent de personnaliser l'affichage des résultats des jets de dés, que ce soit dans la partie sauvegarde que dans le channel où le jet a été effectué.

### Affichage des timestamp: `timestamp`

:::usage
**`/config timestamp [true/false]`**
:::

Si l'option est sur **true**, affiche les timestamps dans les messages de résultats des jets de dés.

![](/assets/rolls/config/timestamp.png)

:::tip
Le timestamp s'adapte automatiquement à l'heure du client.
:::

### Délais avant suppression: `supprimer_après`

:::usage
**`/config supprimer_après [temps]`**
- `[temps]` : En seconde
:::

Par défaut, les messages de résultats des jets de dés sont supprimés après **3** minutes (180s). Cette commande permet de changer le délais (jusqu'à 60 minutes) avant suppression des messages.

Si la valeur est mise à **0**, les messages ne seront plus supprimés.

Cette configuration est désactivée si `/config désactiver_threads` est activée.

:::tip
Cette commande permet d'avoir à la fois les logs dans un channels dédiés, tout en gardant le résultat indéfiniment dans le channel où le jet a été effectué.
:::

### [Sauvegarde] Lien vers le contexte du dé : `contexte`

:::usage
**`/config contexte [true/false]`**
:::

Permet d'ajouter un lien vers le contexte du dé dans la sauvegarde du dé.
- Si l'auto-suppression est activé, le lien créé renverra au message précédent le dé.
- Si l'auto-suppression est désactivé, le lien renverra au message du dé directement.

:::warning
Si le message du contexte est supprimé, le lien ne fonctionnera plus.
:::

![Lien vers le contexte](/assets/rolls/config/context.png)

### [Lancé] Lien vers la sauvegarde `lien_sauvegarde`

:::usage
**`/config lien_sauvegarde [true/false]`**
:::

Permet d'ajouter un lien vers la sauvegarde du dé dans le message de résultat du dé.

![Lien vers la sauvegarde](/assets/rolls/config/backup_link.png)

