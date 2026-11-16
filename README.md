# TD02 – L'objet mystère

On vous a remis un objet connecté, sans documentation. Il communique par radio (6LoWPAN) avec une passerelle, qui le relie à Internet. Votre mission : comprendre ce qu'il fait et en tirer tous ses secrets.

## Objectifs

1. **Vos 4 flags** : l'objet cache 4 flags de la forme `RSR{gN_fK_...}`, où `N` est votre numéro de groupe et `K` le numéro du flag (1 à 4).
2. **Modification du firmware** : faites publier à votre objet, quand on appuie sur le bouton, un message de votre choix.
3. **Flag n°3 d'un autre groupe** : récupérez-le sans toucher au matériel de ce groupe. Il ne compte que si votre compte rendu explique comment vous l'avez obtenu.

## À rendre

Un compte rendu par groupe, envoyé par mail à la fin de la séance. L'IA est autorisée, mais le compte rendu doit montrer que vous avez compris : court et précis vaut mieux que long et creux. Il contient :

1. Le tableau des 5 flags : vos 4 flags et le flag n°3 d'un autre groupe.
2. Votre démarche : pour chaque flag et pour la modification du firmware, expliquez précisément comment vous avez obtenu l'information (par où vous êtes passés, ce que vous avez essayé, ce que vous en avez déduit).
3. Le fonctionnement de l'objet tel que vous l'avez compris : ce qu'il fait, avec qui il communique et comment.
4. Pour chaque faiblesse exploitée, une contre-mesure qui l'aurait empêchée (à proposer, pas à mettre en œuvre). Cette partie compte autant que les flags.

## Pistes

Dans le désordre :

- À qui parle-t-il sur Internet, et sur quels topics ?
- Que se passe-t-il quand on appuie sur le bouton ?
- L'objet ne fait pas que parler : il écoute aussi. Quelles commandes accepte-t-il ?

## Outils et rappels

- Console série : `python -m serial.tools.miniterm`, ou `screen`, au même débit qu'au TD01.
- Sonde : `JLinkExe` (voir le TD01). Un dump n'est fiable que processeur arrêté.
- Analyse : `strings`, `xxd` ou `hexdump`.
- MQTT : `mosquitto-clients` (`mosquitto_sub`, `mosquitto_pub`) ou la bibliothèque Python `paho-mqtt`.
