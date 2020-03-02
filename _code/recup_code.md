---
step: 3
description: Récupération du code
---

La méthode simple : télécharger le fichier zip
----------------------------------

Le code source peut être téléchargé directement sous forme de fichier zip sur [GitHub](https://github.com/prunkdump/GNUVario-TTGO-T5). Il suffit de cliquer sur **Clone or download** and **Download zip**.

![GitHub download zip]({{ "/assets/code_img/code1.jpg" | absolute_url }})

Extrayez le zip à l'emplacement de votre choix. Cela va créer un répertoire **Gnuvario-TTGO-T5-master**.

![GitHub téléchargement zip]({{ "/assets/code_img/code2.jpg" | absolute_url }})

L’installation de l’IDE Arduino a normalement créé un répertoire **Arduino** dans votre dossier personnel.<BR> Assurez-vous que ce dossier est vide et copiez les dossiers  Sources\Beta Code\Gnuvario-E et Sources\Beta Code\libraries du dossier **Gnuvario-TTGO-T5-master** dans le dossier **Arduino**.

**IMPORTANT** : Il ne doit y avoir dans ce dossier Arduino que les fichiers / librairies du projet Gnuvario-E.

![GitHub téléchargement zip]({{ "/assets/code_img/dossierRootArduino.jpg" | absolute_url }})

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