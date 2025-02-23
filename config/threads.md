---
title: Salons des résultats
description: Désactiver la copie des résultats dans les threads ou envoyer dans un salon spécifique.
sidebar_position: 2
---

Par défaut, le bot copiera les résultats des dés dans un thread nommés `🎲` depuis le salon où le jet a été effectué.

Il est possible de :
- Désactiver la copie totalement,
- Copier les résultats dans un salon précis.

:::info
Si le jet est effectué dans un fil commençant par `🎲`, le résultat ne sera pas copié dans le salon configuré ou un thread automatique.
:::


:::usage
**`/config result_channel [?disable_thread] (#channel)`**
:::

Il existe deux options :
- `disable_thread` : Activez cette option pour envoyer les résultats directement dans le salon indiqué, sans créer de thread. Dans ce cas, l'auto-suppression des messages est désactivée.
- `#channel` : Si vous mentionnez un salon, les résultats seront envoyés dans un thread de ce salon. Cette option est ignorée si `disable_thread` est activé.

Si aucun argument n'est utilisé, le comportement correspond à celui de `/config result_channel true` : les résultats seront envoyés directement dans le salon où le jet a été effectué.

:::example
- <u>Envoyer les résultats dans un channel spécifique</u> : 
    - `/config result_channel #channel`  
    - `/config result_channel false #channel`  

- <u>Désactiver la création automatique/le salon de résultat</u> :
    - `/config result_channel true`
    - `/config result_channel true #channel`  
    - `/config result_channel` (si une configuration précédente existe)

- <u>Utiliser la création de thread automatique</u> : `/config result_channel false` (les résultats seront envoyés dans un thread dont le nom commence par `🎲`)
:::

## Jets invisibles

:::usage
**`/config jet_invisible [?basculer] (#channel)`**
:::

Cela active l'option `caché` pour les commandes `/gm` et `/roll` et permet de cacher le résultat aux autres joueurs.

Il y a deux configurations possibles :
- Si un salon est mentionné, ce channel sera utilisée pour la sauvegarde du jet, remplaçant le channel `result_channel` (si configuré).
- Si aucun salon n'est utilisé, alors aucune sauvegarde du résultat ne sera faite.

Dans les deux cas, le message sera envoyé comme un message [**éphémère**](https://support.discord.com/hc/fr/articles/1500000580222-Ephemeral-Messages-FAQ), signifiant qu'il n'y aura aucune trace du jet de dés dans le salon où la commande a été effectuée après un certain temps, et que personne d'autre que le lanceur ne verra le résultat.

