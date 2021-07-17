---
step: 5
description: Wifi
---

Le Gnuvario-E embarque un serveur Web, qui va permettre de configurer le Gnuvario, le mettre à jour,
 récupérer les fichiers de vol mais aussi de copier ou récupérer des fichiers sur la carte SDCard
 
{% include manuelimg.md name = "ecran291wifireboot.png"%}

**Paramètrage du Wifi**      

Avant de pouvoir utiliser le Wifi avec le Gnuvario-E, vous devez indiquer le SSID et le mot de passe de votre Box ou de votre téléphone   

Compléter les informations dans le fichier wifi.cfg. Vous pouvez indiquer jusqu'à 4 réseaux Wifi différents.   

Si vous ne souhaitez pas utiliser la carte SD, vous devrez compléter le fichier variosettings.h (nécessite une compilation du code).

#define DEFAULT_VARIOMETER_SSID_1													"your_SSID1"   
#define DEFAULT_VARIOMETER_PASSWORD_1											"your_PASSWORD_for SSID1"   

#define DEFAULT_VARIOMETER_SSID_2													"your_SSID2"   
#define DEFAULT_VARIOMETER_PASSWORD_2											"your_PASSWORD_for SSID2"   

#define DEFAULT_VARIOMETER_SSID_3													"your_SSID3"   
#define DEFAULT_VARIOMETER_PASSWORD_3											"your_PASSWORD_for SSID3"   

#define DEFAULT_VARIOMETER_SSID_4													"your_SSID4"   
#define DEFAULT_VARIOMETER_PASSWORD_4											"your_PASSWORD_for SSID4"   

**Passage en mode Wifi**

Au démarrage, appuyer sur le bouton gauche

Dès que le Gnuvario-E est connecté au réseau Wifi, l'adresse IP de la page Web s'affiche sur l'écran :

**Connection à la page Web**

Dans votre navigateur Web, connectez-vous avec l'adresse IP indiquée.



