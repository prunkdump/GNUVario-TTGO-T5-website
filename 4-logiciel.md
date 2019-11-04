---
layout: page
title: Logiciel
linkdesc: Le logiciel du GNUVario
linkmsg: Trouver !
linktarget: "/assets/fichiers/Gnuvario-E.zip"
---

Il existe deux versions du logiciel du GNUVARIO-E :

la version Stable : [0.5]({{ '/assets/fichiers/Gnuvario-E.zip' | relative_url }})    
la version de Développement : [0.6 beta 4]({{ '/assets/fichiers/Gnuvario-E_Beta.zip' | relative_url }})    

**Les Fonctionnalités**    
		
Version 0  		
- Vario précis avec capteur de pression et accéleromètres   
- GPS   
- Enregistrement des vols sur carte SD   
- Affichage sur écran E-Ink   
- Affichage du vario, de l'altitude, de la vitesse sol, de l'heure, du temps de vol, ...
                                                                       
Version 0.3                                                                                                                                   
- Paramètre utilisateur dans fichier SETTINGS.TXT                        
- Coupure du son via le bouton central (en vol)                          
                                                                       
Version 0.4                                                             
- Statistiques de Vol                                                   
- taux de chute et finesse                                              
- indicateur de montée/descente   
- Désactiver l'enregistrement des vols   		
                                                                       
Version 0.5                                                               
- Mise à jour via la carte SD (update.bin)                             
- Récupération des vol via Wifi                                         
- Mise à jour via Wifi                                                  
- Upload des fichiers de configuration via Wifi                         
- Ajout Bluetooth                                                       
- Multi-écran (ajout 2ème page / gestion des boutons droit et gauche)    
- Affichage de la température          
- Page de configuration du volume sonore    
- Page de statistique accessible via les boutons    	
- Mise en veille automatique en cas de batterie trop faible            
                                                                      
Version 0.6                                                             
- Page de calibration                                                   
- Mise en veille prolongée                                               
- Ajout gestion de l'écran 2.9''                               
- Ajout du serveur Web sur SDCARD                                       
- Activation du Bluetooth en paramètre dans le fichier SETTINGS.TXT     
- Ajout de titre au dessus des champs de données                        
- Ajout de nouveau objects screen - ligne - rose des vents               
- Modification de l'organisation des fichiers sur la carte SD           
- Ajout compensation de température dans fichier SETTINGS.TXT           
- Ajout correction d'altitude GPS dans SETTINGS.TXT                      		
		
**L'historique du logiciel**

| version | beta    | date     | Description                                              |
|---------|---------|:---------:|---------------------------------------------------------|
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
 AJOUT - page web de configuration du vario / Page Web SDCARD                                           
 MODIF - Refaire gestion Eeprom avec préférence                                                         
 AJOUT - gestion du MPU par Interruption                                                                
 BUG   - affichage figé / problème d'init du MPU et d'attente de la première lecture                    
 BUG   - reboot à l'init du MPU                                                                      
                                                                                                                                                           
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





