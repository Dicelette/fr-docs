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


Il est aussi possible d'utiliser des commandes slash pour lancer des dés, comme `/roll` ([voir ici pour plus d'information](../usage/index.md)).
