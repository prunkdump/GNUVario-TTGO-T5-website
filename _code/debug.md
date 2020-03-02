---
step: 7
description: Le debug
---

Ce chapitre va décrire les méthodes de debuggage utilisées dans le code du Gnuvario-E

Avec le temps, le système d'affichage des informations de debuggage à évolué 

Il existe aujourd'hui 3 methodes implémentées dans le code du Gnuvario-E

**La méthode 1**

L'utilisation du fichier DebugConfig.h et des println     
      
#define ENABLE_DEBUG  
     
#define PROG_DEBUG			  //debug principal program       
      
ENABLE_DEBUG permet d'activer le debuggage.     
     
Ensuite pour chaque type d'information à tracer on commente ou non les define.       
Les messages s'affiche sur le moniteur série en ajoutant des lignes dans le code    

#ifdef SCREEN_DEBUG     
    SerialPort.print("Created task: Executing on core ");     
    SerialPort.println(xPortGetCoreID());    
#endif //SCREEN_DEBUG     


**La méthode 2**

La méthode 2 utilise aussi le fichier DebugConfig.h mais l'affiche est enrichie du nom
du fichier source, du nom des variables et de la ligne   
     
Au début de chaque fichier source il faut déclarer l'utilisation des fonctions de débug     

#include <DebugConfig.h>       
       
#ifdef NMEAPARSER_DEBUG      
#define ARDUINOTRACE_ENABLE 1       
#else      
#define ARDUINOTRACE_ENABLE 0      
#endif       
     
#define ARDUINOTRACE_SERIAL SerialPort      
#include <ArduinoTrace.h>       

Ensuite il  sera possible d'utiliser les fonctions :     

TRACE();        
Affiche sur le moniteur série le numéro de ligne, le nom du fichier   
      
DUMP(someValue);       
Affiche sur le moniteur série la variable ainsi que le fichier et la ligne      
      
SDUMP(someText);         
Affiche sur le moniteur série le texte ainsi que le fichier et la ligne       
       
**La méthode 3**
             
La méthode 3 enregistre les informations de débuggage dans le fichier variolog.log    
Le fichier debug.cfg décrit dans la section "configuration" est utilisé pour selectionner 
les messages à afficher    
          
Il faudra utiliser la librairie variolog.h     

Les fonctions possibles sont :       

TRACELOG(type, module)       
Enregistre dans le fichier de log le fichier et la ligne     

DUMPLOG(type, module, variable)         
Enregistre dans le fichier de log la variable, le fichier et la ligne        

MESSLOG(type, module, Text)             
Enregistre dans le fichier de log un message avec le fichier et la ligne        

INFOLOG(Text)                            
Enregistre dans le fichier de log un texte      
                                                                                                    

