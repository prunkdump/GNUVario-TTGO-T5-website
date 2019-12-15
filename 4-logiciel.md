---
layout: page
title: Logiciel
linkdesc: Le logiciel du GNUVario
linkmsg: Trouver !
linktarget: "/assets/fichiers/Gnuvario-E.zip"
---

**Firmware**      
      
Il existe plusieurs versions du firmware du GNUVARIO-E :   

Version pour écran 1,54''     

la version Stable : [0.5]({{ 'assets/fichiers/firmware154/Beta/Gnuvario-E.ino.esp32.bin' | relative_url }})    
la version de Développement : [0.6 beta 7]({{ 'assets/fichiers/firmware154/Stable/Gnuvario-E.ino.esp32.bin' | relative_url }})  

Version pour écran 2.90''    

la version Stable : [0.5]({{ 'assets/fichiers/firmware290/Beta/Gnuvario-E.ino.esp32.bin' | relative_url }})    
la version de Développement : [0.6 beta 4]({{ 'assets/fichiers/firmware290/Stable/Gnuvario-E.ino.esp32.bin' | relative_url }})  

**Site Web Embarqué**     

RootSD pour la version [Stable 0.5 du Firmware]({{ 'assets/fichiers/RootSD/Stable/RootSD.zip' | relative_url }})    
RootSD pour la version [Beta 0.6b7 du Firmware]({{  'assets/fichiers/RootSD/Beta/RootSD.zip' | relative_url }})     

**Les Fonctionnalités**    
		
Version 0.6  		
- Vario précis avec capteur de pression et accéleromètres   
- GPS   
- Enregistrement des vols sur carte SD   
- Affichage sur écran E-Ink   
- Affichage du vario, de l'altitude, de la vitesse sol, de l'heure, du temps de vol, ...
- Paramètre utilisateur dans plusieurs fichiers au format texte et json                       
- Coupure du son via le bouton central (en vol)                          
- Statistiques de Vol                                                   
- taux de chute et finesse                                              
- indicateur de montée/descente   
- Désactiver l'enregistrement des vols   		
- Mise à jour via la carte SD (update.bin)                             
- Récupération des vol via Wifi                                         
- Mise à jour via Wifi                                                  
- Upload / download de fichiers via Wifi                         
- Multi-écran (navigation avec les boutons droit et gauche)    
- Affichage de la température          
- Page de configuration du volume sonore    
- Page de statistique accessible via les boutons    	
- Mise en veille automatique en cas de batterie trop faible  
- Mise en veille automatique en cas d'inactivité          
- Mise en veille prolongée par bouton                                             
- Page de calibration                                                   
- Ajout gestion de l'écran 2.9''                               
- Ajout du serveur Web sur SDCARD                                       
- Ajout de titre au dessus des champs de données                        
- Ajout de nouveau objects screen - ligne - rose des vents               
- Ajout compensation de température
- Ajout correction d'altitude GPS 
- Paramètres utilisateur modifiable via une pas web en wifi
		
**L'historique du logiciel**

| version | beta    | date     | Description                                              |
|---------|---------|:---------:|---------------------------------------------------------|
| v0.6    | 7       | 17/11/19 | Mise à jour ecran 2.9''                                  |
|         |         |          | Mise à jour fichier params.jso                           |
|         |         |          | Mise à jour page web                                     |
|         |         |          | Correction Bug serveurWeb                                |
|         |         |          | Correction Bug deep sleep                                |
|         |         |          | Ajout TRACE (Debbuger)                                   |
|         |         |          | Ajout Mode veille paramètrable                           |
|         |         |          | Ajout Passage en veille en cas d'inactivité              |
| v 0.6   | 6       | 11/11/19 | plusieurs fichiers de configurations / params.jso        |
|         |         |          | variocal.cfg, wifi.cfg                                   |
|         |         |          | Ajout gestion des versions params.jso automatique /      |
|         |         |          | création automatique des champs avec recup des données   |
|         |         |          | Correction bug volume                                    |
|         |         |          | AJOUT - dans params.jso - MULTIDISPLAY_DURATION et       |
|         |         |          | plusieurs voiles                                         |
| v 0.6   | 5       | 03/11/19 | Déplacement validation deep-sleep sur bouton gauche      |
|         |         |          | Corrections mineures sur varioscreen 2.9''               |
|         |         |          | Corrections mineures sur varioscreen 1.54''              |  
|         |         |          | Amélioration de la gestion de la première mesure d'altit.|
|         |         |          | Correction du bug de l'écran qui fige                    |
|         |         |          | Moyenne alti Gps sur 15 mesures avant calibration baro   |
|v 0.6    |  4      | 27/10/19 | Correction gestion zone horaire                          |
|         |         |          | Changement de librairie MS5611 et MPU                    |
|         |         |          | Ajout compensation alti gps                              |
|         |         |          | Ajout d'un bip lors du réglage du volume                 |
|         |         |          | Amélioration gestion des boutons et des écrans au boot   |
|         |         |          | Correction gestion du volume                             |
|         |         |          | Correction gestion du volume                             |
|         |         |          | Correction Calibration enableAmp                         |
|         |         |          | Correction du bug d'affichage de l'écran de stat         |
|         |         |          | Correction du bug d'affichage de l'écran de stat         |
|         |         |          | Correction du bug de reboot / blocage si #define DEBUG_PRO est commenté          |
|         |         |          |                                                          |
| v 0.6   |  3      | 20/10/19 | Correction bug enregistrement sur la SD                  |
|         |         |          | recodage de l'affichage des satellites                   |
|         |         |          | Ajout désactivation bip au démarrage                     |
|         |         |          | Ajout compensation de température et correction altitude GPS dans le fichier SETTINGS.TXT |
|         |         |          |                                                          |
| v 0.6   |  2      | 06/10/19 | Ajout varioscreen pour l'écran 2.9''                     |
|         |         |          | Ajout serveur Web sur sdcard                             |
|         |         |          | Correction du bug d'affichage des flèches                |
|         |         |          | Ajout du nom des champs de données sur l'écran           |
|         |         |          | Couper le SSID à 12 caractères                           |
|         |         |          | Modification du fichier SETTINGS.TXT v1.4                |
|         |         |          | Ajout paramètre d'activation du BT dans le fichier SETTINGS.TXT |
|         |         |          | Modification de varioscreen pour gérer les lignes et les cercles |
|         |         |          | ainsi que les titres des champs de données                |
|         |         |          | Modification de l'arborescence de la carte SD            |
|         |         |          | Enregistrement des fichiers .IGC (traces) dans le dossier 'vols' |
|         |         |          | Mise à jour Ecran 2,9''                                  |
|         |         |          | Modifier l'affichage des titres pour que la position soit liée au digit                            |
|         |         |          |                                                          |
| v 0.6   |  1      | 26/09/19 | Ajout mise en sommeil                                    |
|         |         |          | Flash via USB en utilisant flash_download_tools          |
|         |         |          | Ajout écran calibration                                  |
|         |         |          | Modification SETTING.TXT (Version 1.3)                   |
|         |         |          | Correction HAVE_SDCARD                                   |
|         |         |          | Changement de la librairie webserver                     |
|         |         |          |                                                          |
| v 0.5   |  9      | 23/09/19 | Correction affichage écran Stat                          |
|         |         |          | Ajout possibilité d'avoir plusieurs tailles d'écran      |
|         |         |          | Deep-sleep sur bouton central (3 sec)                    |
|         |         |          |                                                          |
| v 0.5   |  8      | 22/09/19 | Modification de l'affichage de Vbat                      |
|         |         |          | Ajout d'un filtrage de la mesure de Vbat                 |
|         |         |          |                                                          |
| v 0.5   |  7      | 10/09/19 | Ajout choix des pin SDA, SCL                             |
|         |         |          | Modification des librairies du MPU9250 / ajout fonctions de Calibration                            |
|         |         |          | Modification de la séquence de démarrage - allongement du temps de l'écran de stat à 6 sec         |
|         |         |          | init MS5611 avant écran stat, ajout acquisition durant écran stat et init kalman après             |
|         |         |          | Ajout d'un paramètre de nombre d'acquisition du GPS avant la mise à jour de Altitude Barométrique |
|         |         |          | Modification librairie EEPROM                            |
|         |         |          |                                                          |
| v 0.5   |  6      | 04/09/19 | Changement librairies MS5611 et MPU9250                  |
|         |         |          | Modification de la calibration de l'altitude par le GPS  |
|         |         |          | Ajout d'un coefficient de compensation de température     |
|         |         |          | Modification de la séquence de démarrage de l'enregistrement |
|         |         |          |                                                          |

**Les futurs développements**

 V0.4                                                                                                                                                 																												
 BUG - affichage finesse     
 
 V0.5                                                                    
 BUG   - voir réactivité des données GPS                                                                        
 BUG   - Problème consommation - SDcard - deep sleep                                                           
                                                                                                     
 v0.6                                                                                                      
 AJOUT - Calibration MPU                                                                                                                 
 MODIF - Refaire gestion Eeprom avec préférence                                                         
 BUG   - affichage figé / problème d'init du MPU et d'attente de la première lecture                    
 BUG   - reboot à l'init du MPU    
 BUG   - blocage MPU - plus de valeur valide ou décalage des mesures dans le temps      
 BUG   - temperature     
 BUG   - DISPLAY_OBJECT_LINE object ligne ne fonctionne pas        
 BUG   - Alti erreur - si on ne valide pas le deep sleep                
 BUG   - Norcissement de l'écran       

 v0.7        
 BUG   - UpdateSD ne marche plus - passage à sdfat     
 BUG   - upload et update via wifi ne marche plus
 AJOUT - Maj via Internet         
 AJOUT - Créer une bibliothèque de log (debug)  avec fichier de log              
	
 VX.X                                                                                                
 AJOUT - Paramètrage des écrans                                                                                 
 MODIF - Gérer le son via le DAC                                                                                
 MODIF - revoir gestion du volume du son ToneESP32                                                                         
 AJOUT - Refaire gestion du son (paramétrage via xctracer)                                                      
 AJOUT - Ecran position afficher les coordonnées GPS, la boussole, et l'altitude                                                                                                        *
 MODIF - Création dynamique des objets screen                                                                
 AJOUT - Créer une bibliothèque de log (debug)                                                               
 AJOUT - Sens et vitesse du vent                                                                             
 AJOUT - Carnet de vol                      
 BUG   - vérifier fonctionnement BT                                                                               
 AJOUT - Récupération vol via USB                





