---
title: Journalisation des résultats
---

## Journalisation des modifications et des erreurs : `/config logs`
La commande `logs` offre la possibilité de d'enregister un salon afin de : 
- Rapporter toutes les erreurs,
- Enregistrer toute modification apportée à un personnage.

Renvoyer la commande sans l'argument `#channel` permet de supprimer l'envoi des logs.

## Sauvegarde des résultats: `result_channel`

:::usage
**`/config result_channel (#channel)`**
:::

La commande `/config result_channel` permet de définir un canal pour recevoir les résultats des jets de dés, plutôt que d'utiliser un fil de discussion à chaque fois. L'ID du canal sera alors enregistré dans la base de données de la même manière que la commande `logs`.

Renvoyer la commande sans l'argument "salon" permet de supprimer le canal de résultats à l'instar de la commande `logs`.

## Désactiver l'auto-création des threads: `désactiver_threads`

:::usage
**`/config désactiver_threads [?basculer]`**
:::
Si l'option est sur **true**, désactive la création, par défaut, des threads pour les jets de dés. Tout sera donc envoyé (sans suppression) dans le salon où la commande a été effectuée.

:::warning
Cette option prend le pas sur la commande `/config result_channel`. C'est à dire que dans le cas où elle est activée, les résultats des jets de dés ne seront pas envoyés dans le salon configuré par la commande `/config result_channel` si ce dernier est configuré.
:::

Les channels et fils préfixés par `🎲` ne recevront plus les logs non plus.

L'option sur **faux** réactive le comportement normal du bot.

## Jets invisibles: `jet_invisible`

:::usage
**`/config jet_invisible [?basculer] (#channel)`**
:::

Cela active l'option `caché` pour les commandes `/gm` et `/roll` et permet de cacher le résultat aux autres joueurs.

Il y a deux configurations possibles :
- Si un salon est mentionné, ce channel sera utilisée pour la sauvegarde du jet, remplaçant le channel `result_channel` (si configuré).
- Si aucun salon n'est utilisé, alors aucune sauvegarde du résultat ne sera faite.

Dans les deux cas, le message sera envoyé comme un message [**éphémère**](https://support.discord.com/hc/fr/articles/1500000580222-Ephemeral-Messages-FAQ), signifiant qu'il n'y aura aucune trace du jet de dés dans le salon où la commande a été effectuée après un certain temps, et que personne d'autre que le lanceur ne verra le résultat.
