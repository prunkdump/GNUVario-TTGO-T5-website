---
step: 7
description: La calibration
---


Si nécessaire, calibrez l'accéléromètre
----------------------------------------

Le GnuVario-E intégre un accéléromètre, qui doit être calibré.

D'abord sous Windows ou Mac, installez [Python version 2](https://www.python.org/) . Sous Windows, assurez-vous de cocher l'option **add to PATH variable**.

Ensuite, passer en mode calibration. Assurez-vous que votre carte SD est à l'intérieur du variomètre. Et suivez cette procédure:

<iframe width="560" height="315" src="https://www.youtube.com/embed/6yxoZcxxzVY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

Cela créera un fichier "RECORD**.IGC" sur la carte SD. Copiez ce fichier dans le dossier "best-fit-calibration" et renommez-le si nécessaire en tant que "RECORD00.IGC".

Sous Windows ou Mac, lancez l'**Idle** Python et ouvrez le programme "best-fit-calibrage/calibrer.py". Appuyez sur "F5" pour exécuter.

Sous Linux, lancez simplement :

{% highlight shell_session %}
~$ cd Arduino/best-fit-calibration
~/best-fit-calibration$ python2 calibrate.py
{% endhighlight %}

Cela montrera les paramètres que vous devez remplacer dans votre fichier *HardwareConfig.h* et *SETTINGS.TXT* ou recopier sur la page Web de configuration

