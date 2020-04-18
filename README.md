# Jouer sur Jamulus

## Téléchargement et installation

* Pour Windows : https://sourceforge.net/projects/llcon/files/Jamulus/3.5.0/Jamulus-3.5.0-installer.exe/download
* Pour Mac : https://sourceforge.net/projects/llcon/files/Jamulus/3.5.0/Jamulus-3.5.0-mac.zip/download

Il suffit normalement de lancer le fichier pour installer le soft.

## Lancement et serveurs

Lorsqu'on clique sur "Connect", la liste des serveurs disponibles est affichée, avec une valeur importante qui est le "ping". Cette valeur corresponds au temps réseau nécessaire pour faire un aller-retour avec le serveur, et est très critique car cela va être un élément déterminant pour la latence constatée pendant le jeu. Plus cette valeur est faible, mieux c'est.

J'ai monté le serveur "PetitesEcuries", hébergé à paris (dans les datacentres d'Iliad, a.k.a Free) qui normalement a une bonne latence pour les parisiens et par extensions les gens qui sont topologiquement pas trop loin (on peut avoir des surprises, la topologie d'internet est parfois très éloignée de la géographie).

Tous les serveurs visibles sont "ouverts", c'est à dire que n'importe qui peut s'y connecter et venir jouer, n'importe quand. Il est important d'essayer au maximum de respecter à la fois les règles de chaques serveurs (des fois thématiques par exemple) et les musiciens présents. Ce n'est pas toujours le cas en pratique, mais pour que ça se passe bien danns un monde aussi permissif, il en va des bonnes manières de chacun.

## Gestion de la latence

Mes tests me donnent les chiffres suivants :

* Si la latence est de 50ms ou plus, c'est injouable.
* Une latence entre 40 et 50 se sent et c'est dur.
* Une latence entre 30 et 40 se sent mais c'est jouable.
* Une latence entre 20 et 30 ça devient sympa.
* En dessous de 20, c'est top, mais pas super simple à obtenir.

La latence totale provient de la somme de plusieurs éléments :

* Le temps d'entrée et d'encodage du son, qui est dépendant du matériel du musicien. Une carte son "professionelle" est à privilégier à ce niveau bien que certains matériels intégrés aient maintenant de bons résultats.
* Le temps de trajet du réseau, qu'on peut mesurer avec la valeur de "ping". Pour améliorer cette valeur, il faut une bonne connection (fibre ...), éviter le WiFi (un cable réseau branché sur la box, ça va beaucoup plus vite, j'ai gagné 10ms comme ça).
* Le temps de processing du serveur (négligeable et pas améliorable).
* Le temps de buffer, réglable dans les paramètres ("Jitter Delay" qu'on va laisser à 64 (ou 128 si le son craque) si possible et "Jitter Buffer" réglé automatiquement par défaut). Si le buffer est trop faible par rapport à la qualité et à la stabilité de la conection, la conséquence sera une dégradation assez horrible du son.
* Le temps de décodage et de restitution du son, dépendant comme pour le premier point du matériel du musicien.

Il faut jouer sur tous les paramètres sous notre contrôle pour faire baisser au maximum cette latence, l'utilisabilité du système en dépends directement (cela va d'une expérience comfortable de jeu à quelque chose d'assez horrible où on a l'impression que tout le monde ralentit en permanence, ayant pour conséquence de perdre 30 BPM par minute si chacun ne "pousse" pas le tempo comme un dingue).

## Paramètres

Les paramètres disponibles sont assez limités mais les voici :

- Device : le matériel son utilisé, si possible une carte son externe à sélectionner ici
- Input Channel Mapping : les canaux d'entrée à utiliser, si possible un line-in de la carte son, l'utilisation de microphones est déconseillée et en tout cas si on utilise un micro, il _faut_ jouer au casque pour éviter un feedback (écho) du retour dans le micro.
- Output Channel Mapping : les canaux de sortie à utiliser, si l'entrée est une entrée ligne ou instru on peut utiliser des enceintes, si l'entrée est un micro il _faut_ utiliser un casque et couper les enceintes.
- Buffer Delay : combien de "ticks" on garde en mémoire avant de les jouer pour s'assurer de ne pas avoir de "trou" dans le son. Impact direct sur la latence, il est largement conseillé de garder bas (64 le minimum ou 128 si le son craque).
- Jitter Buffer : un autre type de buffer, il est conseillé dans un premier temps de le laisser en automatique, et éventuellement si le temps et l'envie sont là essayer dans un second temps de baisser progressivement ces valeurs à la main (mais pas forément nécessaire et cela peut avoir un impact sur la qualité du son).

## Gotchas

- Il faut jouer avec le feedback qui provient de Jamulus, et ne pas utiliser le "monitoring" local ou le son de l'ampli en direct, pour jouer "avec" la latence.
