---
title: Auto-enregistrement
sidebar_position: 6
---

## Activer l’auto-enregistrement

:::usage
**`/config auto_enregistrement [?basculer] (?moderation_validation)`**
- `?basculer` : Active/désactive l’option.
- `?moderation_validation` : Seuls les modérateurs peuvent valider la fiche après l’auto-enregistrement par le joueur.
- `?interdire_channel` : L’utilisateur ne peut pas définir de channel (par ID) pour enregistrer son personnage. Si défini sur `true`, la fiche sera envoyée dans le channel par défaut.
:::

Permet aux joueurs ayant accès au modèle d’enregistrer leurs **propres** personnages **publics** (les personnages privés ne peuvent pas être enregistrés par les joueurs).
Les modérateurs pourront toujours enregistrer des personnages pour les autres, les envoyer dans différents channels et enregistrer des personnages privés.

:::tip
Limitez l’accès au modèle à certains rôles pour restreindre l’auto-enregistrement aux joueurs validés.
:::

:::note
Lorsque l’option `moderation_validation` est activée, les modifications de la fiche devront être validées par un modérateur. Si vous ne souhaitez pas permettre aux utilisateurs de modifier leur fiche après l’enregistrement, vous devez restreindre l’accès à la fiche elle-même.
:::

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
