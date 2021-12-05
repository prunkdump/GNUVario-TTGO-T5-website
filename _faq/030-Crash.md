---
description: Mon vario plante de manière aléatoire. 
---

Nous avons identifié plusieurs situations entrainant des plantages aléatoires du vario. 

**1. Liste des debugs:**{: style="color:   #138ca2; opacity: 1;" }

Ne décommentez que les lignes `#define PROG_DEBUG` et `#define DATA_DEBUG` dans le fichier `Arduino\libraries\VarioLog\DebugConfig.h`


{% highlight shell_session %}
#define ENABLE_DEBUG

#if defined(ENABLE_DEBUG)

//              DEBUGING MODE
#define PROG_DEBUG			  //debug principal program
//#define HARDWARE_DEBUG
//#define IMU_DEBUG			  //debug IMU
//#define CAL_DEBUG
//#define I2CDEV_SERIAL_DEBUG   //debug I2Cdev
//#define DEBUG_SERIAL_NMEA_1
//#define SCREEN_DEBUG
//#define SCREEN_DEBUG2
//#define GPS_DEBUG
//#define BUTTON_DEBUG
//#define TONEDAC_DEBUG
//#define MS5611_DEBUG
//#define KALMAN_DEBUG
//#define ACCEL_DEBUG
//#define EEPROM_DEBUG
//#define NMEAPARSER_DEBUG
//#define SDCARD_DEBUG
//#define IGC_DEBUG
#define DATA_DEBUG
//#define BT_DEBUG
//#define WIFI_DEBUG
//#define SOUND_DEBUG
//#define AGL_DEBUG
//#define SQL_DEBUG
//#define BEARING_DEBUG
//#define TWOWIRESCH_DEBUG
//#define POWER_DEBUG
//#define MEMORY_DEBUG
{% endhighlight %}


**2. Réduire la vitesse du Bus I2C:**{: style="color:   #138ca2; opacity: 1;" }

Le problème qui remonte le plus souvent est une perte de l'information d'altitude. Le module CJMCU-117 qui intègre le baromètre MS5611 communique avec la puce ESP32 avec le protocole [I2C](https://fr.wikipedia.org/wiki/I2C). Vous pouvez essayer de réduire la vitesse de communication du BUS en la passant de 400Khz à 100Khz. 
Pour ce faire, modifiez la valeur `400000UL` par `100000UL` de la ligne 355 du fichier `Arduino\libraries\HardwareConfig\HardwareConfigESP32.h`  

{% highlight shell_session %}
/* Set the freq */
#define VARIO_TW_FREQ 400000UL

en

/* Set the freq */
#define VARIO_TW_FREQ 100000UL

{% endhighlight %}

**3. Qualité des soudures:**{: style="color:   #138ca2; opacity: 1;" } 

Il arrive bien souvent que les soudures soient la cause des bugs, même si elles paraissent correctes. Essayez de repasser un coup de fer à souder sur les broches du circuit imprimé.

