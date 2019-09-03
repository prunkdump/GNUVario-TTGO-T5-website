---
layout: page
title: Configuration
---

Avant de configurer le variomètre, vous devez savoir comment [compiler le code]({{ site.baseurl }}{% link 4-code.md %}). Assurez-vous de bien connaître l'IDE Arduino.

La configuration du variomètre est séparée en 2 parties.

1) La configuration matérielle
--------------------------------------

La configuration liée au matériel se fait en éditant les fichiers [libraries/HardwareConfig/HardwareConfig.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/HardwareConfig/HardwareConfig.h) et [libraries/HardwareConfig/HardwareConfigESP32.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/HardwareConfig/HardwareConfigESP32.h) dans votre dossier Arduino. Si vous n'avez pas d'éditeur adapté à l'écriture de code, vous pouvez le télécharger [Notepad++](https://notepad-plus-plus.org/).

Commencez par vérifier les fichiers. Il y a un fichier commun à tout les microcontroleurs et un fichier lié à l'ESP32 (TTGO-T5). La configuration du **matériel**, numéro des pins, adresses des cartes ou de la mémoire se trouvent dans ces fichiers. Chaque option est documentée par des commentaires directement à l'intérieur de ce fichier, lisez-les attentivement.

Pour "commenter" une ligne ajouter "//" au début. Cela désactive l'option.


2) La configuration logiciel
--------------------------------------

Il existe 2 méthodes pour configurer votre variomètre avec vos paramètres personnels

a) Le fichier SETTINGS.TXT sur la carte SD

Le fichier SETTINGS.TXT doit être placé à la racine de la carte SD. Ce fichier contient l'ensemble des paramètres utilisateurs permettant de personnaliser le fonctionnement du GnuVario-ESP32
Chaque paramètre est encadré de crochets et la valeur se trouve après le signe =. Il est impératif de conserver la syntaxe de ce fichier. Ce fichier peut être modifié sans recompilation du code.

[SETTINGS.TXT](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/Gnuvario-E/SETTINGS.TXT)

b) Le fichier VarioSettings.h

Si vous ne souhaitez pas utiliser de carte SD, vous pouvez modifier le fichier libraries/VarioSettings/VarioSettings.h afin de personnaliser votre vario. L'utilisation de ce fichier nécessite la recompilation du code

[libraries/VarioSettings/VarioSettings.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/VarioSettings/VarioSettings.h)


3) Enregistrez vos informations personnelles
----------------------------------

Certains paramètres particuliers doivent être renseignés. Ces paramètres sont vos informations personnelles. 

Ainsi, dans *SETTINGS.TXT*, définissez votre **Nom du pilote** et **Nom de la voile**.


4) Si nécessaire, calibrez l'accéléromètre
----------------------------------------

Si vous intégrez un accéléromètre, vous devez le calibrer.

D'abord sous Windows ou Mac, installez [Python version 2] (https://www.python.org/). Sous Windows, assurez-vous de cocher l'option **add to PATH variable**.

Ensuite, compilez et téléchargez le schéma **calibration_recorder_ESP32**. Assurez-vous que votre carte SD est à l'intérieur du variomètre. Et suivez cette procédure:

<iframe width="560" height="315" src="https://www.youtube.com/embed/6yxoZcxxzVY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Cela créera un fichier "RECORD**.IGC" sur la carte SD. Copiez ce fichier dans le dossier "best-fit-calibration" et renommez-le si nécessaire en tant que "RECORD00.IGC".

Sous Windows ou Mac, lancez l'**Idle** Python et ouvrez le programme "best-fit-calibrage/calibrer.py". Appuyez sur "F5" pour exécuter.

Sous Linux, lancez simplement :

{% highlight shell_session %}
~$ cd Arduino/best-fit-calibration
~/best-fit-calibration$ python2 calibrate.py
{% endhighlight %}

Cela montrera les paramètres que vous devez remplacer dans votre fichier *HardwareConfig.h*.

5) Liste des paramètres personnalisables
-----------------------------

Disponible dans le fichier *SETTINGS.TXT*, il est possible de personnaliser le fonctionnement du GnuVario.

Voici les paramètres modifiables les plus importants et leurs descriptions

[VARIOMETER_BEEP_VOLUME]
Volume des Bips, valeur entre 0 et 10, 10 étant le volume maximum

[VARIOMETER_TIME_ZONE] 
Definit la zone horaire UTC (+2) en été (+1) en hiver 

[VARIOMETER_SINKING_THRESHOLD] 
Seuil de descente

[VARIOMETER_CLIMBING_THRESHOLD] 
Seuil de zérotage

[VARIOMETER_NEAR_CLIMBING_SENSITIVITY]
Seuil de montée

[VARIOMETER_ENABLE_NEAR_CLIMBING_ALARM]
Alarme de montée proche: signale que vous entrez ou sortez de la zone de montée proche

[VARIOMETER_ENABLE_NEAR_CLIMBING_BEEP]
Bip de zérotage: bip lorsque vous êtes dans une zone comprise entre VARIOMETER_CLIMBING_THRESHOLD et VARIOMETER_NEAR_CLIMBING_SENSITIVITY

[VARIOMETER_BASE_PAGE_DURATION] 
Temps d'affichage de la page principale (en millisecondes)

[VARIOMETER_ALTERNATE_PAGE_DURATION] 
Temps d'affichage de la page secondaire (en millisecondes)

[FLIGHT_START_VARIO_LOW_THRESHOLD]
[FLIGHT_START_VARIO_HIGH_THRESHOLD]
Vitesse verticale minimale en m / s (seuil bas / haut) permettant le déclenchement de l'enregistrement

[FLIGHT_START_MIN_SPEED]
Vitesse au sol minimale en km/h déclenchant l'enregistrement du vol

[VARIOMETER_RECORD_WHEN_FLIGHT_START]
Activée, cette option indique que l'enregistrement débutera quand le vol débutera (vitesse horizontale supérieure à FLIGHT_START_MIN_SPEED et vitesse horizontale inférieure à FLIGHT_START_VARIO_LOW_THRESHOLD ou supérieure à FLIGHT_START_VARIO_HIGH_THRESHOLD  

[ALARM_SDCARD}
Alarme de non présence de la carte SD

[ALARM_GPSFIX]
Bip indiquant que le GPS est opérationnel

[ALARM_FLYBEGIN]
Bip indiquant le début de l'enregistrement du vol

[VARIOMETER_DISPLAY_INTEGRATED_CLIMB_RATE]
Affichage du taux de chute moyen sur une période ou du taux de chute instantané si l'option n'est pas active

[VARIOMETER_INTEGRATION_TIME]
durée de l'intégration pour le calcul du taux de chute

[VARIOMETER_INTEGRATION_DISPLAY_FREQ]
fréquence d'affichage du taux de chute

[RATIO_CLIMB_RATE]
		1: Affichage de la finesse
		2: Affichage du taux de chute moyen
		3: Affichage des 2 informations en alternance dans la zone à droite de l'affiche du vario

6) Configuration taux de chute moyen
-----------------------------

Si vous souhaitez utiliser l'affichage du taux de chute moyen, suivez cette procèdure

Avec le taux de chute "moyenné" sur une periode, vous pouvez garder les bips très réactifs mais afficher à l'écran votre bilan sur 5 secondes au plus.

Voici la procédure :

    a) Il vous faut la période de votre GPS 
		  ( même si c'est sûrement 1000 ms ). Chargez le sketch "gps-time-analysis_ESP32" puis attendez le fix. Lorsque le GPS s'est bien stabilisé lisez le chiffre en deuxième position à l'écran. C'est la période du GPS.

    b) Dans HardwareConfig.h entrez votre periode du GPS :

    #define GPS_PERIOD 996 

	c) Si vous voulez un affichage du taux de chute intégré décommentez :

		#define VARIOMETER_DISPLAY_INTEGRATED_CLIMB_RATE

	d) Vous pouvez alors régler la durée de l'intégration 
	    ( ici 5s ) et la fréquence d'affichage ( ici 2 affichage par secondes )

		#define VARIOMETER_INTEGRATION_TIME 5000
		#define VARIOMETER_INTEGRATION_DISPLAY_FREQ 2.0

	Ces paramètres sont aussi utilisés pour la finesse.

	e) Si vous voulez afficher le taux de chute en alternance avec la finesse

		#define RATIO_CLIMB_RATE 2

		1: Affichage de la finesse
		2: Affichage du taux de chute moyen
		3: Affichage des 2 informations en alternance 


7) Téléverser le code du variomètre
-----------------------------

Après avoir copié le fichier *SETTINGS.TXT* sur la carte SD. 

Vous pouvez compiler et téléverser le schéma *GnuVario-E.ino*.

Vous avez terminé !















