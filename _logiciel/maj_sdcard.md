---
step: 4
description: Mise à jour via la SDcard
---

Le logiciel (firmware) du Gnuvario peut être mis à jour depuis la carte SD.  
Voici la procédure.

Il faut bien sûr se procurer en préalable ce firmware ; soit depuis le site du Gnuvario, soit en compilant soi-même les sources.

Ce fichier doit être recopié sur la racine de la carte SD, avec le nom **update.bin** ; voici un exemple de contenu de la carte SD après cette recopie, en mode wifi :

{% include logicielimg.md name="sdcardWithUpdate.bin.jpg" %}

Au prochain redémarrage, le Gnuvario va détecter la présence de ce fichier update.bin, et se mettre à jour à partir de ce code ; le message 'upgrade en cours' va s'afficher à l'écran pendant le processus de mise à jour (environ une minute).

{% include logicielimg.md name="upgradeBySDcard.jpg" %}

Ensuite, le Gnuvario va redémarrer automatiquement et se mettre en fonctionnement normal.

**A noter** : à la fin du processus de mise à jour, le fichier **update.bin** est automatiquement supprimé.