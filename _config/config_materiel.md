---
step: 1
description: La configuration matérielle
---

Cette partie est uniquement nécéssaire si vous souhaitez utiliser du matériel non standard pour réaliser votre GnuVario-E

Avant de configurer la partie matériel, vous devez savoir comment [compiler le code]({{ site.baseurl }}{% link 5-code.md %}). Assurez-vous de bien connaître l'IDE Arduino.

La configuration liée au matériel se fait en éditant les fichiers [libraries/HardwareConfig/HardwareConfig.h](https://github.com/prunkdump/GNUVario-TTGO-T5/tree/master/Sources/Beta%20Code/libraries/HardwareConfig/HardwareConfig.h) et [libraries/HardwareConfig/HardwareConfigESP32.h](https://github.com/prunkdump/GNUVario-TTGO-T5/tree/master/Sources/Beta%20Code/libraries/HardwareConfig/HardwareConfigESP32.h) dans votre dossier Arduino. Si vous n'avez pas d'éditeur adapté à l'écriture de code, vous pouvez le télécharger [Notepad++](https://notepad-plus-plus.org/).

Commencez par vérifier les fichiers. Il y a un fichier commun à tous les microcontroleurs et un fichier lié à l'ESP32 (TTGO-T5). La configuration du **matériel**, numéro des pins, adresses des cartes ou de la mémoire se trouvent dans ces fichiers. Chaque option est documentée par des commentaires directement à l'intérieur de ce fichier, lisez-les attentivement.

Pour "commenter" une ligne ajouter "//" au début. Cela désactive l'option.

Normalement, si vous utiliser un écran de taille différente de 1.54", vous ne devriez avoir à adapter que le type d'écran : c'est la directive **VARIOSCREEN_SIZE** dans le fichier HardwareConfig.h.

