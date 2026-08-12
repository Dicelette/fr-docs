# Envoi de Message

Ce bot détecte la notation des dés et envoie le résultat selon trois méthodes :

1. **Notation Directe** :
   - Exemple : `1d20`
   - Le message "commande" sera supprimé et le résultat sera envoyé dans le même canal (et dans le log).
   ![Direct](/assets/rolls/direct.gif)

2. **Notation Indirecte** :
   - Exemple : `mon contenu de message [1d20]`
   - Le message sera conservé et seul le contenu des crochets sera lancé. Vous recevrez une réponse avec le résultat, et le log sera envoyé dans le fil, incluant un lien vers le message d'origine.
   ![Indirecte](/assets/rolls/indirect.gif)

3. **Notation Semi-Directe** :
   - Exemple : `1d20 Mon message`
   - Le dé trouvé initialement sera lancé, et le reste du message sera envoyé dans le log, considéré comme un commentaire.
   ![Semi-directe](/assets/rolls/semi-direct.gif)


Vous pouvez aussi utiliser des commandes slash pour lancer des dés, comme `/roll` ([voir ici pour plus d'information](../usage/index.md)).

:::tip
Il est possible de mentionner :
- Une statistique, via `$statistique` (ex. `$force`) à condition que l'utilisateur ait enregistrée une fiche ou des attributs.[^1]
- Un personnage, via `@personnage` (ex. `@Bob`).
- Une opposition, en "superposant" les signes : `1d100>20>10` (le dernier élément sera considéré comme l'opposition).
:::

Enfin, vous pouvez modifier les commentaires d'un jet de dés en répondant au message du résultat avec un commentaire préfixé par `///` (ex. `/// Mon commentaire`). Seuls vos propres commentaires peuvent être modifiés. Cette modification est possible sur tous les résultats de dés lancés par le bot, que ce soit via une commande slash ou via un message.

[^1]: Pour utiliser la valeur d'une statistique comme nombre de dés, il faut utiliser `($stat)dX` (ex. `($force)d20`).

<small>Pour plus d’informations sur la syntaxe des champs : [consultez la page dédiée](../introduction/format.mdx).</small>
