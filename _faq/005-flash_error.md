---
description: Erreur lors du flashage
---

- Démarrer le vario avec l'interrupteur, avant de le raccorder au PC par la prise USB, puis lancer l'opération de compilation / flashage.
- Si ceci ne fonctionne pas : démarrer le vario juste au moment le flashage va démarrer, que ce soit avec l'IDe Arduino, l'IDE PlatformIO, ou le 'Flash tools'.

Par exemple, avec l'**IDE Arduino** : 
attendre la ligne "Linking everything together...", puis allumer le vario. 
Il est même possible d'attendre le message "le port série sélectionné n'existe pas ou votre Arduino n'est pas connectée _____....._____....." pour allumer le vario.

autre exemple, avec **PlatformIO** : 
attendre la ligne "Linking .pio\build\esp32dev\firmware.elf", puis allumer le vario. 
Il est même possible d'attendre le message "Connecting........_____....._" pour allumer le vario.
