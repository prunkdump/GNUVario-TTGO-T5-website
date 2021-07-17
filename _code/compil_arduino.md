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

Vous devez maintenant choisir la combinaison écran/circuit imprimé que vous possédez. 
Pour cela, ouvrez avec un éditeur de texte style [**Notepadd++**](https://notepad-plus-plus.org/downloads/) le fichier **HardwareConfig.h** se situant dans le dossier **Arduino\librairies\HardwareConfig**.

Le choix de la combinaison se fait en décommentant la ligne correspondante à votre combinaison. Ici la version 293.

{% highlight shell_session %}
//VERSION
//#define VARIOVERSION 154     //PCB Version 1 avec ecran 1.54 / PCB version 1 with 1.54" screen
//#define VARIOVERSION 254     //PCB Version 2 avec ecran 1.54 / PCB Version 2 with 1.54" screen
//#define VARIOVERSION 290     //PCB Version 2 avec ecran 2.9" paysage / PCB version 2 with 2.9" screen landscape (TTGO-T5-V2.4 before 12/2020)
//#define VARIOVERSION 291     //PCB Version 2 avec ecran 2.9" portrait / PCB version 2 with 2.9" screen portrait (TTGO-T5-V2.4 before 12/2020)
//#define VARIOVERSION 292     //PCB Version 2 avec ecran 2.9" paysage /PCB version 2 with 2.9" screen landscape  (Ecran/Screen Good Display GDEW029M06)      
#define VARIOVERSION 293     //PCB Version 2 avec ecran 2.9" portrait / PCB version 2 with 2.9" screen portrait (Ecran/Screen Good Display GDEW029M06)
//#define VARIOVERSION 294     //PCB Version 2 avec ecran 2.9" portrait / PCB version 2 with 2.9" screen portrait (TTGO-T5-V2.4 after 12/2020 Screen number DKEG0290BNS800F6 /QYEG0290BNS800F6C02 ) For test purpose only
//#define VARIOVERSION 354     //PCB Version 3.1 avec ecran 1.54 / PCB Version 3.1 with 1.54" screen
//#define VARIOVERSION 390     //PCB Version 3.1 avec ecran 2.9" paysage / PCB version 3.1 with 2.9" screen landscape (TTGO-T5-V2.4 before 12/2021)
//#define VARIOVERSION 391     //PCB Version 3.1 avec ecran 2.9" portrait / PCB version 3.1 with 2.9" screen portrait (TTGO-T5-V2.4 before 12/2021)
//#define VARIOVERSION 392     //PCB Version 3.1 avec ecran 2.9" Good Display GDEW029M06 paysage / PCB version 3.1 with 2.9" screen landscape  (Ecran/Screen Good Display GDEW029M06) 
//#define VARIOVERSION 393	   //PCB Version 3.1 avec ecran 2.9" Good Display GDEW029M06 portrait / PCB version 3.1 with 2.9" screen portrait (Ecran/Screen Good Display GDEW029M06) 
//#define VARIOVERSION 395     //PCB Version 3.5 avec ecran 2.9" paysage (futur BNO085/86)
//#define VARIOVERSION 396     //PCB Version 3.5 avec ecran 2.9" portrait (futurBNO085/86)
{% endhighlight %}

Sauvegarder le fichier puis retournez sur l'**IDE Arduino**.

Il vous suffit maintenant de cliquer sur le bouton **téléverser**.

![GitHub download zip]({{ "/assets/code_img/code7.jpg" | absolute_url }})

Ceci va lancer la compilation du code, puis mettre à jour le vario. Le vario redémarrera seul en fin de procédure.

Vous pouvez maintenant débrancher la sortie USB et arrêter le vario.

Pour préparer la carte microSD, c'est [**ICI**]({{site.baseurl}}/manuel/SDupdate.html)



