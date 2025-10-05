# Black_Hole
Création d'une solution qui a pour bute principale de faire perdre un maximum de temps au attaquants voulant scanner nos ports pour trouver les ports et services ouvert et qui tourne sur notre serveur.

- Objectif : accrocher l'attaquant le plus longtemps possible sur nos ports fermés de façon à ce que son analyse prenne un temps monstre et qu'il ne puisse pas différencier un port ouvert d'un port fermé. Envoyer des entêtes de protocoles par les ports dédiés (non utilsé comme le port 22 ) lorsque ces ports sont scannés. Pour les ports génériques, créer une liste d'entête liée à plusieurs protocoles/services et en envoyer un aléatoirement. Faire en sorte que l'envoi se fasse caractère par caractère de façon de plus en plus lente pour ferrer le poisson, mais qu'il passe quand même un temps monstrueux sur chaque port.

