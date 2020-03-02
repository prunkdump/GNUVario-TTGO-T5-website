---
step: 5
description: La page Web
---

Le GnuVario-E embarque un serveur Web ; on y accède après la connexion wifi, via un navigateur Internet. Voir page précédente du manuel.

La page d'accueil se présente comme cela :
{% include manuelimg.md name="pageweb_01.jpg" %}

ou comme cela, si la largeur d'écran ne permet pas l'affichage de l'ensemble des menus. 
{% include manuelimg.md name="pageweb_02.jpg" %}

Dans ce dernier cas, il suffit de cliquer sur l'icone de menu, en haut à droite, pour accéder au menu.

Les différentes options de menu sont décrites maintenant.

### Menu "Mes vols"

C'est le menu proposé par défaut. Il liste les différents fichiers IGC des vols enregistrés sur la carte SD.  
Pour chaque vol, on peut :
- supprimer l'enregistrement
- le télécharger
- le visualiser de manière sommaire



### Onglet "Carte SD"

Présente le contenu de la carte SD. Permet de créer / supprimer des dossiers, télécharger ou télé-déposer des fichiers.  
{% include manuelimg.md name="SDcard_01.jpg" %}  
#### Dossiers
Les dossiers sont proposés en premier. Si on clique sur le titre d'un dossier, on ouvre celui-ci, et les fichiers inclus sont affichés ; on le voit dans la copie d'écran précédente, pour le dossier 'vols'.  
On peut déposer de nouveaux fichiers dans un dossier en cliquant sur l'icone bleue 'Télécharger' ; on peut aussi supprimer un dossier et tous les fichiers inclus en cliquant sur l'icone rouge 'Supprimer'.
#### Fichiers
On peut télécharger sur l'ordinateur le fichier en cliquant sur l'icone verte 'Télécharger' ; on peut également supprimer le fichier en cliquant sur l'icone rouge 'Supprimer'.

### Onglet "Wifi"

Permet de spécifier les réseaux wifi auxquels le vario peut potentiellement se connecter.  
Il est possible de déclarer jusqu'à 4 réseaux wifi.  
Le résultat est écrit sur la carte SD, dans le fichier '/wifi.cfg'

### Onglet "Configuration"

Les options proposées dans cet onglet permettent de personnaliser le fonctionnement du vario ; elles sont liées au fichier '/params.jso' sur la carte SD.  
Les paramètres sont décrits dans la partie ['Configuration']({{ site.baseurl }}/6-configuration.html) de la documentation du GNUVario.

Ces paramètres sont répartis dans 4 onglets :  
'_Général_' - '_Vario_' - '_Début du vol_' - '_Système_'  
{% include manuelimg.md name="configuration_01.jpg" %}  
- Général  
Permet de décrire la ou les voiles sur lesquelles on vole, et le nom du pilote.  
Sert essentiellement aux enregistrements UGC des vols
- Vario  
Permet de paramétrer le fonctionnement du vario : seuil de déclenchement des bips sonores, et différentes options
- Début du vol  
Permet de définit les critères qui vont permettre au vario de déterminer qu'un vol vient de commencer. 
- Système  
Permet de régler différents paramètres relatifs au fonctionnement du vario : bips au démarage du vario, du vol, du fixe GPS, activation de l'enregistrement des vols, compensations de température ou de l'altitude GPS, ...

### Onglet "Mise à jour"
Permet de mettre à jour le logiciel (firmware) du vario.  
{% include manuelimg.md name="update_01.jpg" %}  
La mise à jour peut se faire en 'local', depuis un ordinateur qui disposerait d'une version du firmware désirée.

Il est aussi possible de mettre à jour automatiquement le firmware depuis l'internet. 

Voir la documentation dédiée à la mise à jour du vario.
