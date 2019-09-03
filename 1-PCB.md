---
layout: page
title: Materiel
linkdesc: Les fichiers de réalisation du PCB
linkmsg: Trouver !
linktarget: "/assets/pcb/gnuvario_pcb_layout.zip"
---

Le SCHEMA
-----------------------------------------

![Le Schema du GNUVario]({{ '/assets/schematic.jpg' | relative_url }})

Il peut être téléchargés [ici]({{ '/assets/schematic.pdf' | relative_url }}).

Le PCB
-----------------------------------------

Le projet GNUVario fourni les fichiers du circuit imprimé pour vous aider à construire le variomètre.![Le PCB Back du GNUVario]({{ '/assets/PCB V2 back.jpg' | relative_url }})
![Le PCB Front du GNUVario]({{ '/assets/PCB_V2_front.jpg' | relative_url }})

Ils peuvent être téléchargés [ici]({{ '/assets/pcb/gnuvario_pcb_layout.zip' | relative_url }}).

Voici les paramètres à donner à votre fabricant de PCB :
* largeur  : 44 mm
* longueur : 100 mm 
* épaisseur : 1.6 mm

Cette maquette de circuit imprimé a été réalisée avec [KiCad](http://kicad-pcb.org/) et le projet peut être téléchargé [ici]({{'/assets/pcb/gnuvario_pcb_project.zip' | relative_url }}).

Les composants
-----------------------------------------

* TTGO-T5 V1.6 ou v2.4 avec écran 1.54'' ( ae, ttgo-t5 v2.4 1.54 ) 
![TTGO-T5]({{ '/assets/componants/TTGO-T5-v1-2.jpg' | relative_url }})
* Ms5611 mpu9250 ( eb/ae, CJMCU-117 )
![Slide switch]({{ '/assets/componants/mpu2.jpg' | relative_url }})
* GPS ATGM336H  ( ae, ATGM336H avec antenne externe )
![Slide switch]({{ '/assets/componants/ATGM336H.JPG' | relative_url }})
* Resistance 270k (R1) ( ae/eb ) (pour TTGO v1.6)
* Resistance 1M (R2) ( ae/eb ) (pour TTGO v1.6)
* 3 x Resistance 1k (R3,R4,R5) ( ae/eb )
* Transistor S8050 ou equivalent (2N2222) en boitier T092 ( ae/eb ) (option)
* Batterie 403070 (ae)
![Slide switch]({{ '/assets/componants/battery.jpg' | relative_url }})
* 4 x Vis à bois 3x20
* Velcro 20mm

