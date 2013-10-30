##############
Spécifications
##############

BrewBox vise à répondre aux besoins de contrôle et d'automatisation d'une pico-brasserie et donc du processus de brassage. Après avoir rappelé le `contexte`_ du projet, la section `spécifications fonctionnelles`_ aborde la description des fonctionnalités que doit implémenter BrewBox pour satisfaire ce besoin. La section `spécifications non fonctionnelles`_ aborde ensuite les exigences que doit satisfaire le système afin de pouvoir être mise en oeuvre par tout amateur disposant d'un peu de temps et quelques connaissances en informatique et électronique.

.. note::

   Les spécifications de BrewBox ne sont pas *figées dans le marbre*. Tous les commentaires, remarques ou propostions d'améliorations sont les bienvenus.

Contexte
========

.. note::

 Brassage amateur => construction d'une pico-brasserie
 Amélioration de la qualité => Besoin de contrôler le processus de brassage
 Principes du DIY => composants standards + bricolage de base

Spécifications fonctionnelles
=============================

.. Les spécifications fonctionnelles décrivent ce que le système doit faire

En première approche, le diagramme suivant présente les cas d'utilisation de BrewBox dans le contexte du brassage amateur. Les paragraphes suivants décriront chaque cas d'utilisation afin d'en faire apparaitre les fonctionnalités détaillées.


.. image:: images/UseCaseDiagram.png
    :align: center

Collecter les données des capteurs
----------------------------------

Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des grandeurs physiques essentielles au brassage telles que la température du moût, la température de la cuve d'ébullition ou encore la consommation électrique.

Contrôler les actionneurs
-------------------------

Surveiller le processus de brassage
-----------------------------------

Exécuter un brassin
-------------------

Configurer un brassin
---------------------

Configurer l'interface avec les capteurs/actionneurs
-------------------------------------------------------



Spécifications non fonctionnelles
=================================

.. Les spécifications non fonctionnelles décrivent ce que le système doit être

.. topic:: Qu'est-ce qu'un capteur ?

  Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des grandeurs physiques essentielles au brassage telles que la température du moût, la température de la cuve d'ébullition ou encore la consommation électrique. Il s'agit en général de capteurs électriques qui diffèrent selon de la grandeur physique mesurée, leur précision et la méthode de mesure. Ils se différencient également par les caractéristiques du signal électrique produit en réponse à un changement de la grandeur physique mesurée. Les capteurs peuvent donc être classés en plusieurs catégories :

  + les **capteurs passifs** sont des capteurs dont les caractéristiques électriques varient significativement lorsque la grandeur physique mesurée varie. Cette variation peut être captée par une mesure de courant et/ou de tension et convertie en information. La `thermistance <http://fr.wikipedia.org/wiki/Thermistance>`_ est un exemple de capteur passif: sa résistance varie en fonction de la température. Cette variation peut-être mesurée par la chute de tension créée aux bornes de la termistance.
  + les **capteurs actifs** sont des capteurs qui produisent un signal électrique en réponse à une variation de la grandeur physique mesurée. Ce signal peut être capté et convertie en information.

    + *capteurs analogiques*
    + *capteurs numériques*

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
48

Estimation de la taille d'une donnée : 10 octets maxi

=> On arrive à 58 octets mini par mesure, donc 696 octets par minutes ou 41760 octets par heure

