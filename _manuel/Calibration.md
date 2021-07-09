---
step: 6
description: La calibration
---

**Il est important de calibrer les accéléromètres**

Le GnuVario-E intégre un accéléromètre, qui doit être calibré.

**Procédure:**

Depuis la version 0.10.2 du webserveur, la procédure de calibration est simplifiée.

{% include manuelimg.md name="calibrationweb1.jpg" %}

**1.** Depuis le serveur web, onglet "Carte SD" ou directement sur la carte SD, vérifiez que le fichier variocal.cfg soit le fichier vierge disponible dans le dossier RootSD.

{% highlight shell_session %}
Fichier variocal.cfg vierge

[VERSION=1.0]

/* Calibration */
[VERTACCEL_GYRO_CAL_BIAS_00=0x00]
[VERTACCEL_GYRO_CAL_BIAS_01=0x00]
[VERTACCEL_GYRO_CAL_BIAS_02=0x00]
[VERTACCEL_GYRO_CAL_BIAS_03=0x00]
[VERTACCEL_GYRO_CAL_BIAS_04=0x00]
[VERTACCEL_GYRO_CAL_BIAS_05=0x00]
[VERTACCEL_GYRO_CAL_BIAS_06=0x00]
[VERTACCEL_GYRO_CAL_BIAS_07=0x00]
[VERTACCEL_GYRO_CAL_BIAS_08=0x00]
[VERTACCEL_GYRO_CAL_BIAS_09=0x00]
[VERTACCEL_GYRO_CAL_BIAS_10=0x00]
[VERTACCEL_GYRO_CAL_BIAS_11=0x00]
[VERTACCEL_ACCEL_CAL_BIAS_00=0]
[VERTACCEL_ACCEL_CAL_BIAS_01=0]
[VERTACCEL_ACCEL_CAL_BIAS_02=0]
[VERTACCEL_ACCEL_CAL_SCALE=0]
[VERTACCEL_MAG_CAL_BIAS_00=0]
[VERTACCEL_MAG_CAL_BIAS_01=0]
[VERTACCEL_MAG_CAL_BIAS_02=0]
[VERTACCEL_MAG_CAL_PROJ_SCALE=-16689]
[VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER=6]
[VERTACCEL_MAG_CAL_BIAS_MULTIPLIER=4]

{% endhighlight %}


**2.** Effacez le fichier "RECORD00.CAL si il est présent.

**3.** Redémarrez le vario puis effectuez la manipulation de calibration: 

Passez en mode calibration en appuyant sur le bouton droit au démarrage (au moment de l'écran d'init).          
Vous avez quelques secondes pour placer le vario à plat et appuyer sur le bouton central.

Pour être optimal, la calibration ne doit pas se faire sur un axe nord/sud. Si vous savez ou est le nord, essayez de décaler de 45° le vario par rapport au nord (quand il est a plat sur la table)     

**Attendez les 3 bips** puis commencez à faire pivoter le vario dans toutes les directions en vous aidant d'un support (carton, livre) afin de le stabiliser sur sa tranche.     
Vous devez faire environ 5 à 6 déplacements par face en attendant le bip entre chaque déplacement   
Plus vous ferez de mesures, plus la calibration sera précise.          
**ATTENTION il est indispensable de n'oublier aucune face**      

A la fin, appuyez sur le bouton gauche du vario pendant au moins deux secondes pour terminer la calibration. Le vario redémarre.       

<iframe width="560" height="315" src="https://www.youtube.com/embed/6yxoZcxxzVY" frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>




**4.** Retournez sur le serveur web puis allez sur l'onglet "Configuration", puis "CALIBRATION"

{% include manuelimg.md name="calibrationweb3.jpg" %}

Appuyez sur "Lancer la génération du fichier de calibration". Le fichier RECORD00.CAL créé pendant la phase de calibration est envoyé sur un serveur distant qui calcule les bonnes valeurs et met à jour le fichier Variocal.cfg.  

Si le message "Calcul du fichier de calibration OK apparait, c'est que tout s'est bien passé. Votre vario est calibré. 

{% include manuelimg.md name="calibrationweb2.jpg" %}


**Si la procédure semi-automatique ci-dessus ne fonctionne pas, vous pouvez calculer les valeurs de calibration avec un script python.**


**1.** Sous Windows, installez le programme [Python](https://www.python.org/downloads/) . Assurez-vous de cocher l'option **add Python x.x to PATH**.

{% include manuelimg.md name="python6.jpg" %}

**2.** Copiez sur votre bureau le dossier "calibration" se trouvant dans le dossier RootSD.

**3.** Lancer IDLE python, dans l’IDLE : File>Open et ouvrir le fichier get-pip.py qui se trouve dans le dossier/ calibration/Installation

Appuyez sur F5 une fois le fichier ouvert pour exécuter le programme get-pip.py

{% include manuelimg.md name="python1.jpg" %}

**4.** Une fois l’exécution terminée, ouvrez une invite de commande Windows.

Copiez et exécutez la commande suivante : "python -m pip install --user numpy scipy matplotlib ipython jupyter pandas sympy nose"

{% include manuelimg.md name="python2.jpg" %}

Redémarrez l’ordinateur une fois la commande exécutée et terminée.

**5.** Suivez les étapes de calibration **1. 2. & 3.** de la calibration via le serveur web ci-dessus pour effectuer la calibration du vario.

**6.** Supprimez le fichier “RECORD00.CAL” déjà présent dans le dossier “calibration” qui est sur votre bureau

**7.** Copiez le fichier “RECORD00.CAL” de la carte SD dans le dossier “calibration” qui est sur votre bureau


**8.** Lancez IDLE python, dans l’IDLE : File>Open et ouvrir le fichier calibrate.py qui se trouve dans le dossier  « calibration » qui est sur votre bureau

{% include manuelimg.md name="python3.jpg" %}

**9.** Appuyez sur F5 pour lancer le programme

{% include manuelimg.md name="python4.jpg" %}

**10.** Vous pouvez également écrire directement la commande python calibrate.py sur une invite de commande windows à l'adresse de votre dossier calibration:

{% include manuelimg.md name="python5.jpg" %}

**11.** A la fin de l’exécution du programme, copiez l’ensemble des paramètres de la calibration dans le fichier variocal.cfg présent sur la carte SD.

{% highlight shell_session %}
Fichier variocal.cfg

[VERSION=1.0]

/* Calibration */
[VERTACCEL_GYRO_CAL_BIAS_00=0xad]
[VERTACCEL_GYRO_CAL_BIAS_01=0x80]
[VERTACCEL_GYRO_CAL_BIAS_02=0x0f]
[VERTACCEL_GYRO_CAL_BIAS_03=0x80]
[VERTACCEL_GYRO_CAL_BIAS_04=0x00]
[VERTACCEL_GYRO_CAL_BIAS_05=0x1e]
[VERTACCEL_GYRO_CAL_BIAS_06=0xfd]
[VERTACCEL_GYRO_CAL_BIAS_07=0x3f]
[VERTACCEL_GYRO_CAL_BIAS_08=0x01]
[VERTACCEL_GYRO_CAL_BIAS_09=0x00]
[VERTACCEL_GYRO_CAL_BIAS_10=0xf4]
[VERTACCEL_GYRO_CAL_BIAS_11=0xff]
[VERTACCEL_ACCEL_CAL_BIAS_00=5101]
[VERTACCEL_ACCEL_CAL_BIAS_01=16835]
[VERTACCEL_ACCEL_CAL_BIAS_02=5334]
[VERTACCEL_ACCEL_CAL_SCALE= -433 ]
[VERTACCEL_MAG_CAL_BIAS_00=-10569]
[VERTACCEL_MAG_CAL_BIAS_01=-2289]
[VERTACCEL_MAG_CAL_BIAS_02=18776]
[VERTACCEL_MAG_CAL_PROJ_SCALE= -3553 ]
[VERTACCEL_ACCEL_CAL_BIAS_MULTIPLIER= 8 ]
[VERTACCEL_MAG_CAL_BIAS_MULTIPLIER= 6 ]

{% endhighlight %}


**12.** Replacer la carte SD dans votre variomètre. Il est maintenant calibré.