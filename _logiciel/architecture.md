---
step: 1
description: Architecture
---

Voici la description générale du logiciel du Gnuvario-E

Pour fonctionner le Gnuvario-E a besoin d'un firmware et d'une carte SD avec une organisation particulière

**Le Firmware**      
   
Il existe plusieurs versions de firmware qui correspondent aux différentes versions d'écran et aux versions beta ou stable
   
-- Les versions pour l'écran 1,54''     --

la version {% include lienfichier.md name="Stable" lien="update/Gnuvario154.bin" %}     
la version de {% include lienfichier.md name="Développement" lien="update/Gnuvario154b.bin" %}     

-- Les versions pour l'écran 2.90'' en paysage   --

la version {% include lienfichier.md name="Stable" lien="update/Gnuvario290.bin" %}      
la version de {% include lienfichier.md name="Développement" lien="update/Gnuvario290b.bin" %}     

-- Les versions pour l'écran 2.90'' en portrait   --

la version {% include lienfichier.md name="Stable" lien="update/Gnuvario291.bin" %}    
la version de {% include lienfichier.md name="Développement" lien="update/Gnuvario291b.bin" %}       

**La carte SD**     

La carte SD embarque un site web et des fichiers de configuration. Il existe une arborescence pour la version stable et une pour la version beta

RootSD pour la version {% include lienfichier.md name="Stable du Firmware" lien="fichier/RootSD_Stable.zip" %}     
RootSD pour la version {% include lienfichier.md name="Beta du Firmware" lien="fichier/RootSD_Beta.zip" %}    

**Le dossier www**     

Sur la carte SD, le dossier www contient les fichiers nécessaires au fonctionnement du site web embarqué. Il existe une version pour la version stable et une pour la version beta.

-- Les versions pour l'écran 1,54''     --
   
www pour la version {% include lienfichier.md name="Stable du Firmware" lien="dl-web/Gnuvario154" %}     
www pour la version {% include lienfichier.md name="Beta du Firmware" lien="dl-web/Gnuvario154b" %}    

-- Les versions pour l'écran 2.90'' en paysage   --   
   
www pour la version {% include lienfichier.md name="Stable du Firmware" lien="dl-web/Gnuvario290" %}     
www pour la version {% include lienfichier.md name="Beta du Firmware" lien="dl-web/Gnuvario290b" %}    

-- Les versions pour l'écran 2.90'' en portrait   --    

www pour la version {% include lienfichier.md name="Stable du Firmware" lien="dl-web/Gnuvario291" %}     
www pour la version {% include lienfichier.md name="Beta du Firmware" lien="dl-web/Gnuvario291b" %}    

**Le dossier AGL**

Sur la carte SD, le dossier ALG contient les fichiers nécessaires au fonctionnement de l'affichage de l'altitude sol.
{% include logicielimg.md name="AGL.jpg" %}
[Téléchargement ici](https://vps.skybean.eu/agl/)
