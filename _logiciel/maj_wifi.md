---
step: 5
description: Mise à jour par Wifi
---

Le logiciel (firmware) du Gnuvario peut être mis à jour en mode Wifi ; soit en le téléchargeant directement sur Internet, soit en le téléchargeant depuis l'ordinateur.

Pour cela, il faut démarrer le vario en mode Wifi ; voir ['le manuel']({{ site.baseurl }}/manuel/wifi.html)

Il faut choisir le menu 'Mise à jour' ; la page web va indiquer la version courante, et proposer une mise à jour, soit par Internet, soit en local :

{% include logicielimg.md name="updateByWifi.jpg" %}

### Mise à jour depuis Internet

Deux options possibles : installer une version béta (version de développement), ou une version stable.  
Cliquer sur l'option désirée ; le firmware sera alors automatiquement téléchargé depuis l'Internet vers le vario.  
Une fois le téléchargement terminé, le Gnuvario va se mettre à jour, puis redémarrer avec la nouvelle version.

**A Noter :** les pages du site web embarqué (se trouvent sur la carte SD, dossier /www) sont également mises à jour lors de cette opération.

### Mise à jour locale

Il faut sélectionner le fichier firmware en cliquant sur le bouton 'parcourir' ; puis le télécharger sur le vario en cliquant sur le bouton 'Envoyer'.  
Le Gnuvario va se mettre à jour à partir de ce fichier, puis redémarrer.

**A Noter :** lors de cette opération, seul le firmware du Gnuvario est mis à jour.  
Il faut penser, ensuite, à mettre à jour manuellement le dossier /www de la carte SD.