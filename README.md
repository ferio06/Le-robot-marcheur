# Le-robot-marcheur

D'abord il faut commencer par importer nos fichier depuis repertoir du site github, et pour cela on va commencer par créer les répertoires par les commandes suivantes :
```
mkdir catkin_ws
cd catkin_ws
mkdir src
cd src
https://github.com/ferio06/Le-robot-marcheur.git
```
Après on procède par l'installation de MoveIt, pour cela ouvrir un terminal
et taper : 
```
sudo apt-get install ros-melodic-moveit
```
Une fois que c'est fait, il faudra maintenant lancer le build des packages qu'on vient de télécharger,pour cela ouvrir un terminal dans le repertoire catkin_ws et lancer la commande : 
```
catkin build
source devel/setup.bash
```

Pour lancer l'urdf pour une jambe de notre robot de notre package "urdf_robot" appelé "jambe_urdf.launch" on lance la commande :
```
roslaunch urdf_robot jambe_urdf.launch
```

Pour lancer le package qui nous permet controller les mouvements de cette jambe de notre robot par le package "udm_project_moveit_configs" crée par le service :
```
roslaunch moveit_setup_assistant setup_assistant.launch
```
On lance la commande :
```
roslaunch udm_project_moveit_config demo.launch
```

Pour visualisé le robot après l'ajout des autres jambes qu'on a crée avec le package nommé "urdf_quad_complet" où il y a
l’urdf qu’on a nommé "piedcomplet.urdf" contenant l’ensemble des membres ainsi que la base_link de notre robot marcheur :
```
r o sl a u n c h u dm p r o j e c t c o n t r ol demo . l aunch
```
On laisse le service se lancer puis on ouvre un autre terminale dans le même dossier catkin_ws afin de lancer le service pour le package udm_hand_control pour le contrôl des mouvents de la main robot par cinematique direct et indirect que l'on lancera à partir des commandes :
```
roslaunch udm_hand_control direct.launch
```
```
roslaunch udm_hand_control indirect.launch
```


