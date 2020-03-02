---
step: 2
title: Boîtier3D
description: Boîtier inférieur
---

[Télécharger le profil]({{ 'assets/fichiers/profils3Dprinter/Geeetech_A20M_boitier_bas.fff' | relative_url }})

Une fois votre fichier chargé dans simplify3d, vous allez pouvoir changer les paramètres du profil pour optimiser l'impression.

{% include slicerimg.md name="Bottom_1.jpg" %}


**Onglet "Extrudeuse":** 

La distance et la vitesse de rétractation dépendront de votre imprimante. L'élévateur vertical de rétractation permet de soulever un peu la buse après une rétractation et éviter ainsi de venir toucher la pièce lors d'un mouvement.  

{% include slicerimg.md name="Bottom 2.jpg" %}

**Onglet "Couche"**

Pour cette pièce, des couches de 0.2mm sont un bon compromis entre vitesse et qualité d'impression. Avec une hauteur de première couche à 150%, la première couche sera de 0.3mm. Une vitesse de 20% par rapport à la vitesse globale d'impression permet une bonne accroche, notamment des tours de vis et sangles. 

{% include slicerimg.md name="Bottom 3.jpg" %}

**Onglet "Addition"**

Ajout d'une jupe autour de la pièce, histoire de bien purger la buse.

{% include slicerimg.md name="Bottom 4.jpg" %}

**Onglet  "Remplissage":**

Au choix, ici 40% de matière et un remplissage en nid d'abeille. 

{% include slicerimg.md name="Bottom 5.jpg" %}

**Onglet "Support"**

Pas nécessaire pour cette pièce. Vous pouvez décocher la case. 

{% include slicerimg.md name="Bottom 6.jpg" %}

**Onglet "Température"**

Vous règlerez ici la température d'extrusion du PLA (Shared Heater, ici 215°C) et la température du plateau chauffant (Heated Bed, ici 60°C)

{% include slicerimg.md name="Bottom 7.jpg" %}

**Onglet "Refroidissement"**

Avec du PLA, laissez les valeurs par défaut: première couche sans ventilateur, couche suivante, ventilateur à 100%.

{% include slicerimg.md name="Bottom 8.jpg" %}

**Onglet "G-Code"**

Si vous souhaitez utiliser le profil téléchargeable en haut de page, vous pouvez ici modifier les caractéristiques de votre imprimante (cartésien, delta, volume d'impression etc)

{% include slicerimg.md name="Bottom 9.jpg" %}

**Onglet "Scripts"**

Gardez les scripts par défaut de votre imprimante.

{% include slicerimg.md name="Bottom 10.jpg" %}

**Onglet "Vitesse"**

La vitesse d'impression dépend de la qualité mécanique de votre imprimante. A 60mm/s, il ne devrait pas y avoir de problème.

{% include slicerimg.md name="Bottom 11.jpg" %}

**Onglet "Autre"**

Réglez la taille de votre filament, prix, densité....

{% include slicerimg.md name="Bottom 12.jpg" %}

**Onglet "Avancés"**

Comportement de paroi mince: laissez "Périmètre seulement" et "Autoriser le remplissage des espaces". 

{% include slicerimg.md name="Bottom 13.jpg" %}



