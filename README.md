# TD02 – L'objet mystère

On vous a remis un objet connecté, sans documentation. Il communique par radio (6LoWPAN) avec une passerelle, qui le relie à Internet. Votre mission : comprendre ce qu'il fait et en tirer tous ses secrets.

## Objectifs

1. **Vos 4 flags** : l'objet cache 4 flags de la forme `RSR{gN_fK_...}`, où `N` est votre numéro de groupe et `K` le numéro du flag (1 à 4).
2. **Modification du firmware** : faites publier à votre objet un autre message.
3. **Flag n°3 d'un autre groupe** : récupérez-le sans toucher au matériel de ce groupe. Il ne compte que si votre compte rendu explique comment vous l'avez obtenu.

## À rendre

Un compte rendu par groupe, envoyé par mail à la fin de la séance. Il contient :

1. Le tableau de 5 flags : vos 4 flags et le flag f3 d'un autre groupe, avec pour chacun où et comment vous l'avez obtenu.
2. La méthodologie : les étapes suivies pour les flags et la modification du firmware, avec les commandes utilisées et leur sortie utile.
3. Pour chaque faiblesse exploitée, la protection qui l'aurait empêchée. Cette partie compte autant que les flags.

## Pistes

Dans le désordre :

- Que raconte l'objet quand il démarre ?
- Que contient sa mémoire ? Récupérez le firmware avec la sonde de programmation.
- À qui parle-t-il sur Internet, et sur quels topics ?
- Que se passe-t-il quand on appuie sur le bouton ?
- L'objet ne fait pas que parler : il écoute aussi. Quelles commandes accepte-t-il ?

## Outils et rappels

- Console série : `python -m serial.tools.miniterm`, ou `screen`, au même débit qu'au TD01.
- Sonde : `JLinkExe` (voir le TD01). Un dump n'est fiable que processeur arrêté.
- Analyse : `strings`, `xxd` ou `hexdump`, Ghidra si vous voulez aller plus loin.
- MQTT : `mosquitto-clients` (`mosquitto_sub`, `mosquitto_pub`) ou la bibliothèque Python `paho-mqtt`.
