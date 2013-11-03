######
Notes
######

Dimensionnement
---------------

Volumétrie des données collectées
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Le nombre de mesures à traiter dépend de:

+ du nombre de capteurs à interroger
+ de la fréquence de collecte des mesures

A titre d'exemple, la collecte des données d'un capteur de température toutes les 5 secondes produira 12 mesures par minute ou encore 720 mesures par heure.

La volumétrie (en terme d'occupation mémoire) est directement liée à la taille de la structure de données utilisée pour stocker les mesures.

Taille d'un horodatage en python::

>>> import sys
>>> from datetime import datetime
>>> print(sys.getsizeof(datetime.now()))
>>> 48

Estimation de la taille d'une donnée : 10 octets maxi

=> On arrive à 58 octets mini par mesure, donc 696 octets par minutes ou 41760 octets par heure

