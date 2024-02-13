# K3NG_rotor
Yet another K3NG rotator controler pcb

This implementation is based on an Arduino Mega board and a pair of 4x relay boards to drive an AZ-EL antenna system.

Most basic functions are directly driven via Molex KK 254 connectors (up/down, right/left, lcd display output, GPS input, *
I2C extensions... etc). All other "vacant" gpio could be used via solderpads. 

Board could be powered from 8 to 15V 

Source code and wiki should be downloaded at 

https://github.com/k3ng/k3ng_rotator_controller

![K3NG rotator, component side](https://github.com/F6ITU/K3NG_rotor/blob/main/Pictures/IMG_20240113_153802.jpg)


![K3NG rotator, bottom side](https://github.com/F6ITU/K3NG_rotor/blob/main/Pictures/IMG_20240113_154300.jpg)

# Notes de montage

* Les barrettes de contact au pas de 2,54 doivent être soudées après les avoir insérées dans les connecteur gpio de l’Arduino. La série de brasure doit donc être effectuée avec le module MCU en place, lequel servira ainsi de gabarit d’alignement pour les broches. Sans cette précaution, il sera quasiment impossible d’installer l’Arduino sur la carte. 

* Le régulateur de tension doit être le circuit à souder avant tout autre composant. Les deux principaux condensateurs de filtrage sont très proche du 7805 et gêneraient la brasure ce celui-ci s’il était monté a posteriori

* Tous les connecteurs Molex kk254 ne sont pas nécessairement à installer. C’est le cas notamment des entrées gpio « serial » de 0 à 3, qui peuvent être remplacés par de simples jumpers les reliant aux sorties des périphériques installés. Cela permet de choisir sur quel port seront reliés les modules  gps ou Nextion s’il y a lieu

* Toutes les E/S de l’Arduino sont doublées par une rangée de contacts au pas de 2,54, laissant libre toute possibilité d’ajouts de modules exotiques. 

* Les modules « 4 relais » disponibles sur Amazon ou AliExpress sont généralement livrés avec un connecteur « broches  carte à fils » au pas de 2,54mm orientés vers le dessus de la carte. Il est nécessaire de les dessouder et de les remplacer par un connecteur identique, mais soudé « coté piste ». Le shield K3NG doit, pour sa part, être équipé d’un connecteur femelle « carte à carte » pour recevoir la ou les cartes relais en « piggy back ». 

* Deux cartes relais peuvent être installées pour piloter une paire de moteurs azimut/élévation. Prévoir deux entretoises d’une hauteur équivalente aux connecteurs de liaison. 

* ATTENTION : les relais sont commandés « 2 à 2 », soit pour assurer une coupure courants forts, soit pour être utilisés en inverseur (un contact ouvert et un contact fermé au repos, et lycée de Versailles au travail). Cette configuration est notamment nécessaire pour commander les rotor Kantronic/Yaesu/Toyomura d’ancienne génération (split phase ou à phase divisée)

 * Une BOM interactive est disponible sur ce Github dans le répertoire BOM du même métal
