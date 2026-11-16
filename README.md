# TD02 – L'objet mystère

On vous a remis un objet connecté, sans documentation. Il communique par radio (6LoWPAN) avec une passerelle, qui le relie à Internet. Votre mission : comprendre ce qu'il fait et en tirer tous ses secrets.

Matériel par groupe : l'objet (carte Zest Core STM32L4A6RG déjà programmée, avec un bouton et une LED), une sonde J-Link et un câble USB-série.

## Objectif : 4 flags

L'objet cache 4 flags de la forme `RSR{gN_fK_...}`, où `N` est votre numéro de groupe et `K` le numéro du flag (1 à 4). Chaque groupe a ses propres flags. Un flag d'un autre groupe ne compte que pour le bonus B1, et seulement si votre compte rendu explique comment vous l'avez obtenu.

Pistes, dans le désordre :

- Que raconte l'objet quand il démarre ?
- Que contient sa mémoire ? Récupérez le firmware avec la sonde de programmation.
- À qui parle-t-il sur Internet, et sur quels topics ?
- Que se passe-t-il quand on appuie sur le bouton ?
- L'objet ne fait pas que parler : il écoute aussi. Quelles commandes accepte-t-il ?

## Bonus

- **B1 – Chez les voisins** : récupérez un flag d'un autre groupe sans toucher à son matériel, et expliquez votre méthode.
- **B2 – La clé du réseau radio** : retrouvez la clé qui protège le réseau 6LoWPAN. Que peut faire quelqu'un qui la connaît ?
- **B3 – Sans la carte** : retrouvez vos flags masqués à partir du seul firmware, sans faire fonctionner l'objet.
- **B4 – Prise de contrôle** : faites publier à votre objet un autre message que le sien.

## Règles du jeu

- Votre objet est à vous : tout est permis dessus.
- Les objets des autres groupes ne se touchent qu'à distance, sans les empêcher de fonctionner.
- Interdit : faire redémarrer ou bloquer l'objet d'un autre groupe, publier des messages retenus (`retain`), vous connecter avec l'identifiant d'un objet, inonder le serveur, viser autre chose que les objets du TD.
- Le serveur utilisé est un service public. En dehors de ce cadre, s'introduire dans un système ou l'entraver est un délit (articles 323-1 et 323-2 du Code pénal).

## À rendre

Un compte rendu par groupe, envoyé par mail à la fin de la séance. Il contient :

1. Le tableau de vos flags (et bonus), avec pour chacun où et comment vous l'avez trouvé.
2. Les étapes suivies, avec les commandes utilisées et leur sortie utile.
3. Pour chaque faiblesse exploitée, la protection qui l'aurait empêchée. Cette partie compte autant que les flags.

## Outils et rappels

- Console série : `python -m serial.tools.miniterm`, ou `screen`, au même débit qu'au TD01.
- Sonde : `JLinkExe` (voir le TD01). Un dump n'est fiable que processeur arrêté.
- Analyse : `strings`, `xxd` ou `hexdump`, Ghidra si vous voulez aller plus loin.
- MQTT : `mosquitto-clients` (`mosquitto_sub`, `mosquitto_pub`) ou la bibliothèque Python `paho-mqtt`.
