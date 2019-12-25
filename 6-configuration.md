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

Normalement, vous ne devriez avoir à adapter que le type d'écran, si vous utiliser un écran de taille différente de 1.54" : c'est la directive **VARIOSCREEN_SIZE** dans le fichier HardwareConfig.h.


2) La configuration logiciel
--------------------------------------

Il existe 3 méthodes pour configurer votre variomètre avec vos paramètres personnels

a) La page Web

Le plus simple pour configurer votre GnuVario-E est d'utiliser la page web embarquée et le mode Wifi.  
Ceci va mettre à jour automatiquement les fichiers de configuration sur la sdcard.
Cette fonctionnalitée est décrite dans le [manuel d'utilisation]({{ site.baseurl }}{% link 7-manuel.md %}).

b) Les fichiers de configuration sur la carte SD.

Ces fichiers se trouvent à la racine de la carte SD ; ils sont décrits plus en détail en bas de cette page.  
Ils permettent de configurer le GNUVario sans avoir à recompiler le code.
- params.jso : contient les paramètres généraux du GNUVario.
- wifi.cfg : contient les informations de connexion au réseau wifi ; on peut déclarer jusqu'à 4 réseaux wifi différents.
- variocal.cfg : contient les informations de calibration du GNUVario. Voir le [manuel d'utilisation]({{ site.baseurl }}{% link 7-manuel.md %}) pour l'opération de calibration.

c) Le fichier VarioSettings.h

Cette méthode est réservée aux utilisateurs confirmés qui souhaite utiliser du matériel non standard ou recompiler le code

Si vous ne souhaitez pas utiliser de carte SD, vous pouvez modifier le fichier libraries/VarioSettings/VarioSettings.h afin de personnaliser votre vario. L'utilisation de ce fichier nécessite la recompilation du code

[libraries/VarioSettings/VarioSettings.h](https://github.com/jpg63/Gnuvario_for_TTGO-T5/blob/master/Sources/Stable%20Code/libraries/VarioSettings/VarioSettings.h)

3) Liste des paramètres personnalisables
-----------------------------
### params.jso #

C'est un fichier au format json, qui permet de personnaliser le fonctionnement du GnuVario.

Les principaux paramètres de ce fichier sont les suivants :

**systeme - MULTIDISPLAY_DURATION**    
défaut : 2000 millisecondes    
Temps d'affichage des différentes pages (en millisecondes)

**general - TIME_ZONE**    
Definit la zone horaire UTC : (+2) en été (+1) en hiver 

**general - PILOT_NAME**   
Nom du pilote 

**general - GLIDER_NAMEx**  
x de 1 à 4 : Permet de saisir 4 noms de voiles

**general - GLIDER_SELECT**  
Permet de choisir 1 voile, parmi les 4 possibles

**vario - SINKING_THRESHOLD**    
défaut : -2.0   
Seuil de déclenchement des dégueulantes 

**vario - CLIMBING_THRESHOLD**         
défaut : 0.2        
Seuil de déclenchement du zérotage    

**vario - NEAR_CLIMBING_SENSITIVITY**  
défaut : 0.5   
Zone de zérotage    

de -10 à -2.0 son grave de dégeulante    
de -2.0 à 0.2 pas de son      
de 0.2 à 0.5 bip de zérotage    
de 0.5 à 10 bip de montée      

**vario - ENABLE_NEAR_CLIMBING_ALARM**
défaut : 0       
1 = Alarme de montée proche: signale que vous entrez ou sortez de la zone de montée proche

**vario - ENABLE_NEAR_CLIMBING_BEEP**    
défaut : 0         
1 = Bip de zérotage: bip lorsque vous êtes dans une zone comprise entre VARIOMETER_CLIMBING_THRESHOLD et VARIOMETER_NEAR_CLIMBING_SENSITIVITY

**vario - DISPLAY_INTEGRATED_CLIMB_RATE**     
défaut : 0     
1 = Affichage du taux de chute moyen sur une période     
0 = Affichage du taux de chute instantané 

**vario - CLIMB_PERIOD_COUNT**     
défaut : 10     
durée de l'intégration pour le calcul du taux de chute

**vario - SETTINGS_GLIDE_RATIO_PERIOD_COUNT**     
défaut : 20    
fréquence d'affichage du taux de chute

**vario - RATIO_CLIMB_RATE**    
défaut : 2     
1 = Affichage de la finesse     
2 = Affichage du taux de chute moyen     
3 = Affichage des 2 informations en alternance dans la zone à droite de l'affiche du vario

**vario - RATIO_MAX_VALUE**     
défaut : 30.0    
valeur max utilisée dans le calcul du taux de chute

**vario - RATIO_MIN_SPEED**    
défaut : 10.0    
valeur minimum de vitesse utilisée dans le calcul du taux de chute

**vario - SENT_LXNAV_SENTENCE**     
défaut : 1  
Format de la transmition BT      
1 = LXNAV     
0 = LK8000

**flightstart - FLIGHT_START_MIN_TIMESTAMP**    
défaut : 15000 millisecondes            
Temps minimum entre le début du vol et le démarrage en millisecondes

**flightstart - FLIGHT_START_VARIO_LOW_THRESHOLD**  
défaut : 0.5         
**flightstart - FLIGHT_START_VARIO_HIGH_THRESHOLD**  
défaut : 0.5       
Vitesse verticale minimale en m / s (seuil bas / haut) permettant le déclenchement de l'enregistrement

**flightstart - FLIGHT_START_MIN_SPEED**   
défaut : 8 km/h       
Vitesse au sol minimale en km/h déclenchant l'enregistrement du vol

**flightstart - VARIOMETER_RECORD_WHEN_FLIGHT_START**     
défaut : 1      
0 = desactivée, l'enregistrement débute des que le GPS est opérationel    
1 = Activée, l'enregistrement débutera à la détection du début de vol (vitesse horizontale supérieure à FLIGHT_START_MIN_SPEED et vitesse horizontale inférieure à FLIGHT_START_VARIO_LOW_THRESHOLD ou supérieure à FLIGHT_START_VARIO_HIGH_THRESHOLD  

**systeme - SLEEP_TIMEOUT_MINUTES**   
défaut : 20 minutes     
mise en veille après X minutes d'inactivité

**systeme - SLEEP_THRESHOLD_CPS**    
défaut : 0.5 m       
seuil de déclenchement d'activité (équivalent à +0.5 Vz)

**systeme - ALARM_SDCARD**     
1 = Bip d'alarme indiquant que la carte SD n'est pas présente

**systeme - ALARM_GPSFIX**    
1 = Bip indiquant que le GPS est opérationnel

**systeme - ALARM_FLYBEGIN**     
1 = Bip indiquant le début de l'enregistrement du vol

**systeme - NO_RECORD**     
défaut : 0    
1 = désactivation de l'enregistrement sur la SDcard

**systeme - BT_ENABLE**    
défaut : 0    
1 = Bluetooth activé 

**systeme - COMPENSATION_TEMP**     
défaut : -6      
compensation de la température 

**systeme - COMPENSATION_GPSALTI**      
défaut : -30     
compensation de l'altitude du Gps 

### wifi.cfg #

Ce fichier contient les paramètres de connexion au wifi.   
On peut paramétrer jusqu'à 4 réseaux wifi   

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

### variocal.cfg #

Ce fichier contient les valeurs de calibration du GNUVario.

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















