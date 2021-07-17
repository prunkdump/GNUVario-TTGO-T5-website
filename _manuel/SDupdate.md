---
step: 2
description:  Mise à jour de la carte SD et du serveur web embarqué.
---

# **1. Première mise à jour**{: style="color:   #138ca2; opacity: 1;" }

Si vous venez de construire votre variomètre, il suffit de télécharger la dernière version du dossier "RootSD" correspondant à la version de votre firmware sur le [**site de téléchargement**](http://gnuvario-e.yj.fr/).

Après l'avoir décompressé, copiez les fichiers contenus dans ce dossier directement à la racine de votre carte microSD vierge formatée préalablement en Fat16 ou 32.

Téléchargez ensuite le zip ["www"](http://gnuvario-e.yj.fr/) (Onglet **"Télécharger les fichiers web"**) correspondant à votre version et après l'avoir décompressé, copiez le fichier **www.gz** à la racine de la carte microSD.

N'oubliez pas de télécharger les fichiers topographiques de votre région [**ici**](https://vps.skybean.eu/agl/) et de les copier dans le dossier AGL.

Insérer la carte dans votre vario et démarrez le. Le serveur web se mettra à jour puis il redémarrera. Votre vario est prêt à être [configuré]({{site.baseurl}}/manuel/page_web.html).     

# **2. Mises à jour suivantes**{: style="color:   #138ca2; opacity: 1;" }

Les mises à jour suivantes sont similaires mais certains fichiers ne sont pas à remplacer pour ne pas perdre vos données et paramètres.
 
Téléchargez la dernière version du dossier "RootSD" correspondant à la version de votre firmware sur le [**site de téléchargement**](http://gnuvario-e.yj.fr/)
Après l'avoir décompressé, copiez les fichiers contenus dans ce dossier directement à la racine de votre carte microSD **SAUF**{: style="color:   #ff3349; opacity: 1;" }:

**Les fichiers:**{: style="color:   #138ca2; opacity: 1;" }

- `prefs.jso` (Préfèrences du webserveur)

- `params.jso` (Paramètres du web serveur)

- `variocal.cfg` (votre calibration)

- `variosound.cfg`(votre courbe de son personnalisée)

- `wifi.cfg` (vos codes wifi)

**Les dossiers:**{: style="color:   #138ca2; opacity: 1;" }

- `AGL` (vos fichiers topographiques déja téléchargés)

- `db` (la base de données incluant les vols classés et sites enregistrés)

- `vols` (si vous avez des vols non encore classés).

Téléchargez ensuite le zip ["www"](http://gnuvario-e.yj.fr/) (Onglet **"Télécharger les fichiers web"**) correspondant à votre version et après l'avoir décompressé, copiez le fichier **www.gz** à la racine de la carte microSD.

Au démarrage de votre vario, le serveur web se mettra à jour puis le vario redémarrera. 

Avant tout mise à jour, nous vous conseillons de faire une copie de sauvegarde de votre carte microSD.


