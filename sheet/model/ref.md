---
title: "Références des commandes"
description: "Références des commandes pour la création et l'édition du modèle de fiche de personnage."
---

## Enregistrement du modèle

:::usage
**<mark>`/modèle enregistrer`</mark> `[#channel] [fichier] (#channel_public) (#channel_privé) (?maj_personnages) (?supprimer_personnages)`**
- `#channel` : Canal dans lequel le modèle sera envoyé (utilisé pour la création de fiche).
- `[fichier]` : Fichier JSON créé précédemment.
- `#channel_public` : Canal où seront publiées les fiches.
- `#channel_privé` : Canal pour les fiches privées (voir encadré ci-dessous).
- `?maj_personnages` : Met à jour toutes les anciennes fiches de personnages si elles existent.
- `?supprimer_personnages` : Supprime toutes les anciennes fiches de personnages si elles existent.
:::

![enregistrement](/assets/register/cmd_add_fr.png)

:::danger À propos des fiches privées
Si la fiche n'est pas marquée comme privée, mais est publiée dans un salon auquel les utilisateurs n'ont pas normalement accès, ils pourront tout de même voir la fiche avec les commandes <mark>`/afficher`</mark> et <mark>`/graph`</mark>.
:::

L'embed sera épinglé pour faciliter l'accès.

![embed](/assets/register/embed_template.png)

:::danger
Vous devez réenregistrer le modèle si vous souhaitez modifier le canal par défaut pour les feuilles privées et publiques.  
Mais l'utilisateur enregistré n'a pas besoin d'être réenregistré, car le canal et l'identifiant du message sont sauvegardés dans la base de données.

Pour déplacer toutes les feuilles vers un autre canal, utilisez la commande [<mark>`/export`</mark>](../import_export.md).
:::

## Modification

Pour modifier le modèle, vous pouvez utiliser la commande `/template modifier`.

Cette commande vous permet de télécharger un nouveau fichier JSON, qui remplacera le modèle existant. Contrairement à la commande précédente, elle conserve les différents canaux.

:::usage
**`/template modifier [fichier] (?maj_personnages) (?supprimer_personnages)`**
- `[fichier]` : Fichier JSON
- `?maj_personnages` : Met à jour toutes les anciennes fiches de personnages.
- `?supprimer_personnages` : Supprime toutes les fiches de personnages existantes.
:::

![modifier](/assets/register/modif_template_fr.png)