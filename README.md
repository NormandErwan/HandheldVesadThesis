# Handheld VESAD - Master Thesis

> Extension of a mobile screen by augmented reality: Handheld VESAD (Virtually Extended Screen-Aligned Display).

[![Creative Commons License](https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png)](https://creativecommons.org/licenses/by-nc-nd/4.0/) Erwan Normand, 2018.

This work is licensed under a [Creative Commons Attribution-NonCommercial-NoDerivatives 4.0 International License](https://creativecommons.org/licenses/by-nc-nd/4.0/).

See also the [experiment analysis](https://github.com/NormandErwan/HandheldVesadAnalysis) and the [thesis presentation](https://github.com/NormandErwan/HandheldVesadPresentation).

## Abstract

Significant and recent progress in research and in industry destined augmented reality to deeply integrate both in our personal and professional life.
We propose using augmented reality to extend the screen of a smartphone beyond its physical limits with a virtual surface that is co-planar with the phone and that follows as the phone is moved. This creates the feeling of interaction with a unique big handheld screen. We call this extension a VESAD, or Virtually Extended Screen-Aligned Display.
We illustrate first several ways that a VESAD could be used with two different viewing modes: *multi-windowed view*, to support multi-task, and *extended view* where an application uses the whole extended screen.
We also present two novel interaction techniques: *wrist*, where the user performs a quick rotation of the phone to switch the information shown in the VESAD, and *slide-and-hang* whereby the user can detach a VESAD and leave it hanging in mid-air.
We then describe our video-based augmented reality head-mounted display we developed with a large field of view (100° x 98° for each eye) and our free and open-source (FOSS) augmented reality library ArucoUnity. It ports the camera calibration and fiducial marker tracking functions from the FOSS computer-vision library OpenCV to the 3D engine Unity.
We conducted an experiment that compared three interfaces used for an abstract classification task: the first using only a smartphone, the second using the phone for input but with a VESAD for output, and the third where the user performed input in mid-air on the VESAD (as detected by a Leap Motion).
The second user interface was found to be superior in task completion time, furthermore with the last trials of the participants. It was also the most performant for navigation and was subjectively preferred over the other two interfaces.
We finally report implementation, interfaces and interactions guidelines to create a VESAD.

## Résumé (French)

Les récentes et importantes avancées dans la recherche et en industrie promettent à la réalité augmentée (RA) de s'intégrer profondément dans nos vies personnelles et professionnelles, malgré des limites technologiques encore existantes, pour augmenter nos perceptions du réel et les interactions avec nos environnements.
Nous proposons d'utiliser la RA pour étendre l'écran d'un téléphone, au-delà de ses limites physiques, avec un écran virtuel coplanaire, synchronisé et suivant ses mouvements, créant la perception d'un unique grand écran étendu tenu en main. Nous appelons cette extension *Virtuality Extended Screen-Aligned Display* (VESAD).
Nous décrivons les modes de vues possibles avec cette affichage : *vue multi-fenêtres*, supportant du multi-tâche, et *vue étendue*, où une application utilise tout l'écran étendu.
Nous présentons aussi deux nouvelles techniques d'interaction : *wrist*, où l'utilisateur fait une rotation rapide du poignet pour substituer l'affichage avec un autre, et *slide-to-hang* pour détacher l'écran étendu en une fenêtre virtuelle séparée du téléphone.
Nous décrivons ensuite la conception de notre propre visiocasque de RA à large champ de vision (100° x 98° pour chaque œil), permettant de voir complètement l'écran étendu, ainsi que le développement de notre bibliothèque libre de RA ArucoUnity, qui porte sur le moteur 3D Unity les fonctions de suivi de marqueurs et de calibration de caméra de la bibliothèque libre de vision par ordinateur OpenCV.
Nous menons ensuite une étude expérimentale pour évaluer, d'une part, les avantages d'un téléphone à écran étendu par rapport à un téléphone non étendu et, d'autre part, pour comparer l'utilisation de l'écran tactile à des interactions avec la main sur l'écran virtuel. Nous répliquons une tâche de classement issue de la littérature sur les affichages muraux, impliquant de la navigation et des sélections.
Nos résultats indiquent que la combinaison du téléphone à écran étendu avec les interactions tactiles s'est montrée la plus rapide, en particulier quand la tâche était maîtrisée des participants, et la plus performante en termes de navigation. Elle a également été préférée des participants. Néanmoins, plusieurs participants ont vu plus de potentiel dans les interactions avec la main virtuelle avec l'écran étendu.
Nous donnons enfin des recommandations d'implémentation, de conception d'interface et de techniques d'interaction pour un VESAD.
