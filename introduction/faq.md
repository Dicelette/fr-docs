---
title: FAQ
sidebar_position: 6
---

## Est-ce que le bot est gratuit ?

Oui, et il le sera toujours. **Aucune** commande ne sera jamais mise derrière un paywall. Déjà, parce que j'ai la flemme, mais ensuite parce que je crois fermement que les outils pour le jeu de rôle doivent rester accessibles à tous.

## Où sont stockées les données ?

Sur mon Raspberry Pi personnel, hébergé chez moi en France. J'utilise une base de données SQLite3 légère pour stocker uniquement les informations essentielles (IDs de messages, liens entre utilisateurs et personnages, configurations de serveur, etc.). Aucune donnée sensible n'est stockée.

Une partie des données sont stockées en cache et donc effacées régulièrement pour optimiser les performances.

## Est-il possible de tricher ?

Non.

Avant la version 2.13.0, le bot utilisait le générateur de nombres pseudo-aléatoire `math.random()`, natif en JavaScript. Cependant, ce générateur n'est pas sécurisé et peut être prévisible dans certaines conditions.

Depuis la version 2.13.0, Dicelette utilise un "[CSPRNG](https://fr.wikipedia.org/wiki/G%C3%A9n%C3%A9rateur_de_nombres_pseudo-al%C3%A9atoires?useskin=vector)" (Cryptographically Secure Pseudo-Random Number Generator) via [node crypto](https://nodejs.org/api/crypto.html). 

**Il n'est donc pas possible de tricher avec le bot.**

:::note
Le bot utilise en interne l'API de [@diceRoller](https://dice-roller.github.io/documentation/) pour la gestion du moteur d'aléatoire, qui lui-même utilise [random-js](https://www.npmjs.com/package/random-js).
Le moteur sélectionné par défaut est `crypto`, qui utilise le CSPRNG de Node.js.
Vous trouverez [ici](https://github.com/Dicelette/core/blob/c12610ea645ee7c1cda219a821b4a8aff5f95de0/src/dice.ts#L160) le code source où le moteur est initialisé.
:::