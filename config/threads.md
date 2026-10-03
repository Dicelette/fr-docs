---
title: Salons des résultats
description: Désactiver la copie des résultats dans les threads ou envoyer dans un salon spécifique.
sidebar_position: 2
---

Par défaut, le bot copiera les résultats des dés dans un thread nommé `🎲` depuis le salon dans lequel le jet a été effectué.

Il est possible de :
- Désactiver la copie totalement,
- Copier les résultats dans un salon précis.

:::info
Si le jet est effectué dans un fil commençant par `🎲`, le résultat ne sera pas copié dans le salon configuré ou un thread automatique.
:::

## Configurer l’envoi des résultats

:::usage
**`/admin result_channel [?disable_thread] (#channel)`**
- `?disable_thread` : Ne pas créer de thread, envoyer directement dans le salon indiqué.
- `#channel` : Salon cible pour les résultats.
:::

- Si `disable_thread` est activé, les résultats sont envoyés dans le salon sans création de thread (et l’auto-suppression est désactivée).
- Si un salon est mentionné, les résultats seront envoyés dans un thread de ce salon (sauf si `disable_thread` est activé).
- Sans argument, le comportement correspond à `/admin result_channel true`.

:::example
- **Envoyer dans un salon spécifique** : `/admin result_channel #channel`
- **Désactiver la création automatique/le salon résultat** : `/admin result_channel true`
- **Utiliser la création de thread automatique** : `/admin result_channel false`
:::

Si la copie est totalement désactivée, la [suppression automatique](./display.md#délais-avant-suppression) des résultats le sera aussi.

## Jets invisibles

:::usage
**`/admin jet_invisible [?basculer] (#channel)`**
- `?basculer` : Active/désactive l’option.
- `#channel` : (optionnel) Salon où sauvegarder les jets cachés.
:::

Active l’option `caché` pour les commandes `/gm` et `/roll`, et permet de cacher le résultat aux autres joueurs.

- Si un salon est mentionné, il servira pour la sauvegarde du jet invisible.
- Sinon, aucune sauvegarde ne sera faite.

Dans tous les cas, le message sera envoyé en [**éphémère**](https://support.discord.com/hc/fr/articles/1500000580222-Ephemeral-Messages-FAQ) : seule la personne ayant lancé le dé verra le résultat.

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
