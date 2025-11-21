---
title: Menu Contextuel
sidebar_position: 3
---

:::tip
Pour ouvrir un menu contextuel, faites un clic droit (ou un appui long sur mobile) sur un message, puis sélectionnez `Application`
:::

# Créer un lien vers un résultat

Cette commande permet de créer un lien direct vers un résultat de dé lancé avec le bot. Utile pour partager un résultat précis dans un autre canal ou avec un autre utilisateur.

Cette commande peut être personnalisée de deux façons :
- Par utilisateur, pour chaque serveur, via la commande `/user_config créer_lien`
- Par serveur, par les administrateurs, via la commande `/config créer_lien`

:::important
Le format du serveur a la priorité sur le format de l'utilisateur.
:::

## Format

:::usage
**`/config créer_lien format [final] [results] [dé] [info] [nom] [jointure_résultats]`**
- `dé` : Le résultat du dé en lui-même, généralement `[RES](SIGN)(COMPARAISON)`, par exemple `[29]>=10`.
- `info` : Le texte d'information qui est le texte de critiques (dont customisés), d'échec ou de réussite.
- `nom` : Le nom de la statistique ou de la macro, si une est trouvée.
- `jointure_résultats` : Le texte à utiliser pour joindre plusieurs résultats ensemble.
- `results` : Une liste qui contient la combinaison de `dé` et `info`, joint par la variable `jointure_résultats`.
- `final` : Le format final qui combine les autres variables pour créer le lien.
:::

:::warning
Discord ne permet pas de rajouter des espaces finaux (ou au début) dans les options. Si vous souhaitez ajouter un espace à la fin ou au début d'une des variables, utilisez `\s` pour représenter un espace.
:::

### Variables

Pour simplifier la création du format, vous pouvez utiliser les variables suivantes dans les champs de format :
- `{{dice}}` : Résultat du dé (exemple : `[29]>=10`)
- `{{info}}` : Texte d'information (exemple : `Échec critique`)
- `{{name}}` : Nom de la statistique (exemple : `Force`) ou de la macro
- `{{results}}` : Liste pouvant combiner plusieurs `{{dice}}` et `{{info}}`
- `{{link}}` : Lien vers le message contenant le résultat du dé.

Il existe certaines personnalisations possibles pour `name` et `info` : 
- `{{name:short}}` : Utilise les initiales de la macro/statistique, si le nom est composée de plusieurs mots (exemple : `CA` pour `Classe d'Armure`)
- `{{name:long}}` : Utilise le nom complet de la macro/statistique (même chose que `{{name}}`)

De même, `info` peut être personnalisé avec :
- `{{info:short}}` : Utilise une version abrégée du texte d'information (exemple : `ÉC` au lieu de `Échec critique`)
- `{{info:long}}` : Utilise la version complète du texte d'information (même chose que `{{info}}`)

#### Résultats (`{{results}}`)
La variable `{{results}}` est en réalité une liste qui est join par la variable `jointure_résultats`. Cette variable **ne peut** être composée que de :
- `{{dice}}`
- `{{info}}`

#### Final
La variable `final` ne peut contenir que les variables `{{results}}`, `{{link}}` et `{{name}}`.

![Schéma des variables](../assets/variable_diagram.png)

### Défaut

Par défaut, le format est défini comme suit :
- Final : `[[{{name}}{{results}}]](<{{link}}>)`,
- Results : ``{{info}} `{{dice}}` ``,
- Jointure_résultats :`; `,
- Dé : `{{dice}}`,
- Info : `{{info}} - `,
- Statistiques : `__{{name}}__: ` ,

Ce qui donne : ``[[__Force__ :  Échec critique - `[29] ⩾ 10`]](<https://discord.com/channels/guildId/channelId/messageId>)``

## Affichage

:::usage
**`/config créer_lien afficher`**
:::

Permet d'afficher la liste des formats de lien actuels pour le serveur, ainsi qu'un exemple basé sur le format suivant :
```
__**Personnage**__ (<@000000000000000000>)  (\`>= 11\`):
[__Nom__]
  **Échec critique** — \`1d100\` ⟶ \`[29]\` = \`[29] ⩾ 10\`
```


## Reset
:::usage
**`/config créer_lien reset`**
:::

Réinitialise le format de lien aux valeurs par défaut.