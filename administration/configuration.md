---
title: Configuration
---

## Journalisation
### Administration: `logs`

:::usage
**`/config logs (#channel)`**
:::

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

### Affichage des timestamp: `config_timestamp`

:::usage
**`/config config_timestamp [true/false]`**
:::

Si l'option est sur **true**, affiche les timestamps dans les messages de résultats des jets de dés.
