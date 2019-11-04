---
layout: page
title: Configuration
---

La configuration du variomètre est séparée en 2 parties.

1) La configuration matérielle
--------------------------------------

Cette partie est uniquement nécéssaire si vous souhaitez utiliser du matériel non standard pour réaliser votre GnuVario-E

Avant de configurer la partie matériel, vous devez savoir comment [compiler le code]({{ site.baseurl }}{% link 5-code.md %}). Assurez-vous de bien connaître l'IDE Arduino.

La configuration liée au matériel se fait en éditant les fichiers [libraries/HardwareConfig/HardwareConfig.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/HardwareConfig/HardwareConfig.h) et [libraries/HardwareConfig/HardwareConfigESP32.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/HardwareConfig/HardwareConfigESP32.h) dans votre dossier Arduino. Si vous n'avez pas d'éditeur adapté à l'écriture de code, vous pouvez le télécharger [Notepad++](https://notepad-plus-plus.org/).

Commencez par vérifier les fichiers. Il y a un fichier commun à tous les microcontroleurs et un fichier lié à l'ESP32 (TTGO-T5). La configuration du **matériel**, numéro des pins, adresses des cartes ou de la mémoire se trouvent dans ces fichiers. Chaque option est documentée par des commentaires directement à l'intérieur de ce fichier, lisez-les attentivement.

Pour "commenter" une ligne ajouter "//" au début. Cela désactive l'option.


2) La configuration logiciel
--------------------------------------

Il existe 3 méthodes pour configurer votre variomètre avec vos paramètres personnels

a) La page Web

Le plus simple pour configurer votre GnuVario-E est d'utiliser la page web embarquée et le mode Wifi
Cette fonctionnalitée est décrite dans le manuel d'utilisation

b) Le fichier SETTINGS.TXT sur la carte SD

Le fichier SETTINGS.TXT doit être placé à la racine de la carte SD. Ce fichier contient l'ensemble des paramètres utilisateurs permettant de personnaliser le fonctionnement du GnuVario-ESP32
Chaque paramètre est encadré de crochets et la valeur se trouve après le signe =. Il est impératif de conserver la syntaxe de ce fichier. Ce fichier peut être modifié sans recompilation du code.

[SETTINGS.TXT](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/Gnuvario-E/SETTINGS.TXT)

c) Le fichier VarioSettings.h

Cette méthode est réservée aux utilisateurs confirmés qui souhaite utiliser du matériel non standard ou recompiler le code

Si vous ne souhaitez pas utiliser de carte SD, vous pouvez modifier le fichier libraries/VarioSettings/VarioSettings.h afin de personnaliser votre vario. L'utilisation de ce fichier nécessite la recompilation du code

[libraries/VarioSettings/VarioSettings.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/VarioSettings/VarioSettings.h)

3) Liste des paramètres personnalisables
-----------------------------

Disponible dans le fichier *SETTINGS.TXT*, il est possible de personnaliser le fonctionnement du GnuVario.

Voici les paramètres modifiables les plus importants et leurs descriptions

**VARIOMETER_PILOT_NAME**   
Nom du pilote 

**VARIOMETER_GLIDER_NAME**    
Nom de la voile

**VARIOMETER_TIME_ZONE**    
Definit la zone horaire UTC (+2) en été (+1) en hiver 

**VARIOMETER_BEEP_VOLUME**   
Défaut : 8   
Volume des Bips par défaut, valeur entre 0 et 10, 10 étant le volume maximum

**VARIOMETER_BASE_PAGE_DURATION**    
défaut : 3000 millisecondes    
Temps d'affichage de la page principale (en millisecondes)

**VARIOMETER_ALTERNATE_PAGE_DURATION**    
défaut : 3000   
Temps d'affichage de la page secondaire (en millisecondes)

**VARIOMETER_SINKING_THRESHOLD**    
défaut : -2.0   
Seuil de déclenchement des dégueulantes 

**VARIOMETER_CLIMBING_THRESHOLD**         
défaut : 0.2        
Seuil de déclenchement du zérotage    

**VARIOMETER_NEAR_CLIMBING_SENSITIVITY**  
défaut : 0.5   
Zone de zérotage    

de -10 à -2.0 son grave de dégeulante    
de -2.0 à 0.2 pas de son      
de 0.2 à 0.5 bip de zérotage    
de 0.5 à 10 bip de montée      

**VARIOMETER_ENABLE_NEAR_CLIMBING_ALARM**
défaut : 0       
1 = Alarme de montée proche: signale que vous entrez ou sortez de la zone de montée proche

**VARIOMETER_ENABLE_NEAR_CLIMBING_BEEP**    
défaut : 0         
1 = Bip de zérotage: bip lorsque vous êtes dans une zone comprise entre VARIOMETER_CLIMBING_THRESHOLD et VARIOMETER_NEAR_CLIMBING_SENSITIVITY

**FLIGHT_START_MIN_TIMESTAMP**    
défaut : 15000 millisecondes            
Temps minimum entre le début du vol et le démarrage en millisecondes

**FLIGHT_START_VARIO_LOW_THRESHOLD**  
défaut : 0.5         
**FLIGHT_START_VARIO_HIGH_THRESHOLD** 
défaut : 0.5       
Vitesse verticale minimale en m / s (seuil bas / haut) permettant le déclenchement de l'enregistrement

**FLIGHT_START_MIN_SPEED**   
défaut : 8 km/h       
Vitesse au sol minimale en km/h déclenchant l'enregistrement du vol

**VARIOMETER_RECORD_WHEN_FLIGHT_START**     
défaut : 1      
0 = desactivée, l'enregistrement débute des que le GPS est opérationel    
1 = Activée, l'enregistrement débutera à la détection du début de vol (vitesse horizontale supérieure à FLIGHT_START_MIN_SPEED et vitesse horizontale inférieure à FLIGHT_START_VARIO_LOW_THRESHOLD ou supérieure à FLIGHT_START_VARIO_HIGH_THRESHOLD  

**VARIOMETER_DISPLAY_INTEGRATED_CLIMB_RATE**     
défaut : 0     
1 = Affichage du taux de chute moyen sur une période     
0 = Affichage du taux de chute instantané 

**VARIOMETER_INTEGRATION_TIME**     
défaut : 10     
durée de l'intégration pour le calcul du taux de chute

**VARIOMETER_INTEGRATION_DISPLAY_FREQ**     
défaut : 20    
fréquence d'affichage du taux de chute

**RATIO_CLIMB_RATE**    
défaut : 2     
1 = Affichage de la finesse     
2 = Affichage du taux de chute moyen     
3 = Affichage des 2 informations en alternance dans la zone à droite de l'affiche du vario

**RATIO_MAX_VALUE**     
défaut : 30.0    
valeur max utilisée dans le calcul du taux de chute

**RATIO_MIN_SPEED**    
défaut : 10.0    
valeur minimum de vitesse utilisée dans le calcul du taux de chute

**VARIOMETER_SENT_LXNAV_SENTENCE**     
défaut : 1  
Format de la transmition BT      
1 = LXNAV     
0 = LK8000

**SLEEP_TIMEOUT_SECONDS**   
défaut : 1200 sec soit  20 minutes     
mise en veille après X sec d'inactivité

**SLEEP_THRESHOLD_CPS**    
défaut : 50 cms       
seuil de déclenchement d'activité

**ALARM_SDCARD**     
1 = Bip d'alarme indiquant que la carte SD n'est pas présente

**ALARM_GPSFIX**    
1 = Bip indiquant que le GPS est opérationnel

**ALARM_FLYBEGIN**     
1 = Bip indiquant le début de l'enregistrement du vol

**NO_RECORD**     
défaut : 0    
1 = désactivation de l'enregistrement sur la SDcard

**valeurs de calibration**    

**VERTACCEL_GYRO_CAL_BIAS_00**   
défaut : 0x00       
**VERTACCEL_GYRO_CAL_BIAS_01**    
défaut : 0x00       
**VERTACCEL_GYRO_CAL_BIAS_02**     
défaut : 0x00       
**VERTACCEL_GYRO_CAL_BIAS_03**  
défaut : 0x00     
**VERTACCEL_GYRO_CAL_BIAS_04**   
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_05**   
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_06**   
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_07**    
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_08**    
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_09**    
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_10**    
défaut : 0x00      
**VERTACCEL_GYRO_CAL_BIAS_11**    
défaut : 0x00      
**VERTACCEL_ACCEL_CAL_BIAS_00**   
défaut : 0x00      
**VERTACCEL_ACCEL_CAL_BIAS_01**    
défaut : 0x00      
**VERTACCEL_ACCEL_CAL_BIAS_02**   
défaut : 0x00      
**VERTACCEL_ACCEL_CAL_SCALE**   
défaut : 0    
**VERTACCEL_MAG_CAL_BIAS_00**   
défaut : 0    
**VERTACCEL_MAG_CAL_BIAS_01**    
défaut : 0    
**VERTACCEL_MAG_CAL_BIAS_02**    
défaut : 0    
**VERTACCEL_MAG_CAL_PROJ_SCALE**   
défaut : 15535    
**VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER**   
défaut : 5     
**VERTACCEL_MAG_CAL_BIAS_MULTIPLIER**    
défaut : 5     

**Parametres Wifi**    

**SSID_1**
défaut : your_SSID1       
SSID du premier réseau Wifi

**PASSWORD_1**   
défaut : your_PASSWORD_for SSID1     
Mot de passe du premier réseau Wifi    

**SSID_2**    
**PASSWORD_2**   

**SSID_3**   
**PASSWORD_3**   

**SSID_4**   
**PASSWORD_4**   

**BT_ENABLE**    
défaut : 0    
1 = Bluetooth activé 

**COMPENSATION_TEMP**     
défaut : -6      
compensation de la température 

**COMPENSATION_GPSALTI**      
défaut : -30     
compensation de l'altitude du Gps 


4) Configuration taux de chute moyen
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
















