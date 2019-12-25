---
layout: page
title: Code
linkdesc: Le code source
linkmsg: Trouver !
linktarget: "https://github.com/jpg63/Gnuvario_for_TTGO-T5"
---

Pour compiler le code source GNUVario-E, vous avez besoin de l’IDE ​​Arduino pouvant être téléchargé [ici](https://www.arduino.cc/en/Main/Software). Commencez par l'installer et assurez-vous que vous pouvez lancer l'éditeur.

Ensuite, vous allez ajouter la gestion des cartes ESP32 dans l'IDE Arduino

Allez dans les préférences de l'IDE

![GitHub téléchargement zip]({{ "/assets/code/code11.jpg" | absolute_url }})

Ajouter l'URL https://dl.espressif.com/dl/package_esp32_index.json aux URL de gestionnaire de cartes supplèmentaire 

Maintenant que l'IDE est configuré, vous pouvez récupérer le code source du GNUVario-E.

La méthode simple : télécharger le fichier zip
----------------------------------

Le code source peut être téléchargé directement sous forme de fichier zip sur [GitHub](https://github.com/prunkdump/GNUVario-TTGO-T5). Il suffit de cliquer sur **Clone or download** and **Download zip**.

![GitHub download zip]({{ "/assets/code/code1.jpg" | absolute_url }})

Extrayez le zip à l'emplacement de votre choix. Cela va créer un repertoire **Gnuvario-TTGO-T5-master**.

![GitHub téléchargement zip]({{ "/assets/code/code2.jpg" | absolute_url }})

L’installation de l’IDE Arduino a normalement créé un répertoire **Arduino** dans votre dossier personnel.<BR> Assurez-vous que ce dossier est vide et copiez les dossiers  Sources\Beta Code\Gnuvario-E et Sources\Beta Code\libraries du dossier **Gnuvario-TTGO-T5-master** dans le dossier **Arduino**.

**IMPORTANT** : Il ne doit y avoir dans ce dossier Arduino que les fichiers / librairies du projet Gnuvario-E.

![GitHub téléchargement zip]({{ "/assets/code/dossierRootArduino.jpg" | absolute_url }})

La méthode avancée: utiliser Git
-----------------------------

Vous pouvez également obtenir le code source avec [Git](https://git-scm.com/). C'est une meilleure approche car avec Git, vous pouvez mettre à jour le code tout en gardant vos paramètres préférés.

Installez donc Git et assurez-vous que le dossier **Arduino** de votre répertoire personnel est vide. Avec le bash, allez dans le répertoire **Arduino**, clonez le référentiel et créez une branche pour vous.

{% highlight shell_session %}
~$ cd Arduino
~/Arduino$ git clone https://github.com/prunkdump/GNUVario-TTGO-T5.git .
~/Arduino$ git checkout -b myversion 
{% endhighlight %}

Ainsi, chaque fois que vous souhaitez mettre à jour le code, tapez les commandes suivantes à partir du répertoire **Arduino**. Les deux premières lignes enregistrent vos modifications. Les deux lignes suivantes téléchargent les modifications depuis la branche principale de GitHub. La dernière applique la modification à votre version.

{% highlight shell_session %}
~/Arduino$ git add -A
~/Arduino$ git commit -m 'change'
~/Arduino$ git checkout master
~/Arduino$ git pull
~/Arduino$ git checkout myversion
~/Arduino$ git merge master
{% endhighlight %}

Compiler le code
-----------------
En préalable, il faut mettre en marche le vario sans la sdcard, **puis** le raccorder au PC par la prise USB. Il sera reconnu par le PC comme une interface série COMx (exemple : COM3).

Lancez maintenant l'IDE Arduino et ouvrez l'esquisse que vous souhaitez compiler. Par exemple, le croquis **Gnuvario-E.ino**.

![GitHub download zip]({{ "/assets/code/code5.jpg" | absolute_url }})

Dans le menu **Outils**, **assurez-vous de choisir la bonne carte**. La plus classique de ce projet est l'**ESP32 Dev Module**.

et selectionner partition scheme : **Minimal SPIFFS (1,9 MB APP with OTA / 180 KB SPIFFS)**

Toujours dans le menu **Outils**, choisissez le port série correspondant au vario. 

![GitHub download zip]({{ "/assets/code/ide1.jpg" | absolute_url }})

Il vous suffit de cliquer sur le bouton **téléverser**.

![GitHub download zip]({{ "/assets/code/code7.jpg" | absolute_url }})

Ceci va lancer la compilation du code, puis mettre à jour le vario ; le vario redémarrera seul en fin de procédure.

Vous pouvez maintenant débrancher la sortie USB, arrêter le vario, insérer la sdcard et le démarrer à nouveau.




