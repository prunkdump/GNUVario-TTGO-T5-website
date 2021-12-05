---
step: 3
description: Première mise à jour
---

Avant de pouvoir utiliser le Gnuvario-E vous devez installer le logiciel et préparer la carte SD

### Préparation de la carte SD #
Sur une carte MicroSD vierge formatée en Fat16 ou 32, copier le contenu du dossier RootSD à la racine de la carte SD .   

### Mise à jour du Gnuvario-E #   
Avant de mettre à jour le vario vous devez télécharger et installer l'outil flash download tools d'espressif

Flash Download Tools : <https://www.espressif.com/en/support/download/other-tools>

Démarrez le Gnuvario-E sans la carte SD ; **puis** connectez-le au PC par le port usb. Le PC va voir le vario comme un port Série ; par exemple, COM3.

Exécutez flash_download_tools.exe ; choisir l'option 'ESP32 DownloadTool'.

Choisir ensuite le dernier fichier .bin, en utilisant les paramètres suivants (choisir le port COM correspondant au vario) :

![Flash_download_tools]({{ '/assets/manuel_img/flashTools.jpg' | relative_url }})

Saisissez la valeur 0x10000 après le fichier .bin

Appuyez sur le bouton Start ; le carré vert 'IDLE' indique alors 'Download', et une barre de progression verte s'affiche en bas de l'utilitaire.  
L'écriture du logiciel prend environ 2mn ; lorsque terminé, le carré vert affiche 'FINISH'.

Vous pouvez alors couper l'alimentation du Gnuvario-E, débrancher le port usb, insérer la sdcard et redémarrer le vario.
