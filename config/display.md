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

## Ordre de tri

:::usage
**`/config ordre_tri (?ordre)`**
- `?ordre` : Ordre choisi pour l'affichage des résultats. À choisir entre :
  - <u>Croissant</u>
  - <u>Décroissant</u>
  - <u>Aucun</u> (*Désactivé*)
:::

Par défaut, les sorties des dés (tel que `4d6`) ne sont pas trié. Il est possible de les afficher trié lors du lancé avec [la syntaxe prévue à cet effet (`s`, `sa`, `sd` en fin de dé)](https://dice-roller.github.io/documentation/guide/notation/modifiers.html#sorting).
Cette option de configuration permet de trier par défaut les sorties sans avoir à manuellement mettre la notation.

:::tip
Si le symbole de tri est ajouté au dé, alors il aura priorité sur la configuration.
:::

## Désactiver la comparaison

:::usage
**/config désactiver_comparaison (?basculer)**
- `?basculer` : Sur `True` désactivera les messages de succès ou d'échec.
:::

Cela permet de simplifier la syntaxe d'entrée pour obtenir directement le nombre de succès ou échec (*target failure/success*) au lieu du message d'information, en évitant d'avoir à placer les dés entre accolade. 


:::warning["Cette syntaxe désactive la comparaison aux jets d'opposition"]
:::


[Veuillez vous référez à cette page pour plus d'information sur les comparaisons](../introduction/expression.mdx#les-comparateurs)

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>