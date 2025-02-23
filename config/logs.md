---
title: Journalisation
---

## Journalisation des modifications et des erreurs : `/config logs`
:::usage
**`/config logs (#channel)`**
:::

La commande `logs` offre la possibilité de d'enregister un salon afin de : 
- Rapporter toutes les erreurs,
- Enregistrer toute modification apportée à un personnage.

Renvoyer la commande sans l'argument `#channel` permet de supprimer l'envoi des logs.

## Sauvegarde des résultats: `result_channel`

:::usage
**`/config result_channel [?disable_thread] (#channel)`**
:::

Cette commande permet de choisir où le bot enregistre les résultats des jets de dés (les logs). Par défaut, les résultats sont envoyés dans un thread dont le nom commence par `🎲`.

Il existe deux options :
- `disable_thread` : Activez cette option pour envoyer les résultats directement dans le salon indiqué, sans créer de thread. Dans ce cas, l'auto-suppression des messages est désactivée.
- `#channel` : Si vous mentionnez un salon, les résultats seront envoyés dans un thread de ce salon. Cette option est ignorée si `disable_thread` est activé.

Si aucun argument n'est utilisé, le comportement correspond à celui de `/config result_channel true` : les résultats seront envoyés directement dans le salon où le jet a été effectué.

::::example
- <u>Envoyer les résultats dans un channel spécifique</u> : 
    - `/config result_channel #channel`  
    - `/config result_channel false #channel`  

  :::pin Les résultats ne seront pas renvoyés dans le channel configuré si le jet est lancé dans un thread dont le nom commence par `🎲`.
  :::
- <u>Désactiver la création automatique/le salon de résultat</u> :
    - `/config result_channel true`
    - `/config result_channel true #channel`  
    - `/config result_channel` (si une configuration précédente existe)
- <u>Utiliser la création de thread automatique</u> : `/config result_channel false` (les résultats seront envoyés dans un thread dont le nom commence par `🎲`)
::::



## Jets invisibles: `jet_invisible`

:::usage
**`/config jet_invisible [?basculer] (#channel)`**
:::

Cela active l'option `caché` pour les commandes `/gm` et `/roll` et permet de cacher le résultat aux autres joueurs.

Il y a deux configurations possibles :
- Si un salon est mentionné, ce channel sera utilisée pour la sauvegarde du jet, remplaçant le channel `result_channel` (si configuré).
- Si aucun salon n'est utilisé, alors aucune sauvegarde du résultat ne sera faite.

Dans les deux cas, le message sera envoyé comme un message [**éphémère**](https://support.discord.com/hc/fr/articles/1500000580222-Ephemeral-Messages-FAQ), signifiant qu'il n'y aura aucune trace du jet de dés dans le salon où la commande a été effectuée après un certain temps, et que personne d'autre que le lanceur ne verra le résultat.
