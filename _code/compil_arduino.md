---
step: 4
description: Compilation avec l'IDE Arduino
---

Compiler le code
-----------------
En préalable, il faut mettre en marche le vario sans la sdcard, **puis** le raccorder au PC par la prise USB. Il sera reconnu par le PC comme une interface série COMx (exemple : COM3).

Lancez maintenant l'IDE Arduino et ouvrez l'esquisse que vous souhaitez compiler. Par exemple, le croquis **Gnuvario-E.ino**.

![GitHub download zip]({{ "/assets/code_img/code5.jpg" | absolute_url }})

Dans le menu **Outils**, **assurez-vous de choisir la bonne carte**. La plus classique de ce projet est l'**ESP32 Dev Module**.

et sélectionner partition scheme : **Minimal SPIFFS (1,9 MB APP with OTA / 180 KB SPIFFS)**

Toujours dans le menu **Outils**, choisissez le port série correspondant au vario. 

![GitHub download zip]({{ "/assets/code_img/ide1.jpg" | absolute_url }})

Il vous suffit de cliquer sur le bouton **téléverser**.

![GitHub download zip]({{ "/assets/code_img/code7.jpg" | absolute_url }})

Ceci va lancer la compilation du code, puis mettre à jour le vario ; le vario redémarrera seul en fin de procédure.

Vous pouvez maintenant débrancher la sortie USB, arrêter le vario, insérer la sdcard et le démarrer à nouveau.



