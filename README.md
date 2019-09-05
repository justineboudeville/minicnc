# MINICNC, tutoriel
---

# Hello world! ㋡

    name: Justine Boudeville
    job: Graphic Designer
    date: 04/09/2009 
    


### PREMIER TEST MANUEL :
![Capture d’écran 2019-09-05 à 11 52 21](https://user-images.githubusercontent.com/54895357/64331800-c0ba6180-cfd3-11e9-9b52-30a5128ebc4c.png)


### PREMIER TEST NUMERIQUE (avec application encre argenté) :
![IMG_20190904_141643](https://user-images.githubusercontent.com/54895357/64332190-666dd080-cfd4-11e9-9578-620307a98cad.jpg)

### INTRODUCTION : 
« La machine outil à commande numérique » CNC ou « computer numerical control » en anglais est une machine-outil dotée d'une commande numérique assurée par un ordinateur. La fonction d’usinage est déterminée par un programme, qui commande les déplacements des outils sur la masse à usiner. Il définit l’axe de rotation de la fraise en fraisage, et l’axe de rotation de la pièce en tournage. La machine, une fraiseuse à trois ou cinq axes, est entièrement automatisée et contrôlée par ordinateur.

### CONTEXTE :
Création de tampons dans le cadre du workshop BOOM Festival par le collectif fais le toi-même.
Création personnalisée de drapeaux à envoyer dans le monde. 
### OBJECTIFS : 
Apprendre le processus d’impression sur tampon.
Manipuler le tampon, l’encre, et avoir un rendu net.
Communiquer par le biais d’un langage graphique à travers le monde. 

### MATERIEL :
- Carré de linogravure
- Encrier
- Inkscape
- Extension g-code
- Extension EggBot
- CNC

_Un autre tutoriel qui m'a bien aidé!_
[tutoriel, gcode](http://wiki.funlab.fr/index.php/Gcode_avec_Inkscape)


### Commençons! ☺

#### 1. Ouvrir Inkscape.

#### 2. S’assurer que la dimension du fichier est  ≤ sur la masse à usiner.

![Capture d’écran 2019-09-05 à 11 54 09](https://user-images.githubusercontent.com/54895357/64331894-e8a9c500-cfd3-11e9-8a42-43f1d33fc81b.png)

Ici la surface du carré de lino est de 75 x 75 mm + Vérifier l’échelle (notamment quand on importe un fichier SVG dans Inkscape)

#### 3. Mettre un contour de différentes couleurs pour chaque objet.


#### 4. Vérifier que les  objets soient en chemin, objet vectoriel. « Chemin → Objet en chemin ».
![Capture d’écran 2019-09-05 à 11 54 41](https://user-images.githubusercontent.com/54895357/64331934-f8290e00-cfd3-11e9-9987-384dbc2b44af.png)  
Combiner les chemins (Ctrl+K) si votre design en comporte plusieurs.

#### 6. Mettre l’illustration en effet miroir (uniquement pour l’usage de tampon).
#### 7. Le rayon de l"outil.

Ajuster les contours de votre dessin, par rapport au rayon de l'outil. Ici 1 mm, pour venir enlever la matière avec une mèche universelle. Je mets donc le contour de ma forme à 1 mm.
_Pour une mèche en V, c'est un peu plus casse-tête! Cette dernière me sert ici, pour nettoyer ma forme, que j'utilise en dernier. Voir plus bas l'explication_

#### 8. Extension EggBot
Télécharger l'extension ⬇️
[extension eggbot](https://console.cloud.google.com/storage/browser/tuto_minicnc/EggBot_extensions_v281/)
Ici, nous allons nous servir de la focntion Hatchfill.
Cocher la case "Connect nearby ends?" 
Cela vas générer un chemin avec des noeuds, ce qui permettra de gagner du temps. La fraiseuse vas faire qu'un seul tracé. 

#### 9. Extension G-Code
Les versions d'Inkscape 0.91 et ultérieures disposent nativement de cette extension, traduite en français par "programmation de commande numérique".
Dans le cas contraire, voici le fichier ⬇️

#### 10. Les points d’orientations
Sous Inkscape, sans sélectionner votre dessin, lancer « Extensions → Programmation de commande numérique → Points d’orientation... ». Il s’agit de choisir les origines pour gérer les déplacements de l’outil selon le tracé de votre dessin.
Laissez tous les réglages par défaut et indiquez une valeur pour « Profondeur sur l’axe Z ».
Ici, il consiste à graver d’une profondeur de 1 mm un parapluie dans du lino d’épaisseur 3 mm, (et de surface 750 x 750 mm).
Choisir donc « Profondeur sur l’axe Z : 1 »
Appliquer
Les points de coordonnées apparaissent. 
Ne touchez pas celui du (0.0 ; 0.0 ; 0.0), et positionnez l’autre coordonnée de fait qu’il soit sur la partie droite

#### 11. La blibliothèque d'outils

Le cadre est modifiable avec l’outil texte. 
Changez vos paramètres selon votre design et outil. 

- diameter (diamètre de l’outil en mm) 
- feed (vitesse d’avance horizontale de l’outil en mm/min.) 
- penetration feed (vitesse de pénétration de l’outil dans le matériau en mm/min.) 
- depth step (profondeur de passe en mm) ;

#### 12. Générer le code
« Extensions → Programmation de commande numérique → Chemin vers G-code... »
Renommer fichier + Indiquez l’emplacement du code
Remplacer par .ngc (pour que la machine du lac puisse lire le code)

#### SUR LA MACHINE : 
