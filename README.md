

Les prémices du projet
======================

En 2014 ...

## 1) Envie de jouer avec de l'IA

Un jour j'ai eu envie de programmer de l'intelligence articifielle (IA).
J'ai lu des articles, étudier le fonctionnement de différent algorithme de recherche/choix/...
On se rend rapidement compte que ca peux être tres vite compliqué et pas super marrant.

Je voulais un environnement de jeu assez simple faire créer, partager, et faire s'affronter des petits programmes "intelligent".
J'avais imaginer créer un monde autonome ou une forme d'intelligence evoluerait et ca nous informerait juste de l'evolution sur notre salon IRC.
Peut-etre avec un serveur web pour avoir une représentation visuelle de quelque chose ? rien de bien folichon.
J'ai fini par mettre ca de coté.




## 2) Contrainte: de simplicité technique

Si la programmation de la partie "intelligente" d'un programme va etre compliqué, j'aurais voulu de pas perdre du temps et des cheveux pour programmer l'environnement dans lequel tout ca evoluera!
Il faut donc trouver un univers de jeu simple a gerer (coté serveur) et simple a représenter (coté client).

On oublie donc les voyage spaciaux en 3D (cf. EVE online)
Revenons sur un espace en 2D !
Mais meme la, c'est pas evident.
Par exemple on imagine le cerveau artificiel d'une unité ... l'une des premieres informations qu'il lui faudra est "dit moi ce qui m'entourne"
et dans un univers ou on gere des coordonnees 2D il faut calculer les distances tous les objets autour d'un point de départ (les coordonnees de l'unité).
Ca n'a rien de très difficile mais si on fait ca pour des milliers d'unité évoluant dans un univers vaste... on est vite confronté a des difficultés, qui s'avere etre purement induite par ce choix de coordonnées 2D.

## 3) reduire au minimum

Si l'information qu'une intelligence a besoin est donne moi les objets qui sont proche de moi avec leur distance respective...
arrangeons nous pour que l'univers est une forme proche de celle-ci.

Si la 3D est trop compliquée a représenter, réduisons a la 2D.
Si la 2D est encore un peu trop compliquée réduison a la 1D.

## 4) un univers en 1D

Voila je créé mon univers en 1D une ligne avec des coordonnees entiere (0, 1, 2, ...)

## 5) pour la perfection

La perfection est dans le cercle. Aller soyons fou arrangeons nous pour relier la fin de l'univers (a droite) a son commencement (a gauche).
On obtient un univers en forme de cercle!
Je le batise cercle univers... le cercl'univers !




Envie d'originalité
===================

A certain moment de ma vie j'ai essayé d'imaginer des jeux tres originaux...

## La problématique de l'hyper-vitesse

Dans un jeu spacial, il est de coutume de pouvoir faire parcourir des vaisseaux sur de tres grandes distances, car sinon les joueurs seraient mort avant d'atteindre la 1ere planete.
Grace a la science fiction (battle star galactica, stargate, ...) il devient classique d'avoir de l'hyper-vitesse ... qui téléporte virtuellement un vaisseau d'un bout a un autre de la galaxie.

ce qui me dérangeait c'est ce qui se passe pendant ce déplacement.
Par exemple le vaisseau peut-il est suivis par un enemis ? peut-il est détruit ? ou est-il pendant ce déplacement ?
J'ai donc proposé de créer un 2eme univers pour y placer les vaisseaux en déplacement...


tel qu'un jeu ou on voyagerai en hyper espace ... ou on traverserais un trou de verre et on evoluerait dans un univers parallèle !
ou bien on voyagerait dans le temps !
J'ai peur de rien !
Mais j'ai du mal a trouvé un gameplay adapté, interressant...



Envie de jouer avec l'espace (multi dimension) et le temps
mais ca devient rapidement soit inutilement compliqué, soit ininterressant pour un jeu, soit effrayant pour la majorité des gens ...


Evenement : Edge of tomorrow

le principe "die and retry" m'a reveillé l'envie de faire un jeu ou on puisse partager et forker nimporte quel moment du jeu et pouvoir comparer tous ces forks ...


Le fun pour la machine


Le fun pour le dev

Le fun pour le joueur

casual ?
hardcore gamer ?

