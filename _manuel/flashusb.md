---
step: 1
description: Premier démarrage
---

Avant de pouvoir utiliser le Gnuvario-E vous devez installer le logiciel puis préparer la carte MicroSD.
Pour cela, il vous faut télécharger:
- L'outil [**Flash download tools**](https://www.espressif.com/en/support/download/other-tools) d'Espressif. 
- Le binaire du [**GNUVario-E**](http://gnuvario-e.yj.fr/) correspondant à votre version d'écran et de circuit imprimé, disponible sur la page de téléchargement.
- Les deux binaires nécessaires à une première compilation, disponibles dans le dossier compressé [**Binaires_Flashdownloadtool.ZIP**](http://gnuvario-e.yj.fr/), disponible sur la page de téléchargement.

Les différentes versions de logiciel se décomposent en 3 chiffres. Le premier indique la version du circuit imprimé, de 1 à 3. Les 2 derniers correspondent au type d'écran pris en charge et son orientation sur le variomètre.

Les combinaisons prisent en charge actuellement sont:

|**Gnuvario154**    |   PCB Version 1 avec écran 1.54" |
|**Gnuvario254**    |   PCB Version 2 avec écran 1.54" |
|**Gnuvario290**    |   PCB Version 2 avec écran 2.9" paysage  (TTGO-T5-V2.4 before 12/2020)|
|**Gnuvario291**    |   PCB Version 2 avec écran 2.9" portrait (TTGO-T5-V2.4 before 12/2020)|
|**Gnuvario292**    |   PCB Version 2 avec écran 2.9" paysage (Ecran Good Display GDEW029M06)|      
|**Gnuvario293**    |   PCB Version 2 avec écran 2.9" portrait (Ecran Good Display GDEW029M06)|
|**Gnuvario294**    |   PCB Version 2 avec écran 2.9" portrait  (TTGO-T5-V2.4 after 12/2020 Screen number DKEG0290BNS800F6 /QYEG0290BNS800F6C02 ) Pour test, affichage dégradé.|
|**Gnuvario354**    |   PCB Version 3.1 avec écran 1.54" |
|**Gnuvario390**    |   PCB Version 3.1 avec écran 2.9" paysage (TTGO-T5-V2.4 before 12/2021)|
|**Gnuvario391**    |   PCB Version 3.1 avec écran 2.9" portrait (TTGO-T5-V2.4 before 12/2021)|
|**Gnuvario392**    |   PCB Version 3.1 avec écran 2.9" Good Display GDEW029M06 paysage (Ecran Good Display GDEW029M06)| 
|**Gnuvario393**    |   PCB Version 3.1 avec écran 2.9" Good Display GDEW029M06 portrait (Ecran Good Display GDEW029M06)|
 
 
### **Mise à jour du Gnuvario-E**{: style="color:   #138ca2; opacity: 1;" }   
Démarrez le Gnuvario-E sans la carte SD, **puis** connectez-le au PC par le port usb. Le PC va voir le vario comme un port Série, par exemple COM3.

Exécutez flash_download_tools.exe. choisir le "Chip Type ESP32" et "WorkMode develop".

{% include manuelimg.md name="FDT1.jpg" %}
{% include manuelimg.md name="FDT2.jpg" %}

**Sélectionnez les 3 fichiers suivants:**{: style="color:   #138ca2; opacity: 1;" }

- Le binaire compilé du GNUVario-e  à l'adresse **0x10000**. Ici la version Gnuvario294b.
- Le binaire bootloader_dio_40m.bin à l'adresse **0x1000**
- le binaire partitions.bin à l'adresse **0x8000**

Puis dans la fenêtre **"SpiFlashConfig"**, appuyez sur le bouton **"Default"** ou choississez les options comme sur l'image ci-dessus (40MHz, DIO, 32Mbit, DoNotChgBin).
Choississez le port **COM** correspondant au port USB sur lequel est branché votre vario. 

Appuyez sur le bouton **"Start"**. Le carré vert **"IDLE"** indique alors **"Download"**, et une barre de progression verte s'affiche en bas de l'utilitaire.  
L'écriture du logiciel prend environ 2mn. Lorsqu'elle est terminée, le carré vert affiche **"FINISH"**.

Vous pouvez alors couper l'alimentation du Gnuvario-E et débrancher le port usb.

Il est temps maintenant de préparer la carte MicroSD.


