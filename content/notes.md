# Notes

## Introduction + Revue de littérature

### Berard2009 - Did "Minority Report" Get It Wrong? Superiority of the Mouse over 3D Input Devices in a 3D Placement Task

« Interaction is not defined by an input device alone, but by the combination of a device and an interaction technique. In the example of 3D object rotation, the mouse is typically used with the virtual sphere technique while a free-space device is used with a direct mapping (either absolute or relative) Thus, each device must be matched with its most suitable interaction technique in making performance comparisons, rather than choosing a single interaction technique for all devices. »

### Robertson1998 - Data mountain

Ça fonctionne de s'appuyer sur la mémoire spatiale humaine : justifie notre concept d'organiser l'espace autour du cellulaire comme une idée pertinente. On pourrait organiser les applications dans le plan et en profondeur le long d'un plan qui part de la base du cellulaire avec une pente positive : cela permet de voir toutes les applications, comme sur des gradins d'un stade (c'est ce que Data Moutain suggère comme placement des app dans l'espace)

### Esteves2017 - SmoothMoves

Justifie de faire de l'IHM pour la RA : « The latest products, such as Microsoft HoloLens include powerful computers, high resolution displays and sophisticated tracking. While these technical achievements are impressive, there is less clarity about the best ways for users to interact with AR contents and interfaces. »

Liste des types de techniques d'interactions en IHM pour les HMD en RA : « There is an active community exploring viable modalities for head-mounted displays (HMDs) including on-headset touch mid-air hand input and the use of dedicated wearable peripherals such as gloves or belts Within this space, we argue that input from movements of the eyes and head are particularly practical and appealing: in such scenarios, hands remain free and all sensing can be integrated into the headset.

Argument du prix sur head-tracking vs eye-tracking : « Using head motions accords considerable practical benefits, primarily that the Inertial Motion Units (IMUs) needed to accurately track head movements are small, cheap, low power and already integrated into the majority of AR glasses and other wearables.

Principe et explication de pourquoi l'étudier (dans le HoloLens, le Cardboard) de la technique d'interaction du pointage avec le regard : « Ray-based pointing, in which users interact by projecting a ray from their head to intersect with a target of interest, is the most common and has been integrated into current head-mounted displays, such as the Google Cardboard and the Microsoft HoloLens. »

Explication du pointage avec le regard : « Gaze is the inseparable product of head movements plus eye movements. The relationship between these activities is sophisticated. At the most fundamental level, the Vestibulo-Ocular Reflex (VOR) continuously stabilizes gaze by adjusting (basically inverting) eye position in response to changes in head position sensed by the vestibular system »

Propriétés du du pointage avec le regard : « A number of properties make smooth pursuits movements useful as an input technique. First, they are innate. Users know how to visually track targets and can generate this kind of motion without training. Second, they are distinctive. Users are only able to generate smooth pursuits eye movements in the presence of visually moving targets. Third, they operate on movement not position. As such, they are relatively immune to changes in target size and robust to tracking errors – capturing changes in gaze is much simpler than accurately determining what a user is looking at. Fourth, they are operated hands-free. And fifth, they do not require users to memorize gestures. Several systems have been recently introduced to leverage these properties.

Les auteurs ont montré que les techniques d'interactions (en tout cas le suivi de cible) basées sur le mouvement de la tête (par exemple un curseur projeté depuis le centre de la tête sur des cibles dans la RA) est aussi efficace en terme de performances, et peu même être préféré, que les techniques d'interactions basées sur les mouvements des yeux et a les mêmes propriétés.

### Berge2014 - Exploring smartphone-based interaction with overview+detail interfaces on 3D public displays

Les utilisateurs ont préféré les interactions Mid-Air Phone et Mid-Air Hand (avec ou sans entraînement) versus les interactions touchscreen dans une interface Overview+Detail d'exploration de contenu 3D : un écran faisait overview et un téléphone mobile de detail.

Nous on ne ce pose pas la question de l'entraînement : car on considère que c'est une IHM qui serait utilisée au quotidien ou professionnellement : donc c'est correct d'avoir un temps d'apprentissage.

Il y a trois de types de solutions/approches pour visualizer/afficher de larges espaces d'information : Overview+Detail, Focus+Context et Zooming. Nous n'étudions que Zooming, car c'est le plus courant sur les appareils mobiles. Or on compare les techniques d'interactions de notre solution à un mobile seul. Il aurait été intéressant cependant, dans une deuxième expérimentation, de comparer ces techniques de visualization sur notre solution versus sur un appareil mobile seul.

Toutes nos conditions de la VI technique sont des direct mapping (mappe directement la position de l'input au curseur).

## Large information space visualization on mobile phone - Burigat2011 - On the effectiveness of Overview+Detail visualization on mobile devices

« Results of the experiment suggest that both direct manipulation of the overview and highlighting objects of interest in the overview have a positive effect on user performance in terms of the time to complete search tasks on mobile devices, but do not provide specific advantages in terms of recall of the spatial configuration of targets. »

### 3D navigation with a mobile phone - Peephole

Notre condition téléphone seul est en fait un static navigation peephole, et notre condition peephole est dynamic navigatino peephole.
« Handheld displays leave little space for the visualization and navigation of spatial layouts representing rich information spaces. The most common navigation method for handheld displays is static peephole navigation : The peephole is static and we move the spatial layout behind it (scrolling). A more natural method is dynamic peephole navigation: here, the spatial layout is static and we move the peephole across it. » Mehra2006

#### Huerst2010 - Dynamic versus static peephole navigation of VR panoramas on handheld devices

« We present a formal evaluation and usability studies comparing two interaction concepts. In the first one, the device is seen as a static peephole and the data is moved behind it via touch screen-based scrolling. In the second one, a mobile phone’s sensors are used to create a dynamic peephole that can be moved over static content. In the results of our formal analysis sensor-based dynamic peephole navigation performed twice as good in an orientation task, 75\% better in an object size discrimination task, and was preferred by 80\% of the users. Despite these advantages, additional usability studies indicate that if they are sitting, a majority of users resort to touch screen-based static peephole navigation when interacting. »

#### Mehra2006 - Navigating on handheld displays

« Subjects viewed a spatial layout containing two lines on a static display screen. Only a part of the screen—the peephole—was visible. Subjects had to discriminate line length by either moving a dynamic peephole across a static layout of the lines or by moving a dynamic layout behind a static peephole. »
« Discrimination thresholds for static peephole navigation were 50–75\% higher than for dynamic peephole navigation. Furthermore, static peephole navigation took 24\% more time than dynamic peephole navigation »

## Matériel et méthodes

### Présentation du matériel

- Principe : AR video see-through avec un casque VR diffusant des caméras stereo fisheye + leap motion
- Exemples de projets similaires
    - https://pdfs.semanticscholar.org/a53a/3d25b8258b5331c23056d4696691dabd8eb9.pdf
    - https://link.springer.com/content/pdf/10.1007/s11554-016-0640-9.pdf
    - AR-Rift: https://vr.cs.ucl.ac.uk/portfolio-item/ar-rift/
    - OculAR: https://arxiv.org/abs/1604.08848
    - AR-Rift 2: http://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=7892261
    - Impact of visual and experiential realism on distance perception in VR using a custom video see-through system: https://dl.acm.org/citation.cfm?id=3119892
- Choix techniques
    - Casque de VR (permet tracking)
    - Caméras
    - Leap Motion
    - Téléphone Android
    - Unity

### ArUco Unity

- Voir 2016-01-25 pour l'archi :
    - Parler du principe pour dialoguer avec un plugin C++ : couche en C, gestion des pointeurs en faisant une API C# qui encapsule ces appels à la couche C : plugin C++ OpenCV <-> couche en C <-> couche C# reproduisant la couche C++ 
    - couche Unity avec des gameobjects et components au dessus de la couche C#
- Aussi parler de la mémoire partagée entre Unity et OpenCv sur les images :
    - calcul de taille : 2 cameras * 950 px * 960 px * 3 bytes (RGB) = 5,47 MB
    - lecture du buffer dans sens différents (voir note 2017-04-11)
    - Threads et ordonnancement + copies des buffers images (c'était plus rapide de faire des copies que de faire attendre l'affichage avant le nouveau detect : voir note 2017-05-10) -> il n'y a pas d'attente/blocages entre les threads hormis sur les copies de buffer
- La doc qui a été faite, la petite PR pour rendre compatible les modues aruco et ccalib, le package Unity, les forks et ajouts sur internet, le package pour ovrvision (preuve que c'est extensible (citer les termes du cours MGL843))
- Utiliser des boards de 2 markers minimum pour la détection : beaucoup plus robuste qu'utiliser des markers seuls

### Calibration des caméras

- Voir AdrianKaehler2017 - Learning OpenCV 3
    - Chapitre 11 + OpenCV3.3.0-Calib3dModule + notes 2016-11-28 pour le modèle pinhole de caméra + calibration
    - Chapitre 19 pour la calibration stereo + LeapMotionAlignmentCameraAR2015 pour expliquer pourquoi on applique aux caméras virtuelles l'ICD et non l'IPD
    - OpenCV3.3.0-CcalibModule (car module fisheye buggé et citer le papier qui dit que le modèle de caméra omnidir s'appliquer aussi aux caméras fisheye) pour la calibration fisheye
- Voir BuJo p.150 + AR-Rift PArt 5 pour les équations de configuration de la caméra virtuelle et du placement du background pour qu'il soit aligné avec le contenu 3D filmé par la caméra virtuelle
- Conseils/notes calibrations :
    - Utiliser une board la plus plate possible (attention à l'humidité de l'air qui est absorbée par le papier)
    - Utiliser une bonne lumière pour que la board soit bien détectée et sans reflets
    - Désactiver l'autofocus de la caméra : une calibration se fait pour une focale fixe (les distorsions restent les même mais pas la camera matrix)
    - La caméra ou la board doit rester fixe pendant la calibration
    - Prendre des dizaines de captures remplissant uniformément l'espace de capture de la caméra en variant les angles de capture
    - L'objectif est d'avoir une erreur de reprojection inférieure à 1 pixel
    - OpenCV est système main droite dans son système de coordonnées (http://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/OWENS/LECT9/img4.gif) alors qu'Unity est système main gauche : il suffit d'inverser l'axe des Y (https://answers.unity.com/storage/temp/8053-spaces.jpg) : faire un petit graphe comme la 2e image
    - OpenCV encode sa rotation dans un vecteur dont les coordonnées normalisées donnent l'axe et sa norme l'angle autour de cet axe, alors qu'Unity utilise des quaternions. Adapté ce calcul (http://www.euclideanspace.com/maths/geometry/rotations/conversions/angleToQuaternion/) pour passer du premier au second : https://github.com/enormand/aruco-unity/blob/master/src/aruco_unity_package/Assets/ArucoUnity/Scripts/Plugin/Cv/Vec3d.cs. Voir BuJo 2017-11-07.

### Intégration du Leap Motion

### DevicesSyncUnity

### Mesure des participants