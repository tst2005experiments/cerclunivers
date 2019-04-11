
# Les prémices du projet

En 2014 ...


## 1) Envie de jouer avec de l'Intelligence Artificielle

Un jour j'ai eu envie de programmer de l'intelligence articifielle (IA).

Soyons clair dès le début je parle d'une "intelligence" toute relative.

J'ai lu des articles, étudier le fonctionnement de différent algorithme de "pathfinding".
On se rend rapidement compte que ca peut être très vite compliqué et pas super marrant.

Ce qui m'interesse est la partie programmation de comportement (pseudo) intelligent.

Je voulais un environnement de jeu assez simple pour créer, partager et faire s'affronter des petits programmes "intelligent".

### une idée en passant

J'avais imaginer créer un monde autonome dans lequel une forme d'intelligence évoluerait.
Je serais juste informé de l'évolution sur notre salon IRC.
Peut-être avec un serveur web pour avoir une représentation visuelle de cet univers.
J'ai fini par mettre ca de coté.

### l'idée qui reste

Je n'ai gardé que la première étape "un environnement simple" dans lequel faire évoluer mes petits programmes.


## 2) Contrainte: de simplicité technique

Si la programmation de la partie "intelligente" d'un programme va être compliqué, j'aurais voulu de pas perdre du temps et des cheveux à programmer l'environnement dans lequel tout cela évoluera!

Il faut donc trouver un univers de jeu simple à gérer (coté serveur) et simple à représenter (coté client).
Pour au final trouvé de la compléxité dans les possibilités.

J'aimerais un jeu similaire au caractéristique du jeu d'échec.

* un environnement simple : le plateau de jeu est simple.
* des éléments simples et prévisible : les pièces sont définies et leur déplacements sont connus et simples.
* L'intérêt réside dans la multitude de possibilités.


## 3) Un univers en 3D

Les calculs de distance ou de trajectoire en 3 dimensions est rapidement un cauchemard.

On oublie donc les voyage spaciaux en 3D (cf. EVE online)

Essayons de réduire la difficulté en réduisant le nombre de dimensions.
Revenons sur un espace en 2D !


## 4) Un univers en 2D

Il y a hélà toujours encore beaucoup de calculs.

Mettons nous à la place du programme intelligent que nous essayons de programmer.

Par exemple on imagine le cerveau artificiel d'une unité ... l'une des premières informations qu'il lui faudra est "dit moi ce qui m'entourne"
L'information dont on a besoin est "la liste des objets qui sont proche de moi avec leur distance respective"

Dans un univers où l'on gère des coordonnees 2D il faut calculer les distances tous les objets autour d'un point de départ (les coordonnees de l'unité).
Ca n'a rien de très difficile mais si on fait ca pour des milliers d'unités évoluant dans un univers vaste... on est vite confronté à des difficultés qu'on aimerait éviter,
afin de pouvoir se concentrer sur la logique de l'intelligence qu'on essait de programmer.

Arrangeons nous pour que notre univers est une forme plus simple.


## 5) Un univers encore plus simple

Si la 3D est trop compliquée à représenter, réduisons à la 2D.
Si la 2D est encore un peu trop compliquée, réduisons à la 1D.


## 6) Un univers en 1D

Voila je créé mon univers en 1D : une ligne avec des coordonnees entière (0, 1, 2, ..., max)
N'y a t'il rien de plus simple à gérer qu'une simple liste ?!


```lua
max=10 -- la position 10 deviendra 0
me=2

function move(who, offset)
	return (who + offset) % max
end

me = move(me, 1) --> 3
me = move(me, 7) --> 0 (car 10 -> 0)
me = move(me, -2) --> 8
```

## 7) Un univers sans fin

Aller soyons fou arrangeons nous pour relier la fin de l'univers à son commencement.
On obtient un univers en forme de cercle!

"La perfection est dans le cercle" vous dis-je !

Je le baptise "cercle univers" : le cercl'univers !



# Un univers trop simple

Le problème de mon univers trop simple est qu'il n'a pas assez de profondeur pour en faire un jeu interessant.


# Un univers moins simple

Il faut introduire des possibilités (mais sans trop de complexité à le gérer).

Nous avons donc des points reliés entre eux pas un chemin unique.
On ne peut pas joindre directement un point qui ne soit pas à coté de notre point de départ.

Exemple: en partant de "2" peut joindre directement "1" ou "3" mais pas "4".

Sur chaque point on peut sans trop de mal imaginer stoquer un certain nombre d'informations.


## Des déplacements alternatifs

On peut facilement envisager d'ajouter sur un point une information additionnelle qui indique un lien vers un autre point. Un chemin alternatif.

On obtient des moyens de déplacement conventionnel par le chemin en cercle (très simple à gérer, très simple à calculer).
Et des chemins alternatif, comme des racourcis (simple à gérer, relativement simple à calculer).

Au final on vient de transformer un réseau en cercle en d'un réseau maillé.
La compléxité est au rendez-vous mais la gestion des données reste très basique.
La compléxité ajoutée se fera sentir lors des calculs de distance.


# Le défi personnel

Au delà de l'Intelligence Artificielle qui est un défit à part entière.
J'ai envie de créer un jeu qui utilise des mécaniques qui sont habituellement éludé/évité.

* Imaginez un jeu où l'on voyagerait en hyper espace !
* Imaginez un jeu où l'on traverserait un trou de verre et où on évoluerait dans un univers parallèle !
* Imaginez un jeu ou l'on voyagerait dans le temps !

Vous l'avez compris je n'ai peur de rien !

!	Mais j'avoue avoir du mal a trouver un gameplay adapté et interressant.
!	J'ai envie de jouer avec l'espace (multi dimension) et le temps
!	mais ca devient rapidement soit inutilement compliqué, soit ininterressant pour un jeu, soit effrayant pour la majorité des gens ...


# Un jeu spacial

Il fallait trouver un thème de jeu.
J'ai voulu faire un jeu avec "des planètes et des vaisseaux dans l'espace", un "Space Opera".

* Pour les déplacement sur les bords du cercle on peut imaginer un déplacement "conventionnel".
* Pour les déplacement de planète à planète on peut imaginer une "porte des étoiles" ou une "hyper-vitesse"
* Pour les déplacement vers un univers parallèle il faudra gérer un 2eme "cercle".
* Pour ce qui est du voyage dans le temps, je n'avais pas d'idée.


## Jouer avec le temps

Il y a eu un élément déterminant, j'ai vu un film nommé [Edge of tomorrow](https://fr.wikipedia.org/wiki/Edge_of_Tomorrow).

Le principe de "mourir et recommencer" m'a fait penser à intégrer la rejouabilité d'une partie dans le gameplay lui-même.

Si on pense au jeu d'échec, humain contre machine on peut imaginer perdre une partie en rejouer une et connaitre le comportement de l'adversaire IA.


## Gameplay humain VS machine

Une approche ou le joueur joue contre une IA. Le but est de comprendre comment elle fonctionne et trouver ses failles.
Un peu comme un "combat de boss" où l'on découvre ses "patterns d'attaques" pour ensuite les éviter.


## Gameplay scenario resolution de problème

C'est une approche humain contre machine ou machine contre machine.

Ca conciste a créé une partie dans un état déjà avancé.
Où le but est de réussir un objectif.

L'intérêt étant d'y arriver mais aussi de pouvoir comparer avec ses amis la manière d'y arriver.

On peut aussi remplacer l'humain par un humain qui programme son IA et faire jouer cette IA.



!	Le principe "die and retry" m'a reveillé l'envie de faire un jeu ou on puisse partager et forker n'importe quel moment du jeu et pouvoir comparer tous ces forks ...







## Les déplacements

les points sont donc des planètes ou des système solaires.
Un petit problème survient... A notre échelle les éléments stellaire sont espacé, loin les uns des autres, en résumé l'univers est grand.

Dans notre monde réel, nos moyens de déplacement actuels sont très lent.

Dans les jeux video spaciaux, il faut pouvoir parcourir de très grandes distances en peu de temps.
Si ce n'est pas le cas, le joueur risque de mourir (d'ennuis) avant d'atteindre la 1ère planète.

La science fiction (battle star galactica, stargate, ...) nous fournit un tas de moyen de transport rapide.
* téléportation
* porte des étoiles, trou de verre
* hyper-vitesse (vitesse sub-liminale, vitesse sub-liminique)


## L'hyper-vitesse

Je veux de l'hyper-vitesse !
Elle déplace un vaisseau d'un bout à un autre de la galaxie (parfois en empruntant un "passage" effémère préalablement créé)


## La problématique de l'hyper-vitesse


Ce qui me dérangeait est ce qui se passe pendant ce déplacement, et son existance par rapport au reste du monde.

Je voulais éviter de faire des simplifications qui entraine des problèmes de design.
Cf. ogame : une flotte de vaisseaux spaciaux en déplacement est inattaquable, c'est stupide.


Par exemple le vaisseau peut-il être suivis par un autre vaisseau ? peut-il être détruit ? où se trouve-il pendant ce déplacement ?
J'ai donc proposé de créer un 2eme plan d'existance pour y placer les vaisseaux en déplacement...


Dans un jeu où l'on voyagerait en hyper espace ... ou on traverserais un trou de verre et on evoluerait dans un espace parallèle !
ou bien on voyagerait dans le temps !
J'ai peur de rien !
Mais j'ai du mal a trouvé un gameplay adapté, interressant...



Envie de jouer avec l'espace (multi dimension) et le temps
mais ca devient rapidement soit inutilement compliqué, soit ininterressant pour un jeu, soit effrayant pour la majorité des gens ...



Le fun pour la machine


Le fun pour le dev

Le fun pour le joueur

casual ?
hardcore gamer ?


Envie d'originalité
===================

A certain moment de ma vie j'ai essayé d'imaginer des jeux tres originaux...
Ainsi qu'un besoin de relever un challenge de la "compléxité finalement abordable à tous".

Les idées de challenge.
Faire un jeu avec
* des univers parallèles
* des plans d'existance multiples
* du voyage dans le temps

# Des clés de réussite

- choix
- progression
- compréhension/prise en main
- rejouabilité, évolution

