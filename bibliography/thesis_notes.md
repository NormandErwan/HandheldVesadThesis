# Notes de lectures

## The personal cockpit: a spatial interface for effective task switching on head-worn displays (EnsFinneganIrani2014)

### Problème de recherche

Il y a une prolifération de HMD peu cher, qui permettent d'interagir avec du contenu en permanence, mais qui m'affiche que des interface en 2D à distance fixe de l'utilisateur. Il n'y a pas d'exploitation de la périphérie de l'utilisateur et peut créer des problèmes d'occlusion avec le monde réel. De plus, on retrouve le même problème que les smartphone où le multitache demande de switcher entre des applications, ce qui coûte cher. Pourtant un HMD n'a pas de limites physiques et peut créer des IHM dans l'espace (en 3D et non plus sur un écran 2D), et composées de plusieurs fenêtres.

### Solution

Explorer la conception d'interfaces spatiale mobiles, avec de multiples affichages flottants dans les airs à l'aide un prototype. Pour cela, déterminer quels sont les meilleurs facteurs de design pour concevoir un tel prototype, et les valider avec expérimentations empiriques. Enfin, faire des recommendations pour al conception d'IHM dans l'espace.
Les facteurs explorés sont :

- le FOV : un humain a 200° en horizontal, 130° en vertical, fovea est 3°h8°v, un fov mini pour un hmd est 40°h (si pour fovea) ou 60°h (pour immersion)
- la séparation angulaire (angle de placement du contenu dans l'espace) : meilleur perfs si petits angles, jusqu'à 85° de rot h et 50° rot haut et 60-70° rot bas
- la taille d'affichage (ou résoluton) : plus haute meilleur pour navigation, certaines taches (par ex: recherche mais pas tracé de route) profitent d'un plus grand affichage, mais souvent le fait de pouvoir se déplacer dans l'espace est plus important que d'avoir un grand affichage
- la distance d'affichage des fenêtres : 0.25m minimum mais 1m recommandé pour écrans physiques, impacts sur perfs si affichages à distances différentes, en VR la prof est mal estimée
- méthode d'entrée : directe est plus naturelle mais pose des problémes car vr intangible et problèmes d'estimation de distances
- placement des affichages : sur le monde ou les objets, sur la tête, sur le corps, sur les mains

### Méthodologie

Réaliser quatre expérimentation pour déterminer et valider ces paramètres :
1 Tache de recherche visuelle d'objet
VI : angle de placement (50,75,100,125,150% du FoV) et distance placement (40,60,80,100 cm)
VC : FoV (40°x30°)
VD : temps d'essai, effort perçu

2 Tache de sélection d'une cible
VI : placement (world-, body-, view-fixed), distance placement (40, 50, 60 cm), location cible (centre, haut, bas, gauche, droite)
VC : FoV (40°x30°), 70% du FoV, input direct
VD : temps d'essai, erreurs sélection, effort perçu

3 Tache de recherche visuelle d'objet
VI : angle de placement (50,75,100,125,150% du FoV), distance placement (40,60,80,100 cm)
VC : FoV (40°x30°), 70% du FoV, input direct, world-fixed, 50 cm, curved windows
VD : temps d'essai, erreurs sélection, effort perçu

4

### Résultats

1 75% pour temps, et inconfort à 40 cm malgré pas de diff donc 60 cm min
2 world-fixed le plus précis (pour les autres le manque de précision de l'outil de sélection contrebalançait la proprioception), mais pas de diff de temps + précision meilleure quand distance proche = plus le bras s'allonge, moins c'est précis
3
4

Autres : Les fenêtres VR sont compatibles avec input direct même si FoV limité. Un layout courbe fonctionne bien et limite les erreurs. 

### Limites

Simplement testé l'input direct. Que de l'intangible. FoV très limité et fixe. Il faudrait tester sur plus de taches pour voir si les résultats sont généralisables.

### Concepts-clés

Head-worn display; head-mounted display; task switching; spatial input; spatial user interface; virtual window management; multi-display environment

### Futurs travaux

Répliquer sur un vrai HMD, pas un CAVE comme dans les expériences. Mieux supporter l'input direct et tester d'autres techniques d'input. Mieux comprendre les limitations de la proprioception et de la fatigue utilisateur, donc permettre une pus grand stabilisation quand en mode body-fixed ou changer de mode en fonction du contexte.

### Références centrales

- [12] Steven Feiner , Blair MacIntyre , Marcus Haupt , Eliot Solomon, Windows on the world: 2D windows for 3D augmented reality, Proceedings of the 6th annual ACM symposium on User interface software and technology, p.145-155, December 1993, Atlanta, Georgia, USA
- [13] George W. Fitzmaurice, Situated information spaces and spatially aware palmtop computers, Communications of the ACM, v.36 n.7, p.39-49, July 1993
- [22] Frank Chun Yat Li , David Dearman , Khai N. Truong, Virtual shelves: interactions with orientation aware devices, Proceedings of the 22nd annual ACM symposium on User interface software and technology, October 04-07, 2009, Victoria, BC, Canada
- [34] Lauren Shupp , Robert Ball , Beth Yost , John Booker , Chris North, Evaluation of viewport size and curvature of large, high-resolution displays, Proceedings of Graphics Interface 2006, June 07-09, 2006, Quebec, Canada

## Multifi: Multi fidelity interaction with displays on and around the body (GrubertHeinischQuigleyEtAl2015)

### Problème de recherche

Les écrans se multiplient dans notre espace, qu'ils soient publics ou personnels ; une personne va même souvent transporter plusieurs appareils sur soi. Mais ces appareils ne prennent pas en compte la présence les uns des autres. Pourtant, le travail sur ordinateur avec plusieurs écrans, l'accès à distance d'un ordinateur, ou le screen mirroring montrent que la coordination d'appareil est intéressante.

### Solution

Créer une plateforme pour implémenter une IHM entre différents écrans d'affichage : et ainsi permettre d'utiliser de manière fluide différents appareils conjointement. Il faut pour cela s'accomoder de résolution et de FoV différents pour les écrans de chaque appareil, et de variations de méthodes d'entrées de chaque appareil.