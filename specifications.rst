##############
Specifications
##############

Content :

* First part of this documentation describes the `context`_ in which BrewBox can help.
* Second part addresses the description of the `functional requirements`_ BrewBox must meet.
* Last part describes `non functional requirements`_ which must be satisfied by BrewBox in order to be implemented by any hobbyist having some time and a minimum of knwoledge in electronic and computing.

.. note::

   BrewBox are not *set in stone*. Any comments or improvement proposals are welcome.

Context
========

BrewBox tries to answer the need, which comes to the mind of every brewer, of monitoring and controling a micro brewery. Usually, main reasons for that are :

* being able to ensure a constant quality of the beer produced
* improving brew process efficiency as quantities produced increase.

Monitoring usually means adding some sensors, mostly for temperature control during mash and boiling steps. Controling requires more components for building control panel with displays, switches or PID controller. Finally complete automation requires professional equipements like programmable logic controller, which is not something affordable for every hobbyist.
All theses steps also requires good knowledge in electronic and electricity to deal with components from small temperature probes to 5500W heater for example.

The goal of BrewBox is to help brewers achieve this goal by providing a system :

* flexible enough to fit any configurations of brewery equipements with sensors
* offering a large set of features for monitoring, controling and automate the brewery activity.

Functional requirements
=======================

.. Functional requirements describe what the system must do

BrewBox functional requirements can be described through several use cases represented on this diagram :

.. image:: images/UseCaseDiagram.png
    :align: center

The following sections describe each use case in details and will therefore introduce BrewBox concepts and highlight main features.

Actors
------

Use cases
---------

Collect data from sensors
^^^^^^^^^^^^^^^^^^^^^^^^^

Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des grandeurs physiques essentielles au brassage telles que la température du moût, la température de la cuve d'ébullition ou encore la consommation électrique.

Control actuators
^^^^^^^^^^^^^^^^^


Monitor brewing process
^^^^^^^^^^^^^^^^^^^^^^^

Run batch
^^^^^^^^^

Setup batch
^^^^^^^^^^^


Configure interfaces with sensors/actuators
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^



Non functional requirements
===========================

.. Non-functional requirements describe what the system must be

..
  .. topic:: Qu'est-ce qu'un capteur ?

  Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des grandeurs physiques essentielles au brassage telles que la température du moût, la température de la cuve d'ébullition ou encore la consommation électrique. Il s'agit en général de capteurs électriques qui diffèrent selon de la grandeur physique mesurée, leur précision et la méthode de mesure. Ils se différencient également par les caractéristiques du signal électrique produit en réponse à un changement de la grandeur physique mesurée. Les capteurs peuvent donc être classés en plusieurs catégories :

  + les **capteurs passifs** sont des capteurs dont les caractéristiques électriques varient significativement lorsque la grandeur physique mesurée varie. Cette variation peut être captée par une mesure de courant et/ou de tension et convertie en information. La `thermistance <http://fr.wikipedia.org/wiki/Thermistance>`_ est un exemple de capteur passif: sa résistance varie en fonction de la température. Cette variation peut-être mesurée par la chute de tension créée aux bornes de la termistance.
  + les **capteurs actifs** sont des capteurs qui produisent un signal électrique en réponse à une variation de la grandeur physique mesurée. Ce signal peut être capté et convertie en information.

    + *capteurs analogiques*
    + *capteurs numériques*


..
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