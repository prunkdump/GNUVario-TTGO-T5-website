---
step: 7
description: La calibration
---

Le GnuVario-E intègre un accéléromètre, qui doit être calibré.

## Procédure de calibration

La calibration s’effectue en plusieurs étapes :
1. [Nettoyage de la carte SD](#nettoyage-de-la-carte-sd)
2. [Mesure de points expérimentaux](#mesures)
3. Calcul des valeurs de calibration
4. Sauvegarde des valeurs de calibration sur la carte SD

Depuis la version 0.10.2 du serveur web, les étapes 3 et 4 sont simplifiées.

### Nettoyage de la carte SD

**1.** Réinitialisation du fichier `variocal.cfg`

{% include manuelimg.md name="calibrationweb1.jpg" %}

Depuis le serveur web, onglet « Carte SD » ou directement sur la carte
SD, vérifiez que le fichier `variocal.cfg` est bien le fichier vierge disponible
dans le dossier `RootSD`, dont voici un aperçu :

{% highlight shell_session %}
Fichier `variocal.cfg` vierge :

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

**2.** Effacez le fichier `RECORD00.CAL` s’il est présent.

### Mesures

Redémarrez le vario puis effectuez la manipulation de calibration : 

Passez en mode calibration en appuyant sur le bouton droit au démarrage (au
moment de l’écran d’init). Vous avez quelques secondes pour placer le vario à
plat et appuyer sur le bouton central.

Pour être optimale, la calibration ne doit pas se faire sur un axe nord/sud. Si
vous savez où est le nord, essayez de décaler le vario de 45° par rapport au
nord (quand il est à plat sur la table).

**Attendez les 3 bips**, puis commencez à faire pivoter le vario dans toutes les
directions en vous aidant d’un support (carton, livre) afin de le stabiliser sur
sa tranche. Vous devez faire environ 5 à 6 déplacements par face en attendant le
bip entre chaque déplacement. Plus vous ferez de mesures, plus la calibration
sera précise. **ATTENTION il est indispensable de n’oublier aucune face.**

À la fin, appuyez sur le bouton gauche du vario pendant au moins deux secondes
pour terminer la calibration. Le vario redémarre.

<iframe width="560" height="315" src="https://www.youtube.com/embed/6yxoZcxxzVY"
frameborder="0" allow="autoplay; encrypted-media" allowfullscreen></iframe>

### Calcul et sauvegarde des valeurs de calibration

Retournez sur le serveur web puis allez sur l’onglet « Configuration », puis
« CALIBRATION »

{% include manuelimg.md name="calibrationweb3.jpg" %}

Appuyez sur « Lancer la génération du fichier de calibration ». Le fichier
`RECORD00.CAL` créé pendant la phase de calibration est envoyé sur un serveur
distant qui calcule les bonnes valeurs et met à jour le fichier `variocal.cfg`.

Si le message « Calcul du fichier de calibration OK » apparait, c’est que tout
s’est bien passé. Votre vario est calibré.

{% include manuelimg.md name="calibrationweb2.jpg" %}


## Calcul des valeurs de calibration à l’aide du script Python

**Si la procédure semi-automatique [décrite
ci-dessus](#calcul-et-sauvegarde-des-valeurs-de-calibration) ne fonctionne
pas**, vous pouvez calculer les valeurs de calibration avec un script python,
après avoir effectué [le nettoyage de la carte SD](#nettoyage-de-la-carte-sd) et
la [mesure de points expérimentaux](#mesures).

### Instructions pour les utilisateurs de Windows

**1.** Installez le programme [Python](https://www.python.org/downloads/).
Assurez-vous de cocher l’option **add Python x.x to PATH**.

{% include manuelimg.md name="python6.jpg" %}

**2.** Copiez sur votre bureau le dossier « calibration » se trouvant dans le
dossier `RootSD`.

**3.** Lancer IDLE python, dans l’IDLE : File>Open et ouvrir le fichier
`get-pip.py` qui se trouve dans le dossier `calibration/Installation`.

Appuyez sur `F5` une fois le fichier ouvert pour exécuter le programme
`get-pip.py`.

{% include manuelimg.md name="python1.jpg" %}

**4.** Une fois l’exécution terminée, ouvrez une invite de commande Windows.

Copiez et exécutez la commande suivante : `python -m pip install --user numpy
scipy matplotlib ipython jupyter pandas sympy nose`

{% include manuelimg.md name="python2.jpg" %}

Redémarrez l’ordinateur une fois la commande exécutée et terminée.

**5.** Supprimez le fichier `RECORD00.CAL` déjà présent dans le dossier
`calibration` qui est sur votre bureau

**6.** Copiez le fichier `RECORD00.CAL` qui a été généré sur la carte SD dans le
dossier `calibration` qui est sur votre bureau

**7.** Lancez IDLE python, dans l’IDLE : File>Open et ouvrir le fichier
`calibrate.py` qui se trouve dans le dossier `calibration` qui est sur votre
bureau

{% include manuelimg.md name="python3.jpg" %}

**8.** Appuyez sur `F5` pour lancer le programme

{% include manuelimg.md name="python4.jpg" %}

**9.** Vous pouvez également écrire directement la commande `python
calibrate.py` sur une invite de commande windows, après avoir changé de
répertoire (commande `cd`) pour vous placer dans le dossier `calibration` :

{% include manuelimg.md name="python5.jpg" %}

**10.** À la fin de l’exécution du programme, copiez l’ensemble des paramètres
de la calibration dans le fichier `variocal.cfg` présent sur la carte SD.

{% highlight shell_session %}
Exemple de fichier `variocal.cfg` mis à jour avec des valeurs de calibration :

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


**11.** Replacer la carte SD dans votre variomètre. Il est maintenant calibré.

### Instructions pour les utilisateurs de Linux

1. Ouvrir un terminal de commande

1. Créer un répertoire temporaire, dans lequel effectuer la calibration (dans
   l’exemple ci-dessous, il s’appelle `demo`), puis déplacez vous dans ce nouveau répertoire.

   ```bash
   mkdir demo
   cd demo
   ```

1. Copiez le dossier `calibration` de `RootSD` dans le dossier `demo`, puis
   déplacez vous dans ce nouveau répertoire.

   Si vous avez le logiciel `git`, une manière de procéder peu élégante,
   consiste à cloner le [dépôt
   logiciel](https://github.com/prunkdump/GNUVario-TTGO-T5.git) depuis Github,
   puis à y récupérer le dossier :
   ```bash
   git clone https://github.com/prunkdump/GNUVario-TTGO-T5.git
   cp -r "./GNUVario-TTGO-T5/Sources/RootSd/Pour v0.8b6/RootSD/calibration" .
   cd calibration
   ```

1. Comme il n’est pas très propre, autant faire un peu de nettoyage avant de commencer.

   ```bash
   rm -rf *.pyc *.old __pycache__
   ```

1. Copiez les mesures effectuées [précédemment](#mesures) — c’est-à-dire le
fichier `RECORD00.CAL` qui a été généré sur la carte SD — dans le dossier
`calibration`

1. Mise à jour de `pip`, et récupération de `pipenv` (qui va permettre de tout
   faire dans un environnement virtuel avec la bonne version de Python, puis de
   l’effacer après coup, de manière à ne pas polluer votre ordinateur)

   ```bash
   python -m pip install --upgrade pip
   python -m pip install pipenv
   ```

1. Création puis lancement de l’environnement virtuel

   ```bash
   python -m pipenv --python 3.7
   python -m pipenv shell
   ```

1. Installation des librairies requises dans l’environnement

   ```bash
   python -m pip install numpy scipy matplotlib ipython jupyter pandas sympy nose
   ```

1. Calibration

   ```bash
   python calibrate.py
   ```

   Recopiez les valeurs générées dans un fichier `variocal.cfg` (voir plus haut
   l’exemple de fichier `variocal.cfg` mis à jour avec des valeurs de
   calibration)

1. Sortie de l’environnement virtuel, puis suppression de l’environnement virtuel et du dossier temporaire de travail
   ```bash
   exit
   pip -m pipenv --rm
   cd ..
   cd ..
   rm -rf demo
   ```