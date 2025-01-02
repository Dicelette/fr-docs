---
sidebar_position: 2
title: Traduction
---
Le bot est entièrement disponible en français et en anglais. Les commandes slash seront automatiquement traduites dans la langue du client utilisé.

:::tip
Par exemple, un utilisateur dont le client est en français recevra les réponses en français, tandis qu'un utilisateur dont le client est en anglais recevra les réponses en anglais.
:::

Cependant, pour les messages "directs" (c'est-à-dire les messages qui ne sont pas des commandes slash), le bot ne peut pas déterminer quelle langue utiliser. Il utilisera donc la langue du serveur, qui ne peut être sélectionnée que pour les Serveurs Communautaires.

Pour ajouter une nouvelle langue, vous devez copier et traduire le fichier [`en.json`](https://github.com/Dicelette/discord-dicelette/blob/main/src/localizations/locales/en.json).

:::important
Le nom doit suivre le format des [locales discord.js](https://github.com/discordjs/discord-api-types/blob/main/rest/common.ts#L300). Par exemple, `ChineseCN` pour le chinois (Chine) et `ChineseTW` pour le chinois (Taïwan).
:::

Ensuite, vous devez ajouter la langue dans le fichier [`i18next.ts`](https://github.com/Dicelette/discord-dicelette/blob/main/src/localizations/i18next.ts), comme suit :
```ts
import NouvelleTraduction from "./locales/nouvelleTraduction.json";

export const resources = {
	// ...
	discordLocale: { // par ex. fr, en-US, etc.
		translation: NouvelleTraduction,
	},
};
```
