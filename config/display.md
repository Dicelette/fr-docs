---
title: Affichage des résultats
---
Diverses options permettent de personnaliser l'affichage des résultats des jets de dés, que ce soit dans la partie sauvegarde que dans le salon où le jet a été effectué.

## Affichage des timestamp: `timestamp`

:::usage
**`/config timestamp [?basculer]`**
:::

Si l'option est sur **true**, affiche les timestamps dans les messages de résultats des jets de dés.

![](/assets/rolls/config/timestamp.png)

:::tip
Le timestamp s'adapte automatiquement à l'heure du client.
:::

## Délais avant suppression: `supprimer_après`

:::usage
**`/config supprimer_après [temps]`**
- `[temps]` : En seconde
:::

Par défaut, les messages de résultats des jets de dés sont supprimés après **3** minutes (180s). Cette commande permet de changer le délais (jusqu'à 60 minutes) avant suppression des messages.

Si la valeur est mise à **0**, les messages ne seront plus supprimés.

Cette configuration est désactivée si `/config désactiver_threads` est activée.

:::tip
Cette commande permet d'avoir à la fois les logs dans un channels dédiés, tout en gardant le résultat indéfiniment dans le salon où le jet a été effectué.
:::

## Context et liens
### [Sauvegarde] Lien vers le contexte du dé : `contexte`

:::usage
**`/config contexte [?basculer]`**
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
**`/config lien_sauvegarde [?basculer]`**
:::

Permet d'ajouter un lien vers la sauvegarde du dé dans le message de résultat du dé.

![Lien vers la sauvegarde](/assets/rolls/config/backup_link.png)