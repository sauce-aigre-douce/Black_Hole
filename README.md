# Black_Hole
Création d'une solution qui a pour bute principale de faire perdre un maximum de temps au attaquants voulant scanner nos ports pour trouver les ports et services ouvert et qui tourne sur notre serveur.

- Objectif : accrocher l'attaquant le plus longtemps possible sur nos ports fermés de façon à ce que son analyse prenne un temps monstre et qu'il ne puisse pas différencier un port ouvert d'un port fermé. Envoyer des entêtes de protocoles par les ports dédiés (non utilsé comme le port 22 ) lorsque ces ports sont scannés. Pour les ports génériques, créer une liste d'entête liée à plusieurs protocoles/services et en envoyer un aléatoirement. Faire en sorte que l'envoi se fasse caractère par caractère de façon de plus en plus lente pour ferrer le poisson, mais qu'il passe quand même un temps monstrueux sur chaque port.

- On a la possibilité de gérer le nombre maximum de communications que l'on garde dans notre Black_Hole simultanément grâce à la constante `MAX_CONNEXIONS`, modifier sa valeur selon la puissance de calcule que vous voulez alouer au script et donc la taille de votre machine.
- On a une gestion du delai d'envoie des caractères des bannières de service. selon le service et le nombre de caractères déjà envoyer la bannière s'envoie plus ou moins vite.
- Dans la fonction `main`on peut gérer les ports sur les quelles ont veut faire tourner le service :
  exemple : 
  ```python
  ports = [22, 21, 25, 80, 110, 995] + list(range(10000, 10010))
  ```
  *cela dit a notre script d'écouter sur les ports 22, 21, 25, 80, 110 et 995 et sur les ports de 10000 à 10010.*

  on uilise la bibliotèque `asyncio` pour que l'OS communique a notre script les tentative de connexion sur les ports non utilisé si ils font partie de notre liste.

  - Le script envoie des logs des connexions en cours. celle qui commence? celle qui se termine et a un compteur du nombre de connexion simultanée.
