---
title: Suppression des messages HRP
description: Configuration de la suppression automatique des messages HRP dans des salons spécifiques.
sidebar_position: 5
---

La commande `/config supprimer_hrp` permet de configurer la suppression automatique des messages hors roleplay (HRP) dans des salons spécifiques.

:::info
Cette fonctionnalité est particulièrement utile pour maintenir l'immersion dans les salons de roleplay en supprimant automatiquement les messages HRP après un délai défini.
:::

## Configuration de base

:::usage
**`/config supprimer_hrp (préfix) (suffixe) (regex) (timer) (#channel) (?thread_mode)`**
- `préfix` : Préfixe des messages HRP à supprimer
- `suffixe` : Suffixe des messages HRP à supprimer
- `regex` : Expression régulière pour les messages HRP à supprimer
- `timer` : Durée en secondes après laquelle les messages HRP seront supprimés
- `channel` : Salon où les messages HRP seront transférés avant suppression
- `thread_mode` : Si `true`, les messages seront transférés dans un thread
:::

### Paramètres de détection

Vous pouvez utiliser trois méthodes pour identifier les messages HRP :

1. **Préfixe et suffixe** : Messages encadrés par des caractères spécifiques
2. **Expression régulière** : Pour des patterns plus complexes (utilisateurs avancés)

:::warning
Les expressions régulières peuvent être complexes et entraîner des suppressions non souhaitées. Préférez les champs `préfix` et `suffixe` si vous n'êtes pas familier avec les regex.
:::

### Options de transfert

- **Sans salon spécifié** : Les messages seront supprimés directement
- **Avec salon (`#channel`)** : Les messages seront transférés dans le salon avant suppression
- **Mode thread (`thread_mode: true`)** : Les messages seront transférés dans un thread (similaire aux [threads de résultats](./threads.md))

## Exemples d'utilisation

:::example
**Suppression avec préfixe/suffixe :**
```
/config supprimer_hrp prefix:- suffix:- timer:180 channel:#hrp
```
Supprime les messages HRP encadrés par `-` (ex : `-message hrp-`) et les transfère dans `#hrp` après 3 minutes.

**Suppression avec regex :**
```
/config supprimer_hrp regex:\(hrp::(.*)\) timer:60
```
Supprime les messages du type `(hrp:: message)` après une minute.

**Suppression directe :**
```
/config supprimer_hrp prefix:((( suffix:))) timer:120
```
Supprime les messages encadrés par `(((` et `)))` après 2 minutes sans sauvegarde.
:::

## Sélection des salons

Lors de l'utilisation de la commande, une interface de sélection apparaîtra pour choisir les salons, catégories, forum, voire thread où la suppression des messages HRP sera active.

:::tip Limites
- **Minimum** : 1 salon doit être sélectionné pour activer la fonctionnalité
- **Maximum** : 25 salons/threads/catégories peuvent être sélectionnés
:::

## Désactivation

Pour désactiver la suppression des messages HRP :

:::usage
**`/config supprimer_hrp`** (sans paramètres)  
**`/config supprimer_hrp timer:0`**
:::

Les deux méthodes permettent de désactiver complètement la fonctionnalité.

## Intégration avec d'autres fonctionnalités

Cette fonctionnalité peut être utilisée conjointement avec :
- [Salons des résultats](./threads.md) pour organiser les messages des jets de dé
- [Affichage des résultats](./display.md) pour la gestion des délais de suppression des jets de dés

<small>Pour plus d'informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
