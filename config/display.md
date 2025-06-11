---
title: Affichage des résultats
sidebar_position: 4
---

Diverses options permettent de personnaliser l’affichage des résultats des jets de dés, que ce soit pour la sauvegarde ou dans le salon dans lequel le jet a été effectué.

## Affichage des timestamps

:::usage
**`/config timestamp [?basculer]`**
- `?basculer` : Active/désactive l’affichage du timestamp.
:::

Si activé (**true**), un timestamp sera affiché dans les messages de résultats des jets.

![](/assets/rolls/config/timestamp.png)

:::tip
Le timestamp s’adapte à l’heure du client.
:::

## Délais avant suppression

:::usage
**`/config supprimer_après [temps]`**
- `[temps]` : Durée en secondes (0 = jamais supprimé).
:::

Définit le délai avant suppression automatique des messages de résultats (de 0 à 3600s, défaut : 180 s).

Cette configuration est désactivée s’il n’y a aucun channel ou thread de sauvegarde.

:::tip
Permet d’avoir à la fois un log dédié et de garder le résultat indéfiniment dans le salon d’origine si besoin.
:::

## Liens contextuels

### Lien vers le contexte du dé

:::usage
**`/config contexte [?basculer]`**
- `?basculer` : Active/désactive le lien vers le contexte.
:::

Ajoute un lien vers le contexte du dé dans la sauvegarde du dé.

- Si l’auto-suppression est activée, le lien renverra au message précédent.
- Sinon, il renverra au message du dé.

:::warning
Si le message de contexte est supprimé, le lien ne fonctionnera plus.
:::

![Lien vers le contexte](/assets/rolls/config/context.png)

:::tip
L'option est désactivée s'il n'y a ni channel ni thread de sauvegarde pour le résultat.
:::

### Lien vers la sauvegarde du dé

:::usage
**`/config lien_sauvegarde [?basculer]`**
- `?basculer` : Active/désactive le lien vers la sauvegarde.
:::

Ajoute un lien vers la sauvegarde du dé dans le message de résultat.

![Lien vers la sauvegarde](/assets/rolls/config/backup_link.png)

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
