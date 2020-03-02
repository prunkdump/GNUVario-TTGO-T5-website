---
step: 5
description: Compilation avec VSCode - PlatformIO
---

En préalable, il faut télécharger localement les sources depuis le dépot GIT.  
Le répertoire local doit contenir à minima :
- le dossier src/, qui contient le fichier Gnuvario-E.cpp
- le dossier lib/, qui contient les librairies nécessaires
- les fichiers platformio.ini et custompart.csv

{% include codeimg.md name="platformio_files.jpg" %}

Dans VSCode, cliquer sur l'icone 'PlatformIO: Home' dans la barre horizontale en bas. La page PlatformIO Home va s'afficher dans l'IDE. 

{% include codeimg.md name="platformio_home.jpg" %}

Cliquer sur 'Import Arduino Project'.
- sélectionner le 'board'. Pour accélérer la sélection, saisir esp32, puis choisir 'Expressif ESP32 Dev Module'
- ne pas cliquer 'Use libraries installed by Arduino IDE'
- sélectionner le dossier qui contient le code récupéré du dépôt git
- cliquer sur le bouton 'Import'

{% include codeimg.md name="platformio_import_project.jpg" %}

Le projet apparait dans la colonne gauche (EXPLORER) de l'IDE ; il est possible d'explorer les différents fichiers de celui-ci.

{% include codeimg.md name="platformio_projet.jpg" %}

Dans la barre horizontale du bas, plusieurs icônes liées à PlatformIO et au projet courant apparaissent.  
Les icones les plus intéressantes sont :
- (1). PlatformIO: Home : ouvrir la fenêtre PlatformIO Home
- (2). PlatformIO: Build : compiler le code
- (3). PlatformIO: Upload : compiler de code, et le charger dans le vario
- (8). Platformio: Serial Monitor : ouverture d'un terminal série basique

Et maintenant, si on désire compiler le code et le charger dans le vario, il faut :
- démarrer le vario
- relier le vario au PC via la micro USB
- cliquer sur l'icône PlatformIO: Upload

La compilation va se faire. si pas d'erreur, le code compilé sera chargé dans le vario, et celui-ci redémarrera.
