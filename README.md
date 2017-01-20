# MICTCP
MICTCP est une implémentation de TCP qui permet de paramétrer un taux de pertes admissibles dans le but de transporter de la vidéo de façon fluide.

## Principe
TCP intègre un mécanisme de reprise des pertes, l'implémentation MICTCP permet de choisir un taux de reprise des pertes ce qui signifie que tous les paquets ne seront pas renvoyés. Ceci permet le transport vidéo en évitant les "freeze", certaines frames sont perdues mais globalement la vidéo est lue de façon fluide.

## Démonstration
### Paramétrage
Le présent programme intègre une simulation de perte de paquets sur la boucle local. Le taux de perte est paramétrable avec la macro `LOSS_RATE`. Le taux de perte admissible est donné par la macro `ADMISSIBLE_LOSS_RATE`.

### Exécution
1. Compiler le programme avec `make`
2. Lancer le programme puits :
  * `./tsock_texte -p` pour échanger des données textuelles
  * `./tsock_video -p -t (tcp|mictcp) pour de la vidéo  (`-t` définit le protocole à utiliser pour la transmission)
3. Lancer le programme source :
  * `./tsock_texte -s` pour échanger des données textuelles
  * `./tsock_video -s -t (tcp|mictcp) pour de la vidéo  (`-t` définit le protocole à utiliser pour la transmission)

### Vidéo
Une vidéo de démonstration est téléchargeable ici : http://etud.insa-toulouse.fr/~girardi/reseau/video.bin. Créez un dossier `video` à la racine du projet et placez la dedans.

## Auteurs 
Guilhem Cichocki (https://github.com/gcichocki)  // Alexis Girardi
