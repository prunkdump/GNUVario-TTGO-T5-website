---
step: 3
description: Premier Démarrage
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

Appuyez sur le bouton Start ; le carré vert 'IDLE' indique alors 'Download', et une barre de progression verte s'affiche en bas de l'utilitaire.  
L'écriture du logiciel prend environ 2mn ; lorsquelle est terminée, le carré vert affiche 'FINISH'.

Vous pouvez alors couper l'alimentation du Gnuvario-E, débrancher le port usb, insérer la sdcard et redémarrer le vario.

**ATTENTION**

Si vous avez compilé le code source avec PlatformIO au lieu de l'IDE Arduino, il est nécessaire d'ajouter la table de partition en 0x8000 que vous trouverez dans votre dossier de compilation .pio.

Les binaires disponibles sur la page de téléchargement sont compilés avec l'IDE Arduino.

{% include manuelimg.md name="code&partition.PNG" %}

Enfin, si vous avez effacé l'ensemble de votre flash il vous faudra charger le bootloader en 0X1000.
le code bin se trouve sur <https://github.com/espressif/arduino-esp32> dans l'espace tools.
