---
step: 5
description: Le serveur Web
---

Le GnuVario-E embarque un serveur Web. On y accède après la connexion wifi, via un navigateur Internet. Voir page précédente du manuel.

La page d'accueil se présente comme cela :
{% include manuelimg.md name="pageweb_01.jpg" %}

ou comme cela, si la largeur d'écran ne permet pas l'affichage de l'ensemble des menus. 
{% include manuelimg.md name="pageweb_02.jpg" %}

Dans ce dernier cas, il suffit de cliquer sur l'icone de menu, en haut à droite, pour accéder au menu.

### Onglet "Mes vols"

C'est le menu proposé par défaut. Il liste les différents fichiers IGC des vols enregistrés sur la carte SD.  
Il y a trois onglets:

**Mes traces en attente où pour chaque vol vous pouvez:**
- Le téléverser sur le site paraglidinglogbook.com
- Le placer dans votre carnet de vol
- le télécharger
- supprimer l'enregistrement
- le visualiser de manière sommaire

{% include manuelimg.md name="mestracesenattente.jpg" %}

**Mon carnet de vols**
- Liste des vols
- Permet de les éditer
- Statistiques de vols

{% include manuelimg.md name="moncarnetdevols.jpg" %}

**Mes sites de vols**
- Permet d'ajouter des sites de vols. 
- Les coordonnées géographiques doivent être entrées en format décimal. Vous pouvez retrouver les coordonnées sur google earth, votre trace IGC et les convertir en décimales à l'aide de ce [site](https://fr.planetcalc.com/1129/):  

{% include manuelimg.md name="messitesdevols.jpg" %}

### Onglet "Carte SD"

Présente le contenu de la carte SD. Permet de créer / supprimer des dossiers, télécharger ou télé-déposer des fichiers.  
{% include manuelimg.md name="SDcard_01.jpg" %}  
#### Dossiers
Les dossiers sont proposés en premier. Si on clique sur le titre d'un dossier, on ouvre celui-ci, et les fichiers inclus sont affichés ; on le voit dans la copie d'écran précédente, pour le dossier 'vols'.  
On peut déposer de nouveaux fichiers dans un dossier en cliquant sur l'icone bleue 'Télécharger' ; on peut aussi supprimer un dossier et tous les fichiers inclus en cliquant sur l'icone rouge 'Supprimer'.
#### Fichiers
On peut télécharger sur l'ordinateur le fichier en cliquant sur l'icone verte 'Télécharger'. on peut également supprimer le fichier en cliquant sur l'icone rouge 'Supprimer'.

### Onglet "Wifi"

Permet de spécifier les réseaux wifi auxquels le vario peut potentiellement se connecter.  
Il est possible de déclarer jusqu'à 4 réseaux wifi.  
Le résultat est écrit sur la carte SD, dans le fichier '/wifi.cfg'

### Onglet "Configuration"

Les options proposées dans cet onglet permettent de personnaliser le fonctionnement du vario ; elles sont liées au fichier '/params.jso' sur la carte SD.  
Les paramètres sont décrits dans la partie ['Configuration']({{ site.baseurl }}/6-configuration.html) de la documentation du GNUVario.

Ces paramètres sont répartis dans 4 onglets :  
'_Général_' - '_Vario_' - '_Début du vol_' - '_Système_'- '_Calibration_'   
{% include manuelimg.md name="configuration_01.jpg" %}  
- Général  
Permet de décrire la ou les voiles sur lesquelles on vole, et le nom du pilote.  
Sert essentiellement aux enregistrements IGC des vols
- Vario  
Permet de paramétrer le fonctionnement du vario : seuil de déclenchement des bips sonores, et différentes options
- Début du vol  
Permet de définit les critères qui vont permettre au vario de déterminer qu'un vol vient de commencer. 
- Système  
Permet de régler différents paramètres relatifs au fonctionnement du vario : bips au démarage du vario, du vol, du fixe GPS, activation de l'enregistrement des vols...
- Calibration     
Permet de générer le fichier variocal.cfg après avoir calibré son vario (voir page dédiée)

### Onglet "Mise à jour"
Permet de mettre à jour le logiciel (firmware) du vario.  
{% include manuelimg.md name="update_01.jpg" %}  
La mise à jour peut se faire en 'local', depuis un ordinateur qui disposerait d'une version du firmware désirée.

Il est aussi possible de mettre à jour automatiquement le firmware depuis l'internet si disponible. 

Voir la documentation dédiée à la mise à jour du vario.
