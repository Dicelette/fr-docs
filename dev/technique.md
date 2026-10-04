---
title: Fonctionnement technique
sidebar_position: 3
---

Cette page décrit comment Dicelette fonctionne en interne et comment vos données sont gérées. Pour la liste complète des données enregistrées, voir les [CGU](./TOS/index.md) et la [politique de confidentialité](./TOS/policy.md).

## Architecture technique

Le bot utilise l'API [@diceRoller](https://dice-roller.github.io/documentation/) pour tous les calculs de dés, garantissant des résultats fiables et une grande variété d'expressions supportées. Les différences entre la syntaxe de Dice Roller et celle de Dicelette sont détaillées dans la page [Notations des dés](../introduction/expression.mdx).

Le générateur de nombres aléatoires utilisé est décrit dans la [FAQ](../introduction/faq.md).

## Approche respectueuse des données

Contrairement à d'autres solutions, ce bot privilégie votre contrôle sur vos données :
- **Stockage minimal** : Seuls les identifiants des messages et informations essentielles sont sauvegardés
- **Contrôle total** : Vos fiches de personnage restent dans vos messages Discord
- **Nettoyage automatique** : Les données obsolètes sont supprimées automatiquement

Cette approche vous garantit une sécurité maximale et un contrôle total sur vos informations de jeu.

## Gestion des données

### Ce qui est stocké

Le bot utilise une base de données SQLite3[^1] pour conserver uniquement :
- Les identifiants des messages contenant vos fiches
- Les liens entre utilisateurs et leurs personnages
- Les paramètres de configuration du serveur
- Les modèles de statistiques personnalisés

### Nettoyage automatique

Les données sont automatiquement supprimées dans plusieurs cas :
- Suppression des messages ou canaux enregistrés
- Expulsion du bot du serveur
- Utilisation des fonctionnalités de nettoyage intégrées

### Respect de la vie privée

:::note Contact pour suppression
Si vous souhaitez supprimer vos données après avoir quitté un serveur, contactez-nous via Discord (`@mara__li`) ou par e-mail (`lisandra_dev@yahoo.com`) avec votre identifiant Discord ou l'ID du serveur.
:::

:::warning Nettoyage manuel
En cas de problème avec la suppression automatique, utilisez les commandes de suppression manuelle disponibles dans le bot pour nettoyer vos données.
:::

[^1]: Base de données locale utilisant [Enmap](https://enmap.evie.dev/) pour une gestion optimisée.
