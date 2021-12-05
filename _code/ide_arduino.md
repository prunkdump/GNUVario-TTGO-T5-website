---
step: 1
description: IDE Arduino
---

Pour compiler le code source GNUVario-E, vous avez besoin de l’IDE ​​Arduino pouvant être téléchargé [ici](https://www.arduino.cc/en/Main/Software). Commencez par l'installer et assurez-vous que vous pouvez lancer l'éditeur.

Ensuite, vous allez ajouter la gestion des cartes ESP32 dans l'IDE Arduino

Allez dans l'onglet **"Fichier"** puis **"Préférences"** de l'IDE et ajouter l'URL **https://dl.espressif.com/dl/package_esp32_index.json** aux URL de gestionnaire de cartes supplémentaires.

![GitHub téléchargement zip]({{ "/assets/code_img/code11.jpg" | absolute_url }})

Puis allez dans l'onglet **"Outils"**, **"type de carte"** et cliquez sur **"Gestionnaire de carte"**

![GitHub téléchargement zip]({{ "/assets/code_img/code12.jpg" | absolute_url }})

Cherchez les cartes **ESP32 by Espressif Systems** puis cliquez sur installer.

![GitHub téléchargement zip]({{ "/assets/code_img/code13.jpg" | absolute_url }})


Maintenant que l'IDE est configuré, vous pouvez récupérer le code source du GNUVario-E.