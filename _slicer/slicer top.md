---
step: 3
title: Boîtier3D
description: Boîtier supérieur
---
[Télécharger le profil]({{ 'assets/fichiers/profils3Dprinter/Geeetech_A20M_boitier_haut.fff' | relative_url }})

Pour créer un bel arrondi des bords, l'idéal est d'imprimer le boîtier supérieur en couches de 0.1mm. Mais afin de réduire le temps d'impression et avoir une meilleure accroche des premières couches, nous allons créer plusieurs étapes d'impression.
Nous allons également voir comment créer et optimiser les supports pour les enlever facilement.

{% include slicerimg.md name="top 1.jpg" %}

# **Générer et optimiser l'impression des supports:**


Ouvrir les fenêtres "Vue en section transversale" et "Support de génération". Mettez 1mm à "Résolution de support" et 40° à "Angle de surplomb maximal". Ensuite, créez les supports en appuyant sur "Générer des supports automatiques"

{% include slicerimg.md name="top 2.jpg" %}

Mettez vous ensuite en vue de dessus puis réglez l'axe Z de la section transversale à 7mm. Vous allez pouvoir enlever les supports dans les trous de vis en appuyant sur "supprimer les supports actuels" et en cliquant sur chaque bâtonnet dans les trous.  

{% include slicerimg.md name="top 3.jpg" %}

Il reste maintenant à optimiser les supports dans l'encoche du haut parleur. Réglez la vue du boîtier pour bien voir les supports puis enlever les supports comme sur l'image ci-dessous (clic gauche de la souris pour la rotation de l'image, clic droit pour la translation). Ils seront ainsi bien plus facile à enlever.


{% include slicerimg.md name="top 4.jpg" %}


## **Gestion des process**
   
L'idée est de découper l'impression en plusieurs tranches en changeant de réglages selon la hauteur. 

Dans cet exemple, nous avons 3 process. 
 
## **Process1:**

Il s'agit ici de régler les premières couches afin qu'elles accrochent bien au plateau. 

**Onglet "Extrudeuse":** 

La distance et la vitesse de rétractation dépendront de votre imprimante. L'élévateur vertical de rétractation permet de soulever un peu la buse après une rétractation et éviter ainsi de venir toucher la pièce lors d'un mouvement.  

{% include slicerimg.md name="top 5.jpg" %}

**Onglet "Couche"**

Nous commençons par des couches de 0.2mm pour cette pièce. Avec une hauteur de première couche à 150%, la première couche sera de 0.3mm. Une vitesse de 20% par rapport à la vitesse globale d'impression permet une bonne accroche des supports. 

{% include slicerimg.md name="top 6.jpg" %}

**Onglet "Addition"**

Ajout d'une jupe autour de la pièce, histoire de bien purger la buse.

{% include slicerimg.md name="top 7.jpg" %}

**Onglet  "Remplissage":**

Au choix, ici 40% de matière et un remplissage rectiligne. 

{% include slicerimg.md name="top 8.jpg" %}

**Onglet "Support"**

Paramètres importants pour cette pièce!

Choisissez 15% de remplissage  toutes les 1 couche. C'est le remplissage par défaut des supports. Pour augmenter la surface des supports juste avant l'impression du boîtier, mettez 4 couches de support denses avec un pourcentage de remplissage de 30%.
Dans la partie "Distance avec la pièce", choisissez 0.5mm de décalage horizontal depuis la pièce (les supports ne toucheront pas la pièce sur le plan horizontal), "couche de séparation verticale supérieure" de 2 (les supports ne seront plus imprimés deux couches avant l'impression du boîtier et seront vraiment plus facile à décoler!) et 1 couche de séparation verticale inférieure.
 

{% include slicerimg.md name="top 9.jpg" %}
{% include slicerimg.md name="top 14.jpg" %}

**Onglet "Température"**

Mêmes réglages que le boîtier inférieur. Plateau 60°, extrudeur 215°


**Onglet "Refroidissement"**

Mêmes réglages que le boîtier inférieur.


**Onglet "G-Code"**

Mêmes réglages que le boîtier inférieur.

**Onglet "Scripts"**

Mêmes réglages que le boîtier inférieur.

**Onglet "Vitesse"**

Pour maximiser les chances de réussite, les premières couches seront imprimées à une vitesse de 40mm/s

{% include slicerimg.md name="top 11.jpg" %}

**Onglet "Autre"**

Mêmes réglages que le boîtier inférieur.

**Onglet "Avancés"**

C'est dans cette fenêtre que l'on choisira la hauteur d'impression sur laquelle sera appliquée chaque process. Dans notre cas, dans la fenêtre "Modification de couche", nous commençons le process 1 à 0mm et le terminons à 0,7mm. Vous pouvez laisser les autres valeurs comme pour le boîtier inférieur.

{% include slicerimg.md name="top 13.jpg" %}

## **Process 2**

Pour ajouter un nouveau process, il vous suffit de cliquer sur "ajouter". Le process précédent sera dupliqué et vous n'aurez plus qu'à le modifier.


Dans ce deuxième process, nous appliquerons les même réglages que le process 1 mis à part la vitesse d'impression qui sera changée de 40mm/s à 60mm/s. La hauteur de la couche principale sera toujours de 0,2mm mais on changera la hauteur de la couche principale de 150% à 100%.
Dans l'onglet "Avancés", les hauteurs d'impression seront modifiées de manière à commencer à 0,7mm (fin du process 1) et finir à 5.9mm

## **Process 3**

Dans ce troisième process, nous reprendrons les même réglages que le process 2 hormis la hauteur des couches qui passera de 0,2mm à 0,1mm. La courbure du boîtier sera ainsi plus finement imprimée. Dans l'onglet "Avancés", les hauteurs d'impression seront modifiées pour commencer à 5,9mm et pour finir, vous pouvez décocher la case "Stopper l'impression à la hauteur".







