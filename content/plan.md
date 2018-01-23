# Plan du mémoire

## Introduction

- Les dernières innovations RA en date, état rapide de l'industrie :
  - Magic Leap, HoloLens, Meta, ARKit et ARCore, OpenXR
  - Données sur la croissance du marché en 2016, 2017 + potentiels marchés à atteindre + évolution hype curve RA
- Définition et principe de la RA
  - Définition vulgarisée
    - « generate digital [3D content that] blend seamlessly with [real world content] to produce lifelike digital objects that coexist in the real world. This [...] allows our brain to naturally process digital objects the same way we do real-world objects, making it comfortable to use for long periods of time. » (https://www.magicleap.com/)
    - Métaphore du téléphone portable placé dans des lunettes
  - Définition technique
    - http://doc-ok.org/?p=337
    - Reprendre Azura 1997 : contenu 3D virtuel, aligné avec le contenu réel, en temps réel
    - Stereoscopie, effet de parallaxe)
  - Méthodes : CAVE, écran d'appareil mobile, HMD (Video see trough vs. optical see trough), lentille
- État rapide de la recherche :
  - Les domaines qui interviennent : computer graphics, computer vision, human-computer interactions
  - Les connaissances techniques
  - Les connaissances en IHM pour la RA
- Pourquoi étudier les IHM en RA (+ designer interfaces 3D et interactions multimodales)
  - « We live and think in a 3D world, not on a flat screen. Our spatial interface includes multiple input modes including voice, gesture, head pose and eye tracking. This collective input system provides the tools needed to break free from outdated conventions of point and click interfaces, delivering a more natural and intuitive way to interact with technology. »
  - « We believe MR should be human and object centric, and use the world as a device (aka “clickable world”) » UnityFutureMRPartIII2017
- Problématique : les interfaces en RA ont commencé à être étudiée et ont des avantages/faiblesses et le touchscreen a d'autre propriétés. Les deux ne sont pas beaucoup étudiés conjointement pourtant vont coexister dans les années à venir.
- Expliquer rapidement projet (ce que j'ai fait) et pourquoi : comparaison de techniques d'interactions, de sélection et de mouvement de contenu 3D, projeté en RA autour d'un appareil mobile tenu en main, aligné sur le même plan de l'écran de cet appareil mobile (+ HMD RA video + librairie RA pour Unity)
- Contributions
- Plan du mémoire

## Revue de littérature

Voire notes_RL.md

## Matériel et méthodes

### Matériel

- Choix du video see trough
  - Principe
  - Avantages/inconvénients par rapport à l'optical see through
- Principe inspiré de SteptoeAR-Rift2014
  - Choix des caméras : même fov, même résolution + stéréo. Choix ovrvision
  - Tracking du DK2
- Téléphone

### Logiciels

- Unity
- OpenCV
  - ArUco
  - Calibration
- Unity networking

### AR video see through

Goal: Align the 3D content filmed by the virtual camera with the images filmed by the physical camera.
How: Match the camera parameters of the two cameras. Intrinsic camera parameters: camera matrix (how the 3D world is projected into a 2D image), distorsion coefficients (), image size. Extrinsic camera parameters: position and rotation in the 3D world.

#### Pinhole camera model (physical camera)

https://www.scratchapixel.com/lessons/3d-basic-rendering/3d-viewing-pinhole-camera/how-pinhole-camera-works-part-1
https://www.scratchapixel.com/lessons/3d-basic-rendering/3d-viewing-pinhole-camera/how-pinhole-camera-works-part-2

#### Perspective projection, undistortion and rectification (virtual camera)

Perspective projection matrix (virtual camera frustum) = projection transform (camera matrix) + Normalized Device Coordinates (NDC) matrix (orthogonal projection) : http://ksimek.github.io/2013/06/03/calibrated_cameras_in_opengl/
Perspective projection matrix = simpler pinhole camera model : http://ksimek.github.io/2013/08/13/intrinsic/
« They all require a precise understanding of how the pixels in a 2D image relate to the 3D world they represent. In other words, they all hinge on a strong camera model. »

« While optical see-through AR is an attractive ideal, in practice it is very difficult to achieve accurate registration with optical see-through AR systems. (Registration is the alignment of the virtual objects shown in the display and their real-world referent). Most of these limitations come from the properties of the display itself, not the calibration procedures. » : https://www.artoolkit.org/documentation/doku.php?id=8_Advanced_Topics:config_optical_see-through

#### Perspective projection rectification from fisheye image in the unified projection model used in omnidirectional camera calibration (ccalib OpenCV's module)

Omnidir camera model : http://rpg.ifi.uzh.ch/docs/omnidirectional_camera.pdf

determine Knew https://medium.com/@kennethjiang/calibrate-fisheye-lens-using-opencv-part-2-13990f1b157f

explications : http://www.bobatkins.com/photography/technical/field_of_view.html
fisheye projections : https://wiki.panotools.org/Fisheye_Projection
various lens projections : http://michel.thoby.free.fr/Fisheye_history_short/Projections/Various_lens_projection.html

ccalib article : https://hal.archives-ouvertes.fr/file/index/docid/767674/filename/omni_calib.pdf

#### Off-axis projection model used in VR stereo camera

why : http://rifty-business.blogspot.ca/2013/10/understanding-matrix-transformations.html
description of the model : http://doc-ok.org/?p=27
consequences of bad configured camera matrix : http://rifty-business.blogspot.ca/search/label/projection
stereo vr : https://www.youtube.com/watch?v=iqcNrI_hkMs
off-axis projection model in stereo vr : http://doc-ok.org/?p=77
usage/implementation in oculus rift (dk1) : http://doc-ok.org/?p=756

very complete presentation that explain the problem and the solution : http://paulbourke.net/papers/HET409_2004/het409.pdf
good description of the projection model : http://csc.lsu.edu/~kooima/pdfs/gen-perspective.pdf

#### Stereo calibration

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

### Calibration

- Voir
    - AdrianKaehler2017 - Learning OpenCV 3 - Chapitre 11 + OpenCV3.3.0-Calib3dModule + notes 2016-11-28 pour le modèle pinhole de caméra + calibration
    - AdrianKaehler2017 - Learning OpenCV 3 - Chapitre 19 pour la calibration stereo + LeapMotionAlignmentCameraAR2015 pour expliquer pourquoi on applique aux caméras virtuelles l'ICD et non l'IPD
    - OpenCV3.3.0-CcalibModule (car module fisheye buggé et citer le papier qui dit que le modèle de caméra omnidir s'appliquer aussi aux caméras fisheye) pour la calibration fisheye
- Autres ressources :
    - Stereo rectification : http://www.sci.utah.edu/~gerig/CS6320-S2013/Materials/CS6320-CV-F2012-Rectification.pdf
    - Stereo calibration tutorial :
        - http://www.jayrambhia.com/blog/stereo-calibration
        - http://sourishghosh.com/2016/stereo-calibration-cpp-opencv/
- Voir BuJo p.150 + AR-Rift PArt 5 pour les équations de configuration de la caméra virtuelle et du placement du background pour qu'il soit aligné avec le contenu 3D filmé par la caméra virtuelle
- Conseils/notes calibrations :
    - Utiliser une board la plus plate possible (attention à l'humidité de l'air qui est absorbée par le papier)
    - Utiliser une bonne lumière pour que la board soit bien détectée et sans reflets
    - Désactiver l'autofocus de la caméra : une calibration se fait pour une focale fixe (les distorsions restent les même mais pas la camera matrix)
    - La caméra ou la board doit rester fixe pendant la calibration
    - Prendre des dizaines de captures remplissant uniformément l'espace de capture de la caméra en variant les angles de 
    - L'objectif est d'avoir une erreur de reprojection inférieure à 1 pixel
    - OpenCV est système main droite dans son système de coordonnées (http://homepages.inf.ed.ac.uk/rbf/CVonline/LOCAL_COPIES/OWENS/LECT9/img4.gif) alors qu'Unity est système main gauche : il suffit d'inverser l'axe des Y (https://answers.unity.com/storage/temp/8053-spaces.jpg) : faire un petit graphe comme la 2e image
    - OpenCV encode sa rotation dans un vecteur dont les coordonnées normalisées donnent l'axe et sa norme l'angle autour de cet axe, alors qu'Unity utilise des quaternions. Adapté ce calcul (http://www.euclideanspace.com/maths/geometry/rotations/conversions/angleToQuaternion/) pour passer du premier au second : https://github.com/enormand/aruco-unity/blob/master/src/aruco_unity_package/Assets/ArucoUnity/Scripts/Plugin/Cv/Vec3d.cs

### Synchronisation réseau

- DevicesSyncUnity basé sur Unity Unet