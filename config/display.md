---
title: Affichage des résultats
sidebar_position: 4
---

Diverses options permettent de personnaliser l'affichage des résultats des jets de dés, que ce soit dans la sauvegarde ou dans le salon où le jet a été effectué.

## Affichage des timestamps : `timestamp`

:::usage
**`/config timestamp [?basculer]`**
:::

Si l'option est activée (**true**), les timestamps seront affichés dans les messages de résultats des jets de dés.

![](/assets/rolls/config/timestamp.png)

:::tip
Le timestamp s'adapte automatiquement à l'heure du client.
:::

## Délais avant suppression : `supprimer_après`

:::usage
**`/config supprimer_après [temps]`**
- `[temps]` : En secondes
:::

Par défaut, les messages de résultats des jets de dés sont supprimés après **3 minutes** (180s). Cette commande permet de changer le délai (jusqu'à 60 minutes) avant suppression des messages.

Si la valeur est mise à **0**, les messages ne seront plus supprimés.

Cette configuration est désactivée s'il n'y a aucun channel ou thread de sauvegarde.

:::tip
Cette commande permet d'avoir à la fois les logs dans un channel dédié, tout en gardant le résultat indéfiniment dans le salon où le jet a été effectué.
:::

## Contexte et liens
### [Sauvegarde] Lien vers le contexte du dé : `contexte`

:::usage
**`/config contexte [?basculer]`**
:::

Permet d'ajouter un lien vers le contexte du dé dans la sauvegarde du dé.
- Si l'auto-suppression est activée, le lien créé renverra au message précédent le dé.
- Si l'auto-suppression est désactivée, le lien renverra directement au message du dé.

:::warning
Si le message de contexte est supprimé, le lien ne fonctionnera plus.
:::

![Lien vers le contexte](/assets/rolls/config/context.png)

:::tip
Cette option est désactivée s'il n'y a aucun channel ou thread de sauvegarde.
:::

### [Lancé] Lien vers la sauvegarde : `lien_sauvegarde`

:::usage
**`/config lien_sauvegarde [?basculer]`**
:::

Permet d'ajouter un lien vers la sauvegarde du dé dans le message de résultat du dé.

![Lien vers la sauvegarde](/assets/rolls/config/backup_link.png)