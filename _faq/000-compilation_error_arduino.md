---
description: Erreur lors de la compilation du code dans l'IDE Arduino
---

- Il faut que le dossier Arduino par défaut (sous Windows, *Documents/Arduino*) ne contienne que les fichiers du projet Gnuvario ; en fait, deux dossiers : 
  - *Gnuvario-E* : contient Gnuvario-E.ino
  - *libraries* : les librairies du projet, et uniquement celles-ci.
- Il faut démarrer le vario avec l'interrupteur et sans la sdcard, avant de le raccorder au PC par l'USB.
- Dans le menu *Outils* de l'IDE Arduino, la carte choisie doit être *ESP32 Dev Module*, la partition scheme  *Minimal SPIFFS (1,9 MB APP with OTA / 180 KB SPIFFS)*, et le port COM celui correspondant au vario.

Voir [la documentation dédiée]({{ site.baseurl }}/5-code.html)