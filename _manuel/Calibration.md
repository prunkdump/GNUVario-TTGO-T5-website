---
step: 7
description: La calibration
---

**ATTENTION. La version actuelle du Gnuvario-E ne permet pas encore de faire la calibration**

Si nécessaire, calibrez l'accéléromètre
----------------------------------------

Le GnuVario-E intégre un accéléromètre, qui doit être calibré.

D'abord sous Windows ou Mac, installez [Python version 2](https://www.python.org/) . Sous Windows, assurez-vous de cocher l'option **add to PATH variable**.

Assurez-vous que votre carte SD est à l'intérieur du variomètre.  
Passez en mode calibration en appuyant sur le bouton droit au démarrage, Et suivez cette procédure:

<iframe width="560" height="315" src="https://www.youtube.com/embed/6yxoZcxxzVY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Cela créera un fichier "RECORD**.CAL" sur la carte SD. Copiez ce fichier dans le dossier "best-fit-calibration" et renommez-le si nécessaire en tant que "RECORD00.IGC".

Sous Windows ou Mac, lancez l'**Idle** Python et ouvrez le programme "best-fit-calibrage/calibrer.py". Appuyez sur "F5" pour exécuter.

Sous Linux, lancez simplement :

{% highlight shell_session %}
~$ cd Arduino/best-fit-calibration
~/best-fit-calibration$ python2 calibrate.py
{% endhighlight %}

Cela montrera les paramètres que vous devez remplacer dans votre fichier *HardwareConfig.h* (utile si pas de sdcard, mais nécessite une compilation) et *vatiocal.cfg* ou recopier sur la page Web de configuration

