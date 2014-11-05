##############
Specifications
##############

.. toctree::
   :hidden:

   intro
   usecases/index

Brewbox specifications are divided into several documents :

* an :doc:`introduction <intro>` describing the context in which BrewBox can help.
* a description of :doc:`use-cases <usecases/index>` and other `functional requirements`_ achieved by BrewBox.
* a reference :doc:`class model <classmodel>`.
* a description of `non functional requirements`_ which must be satisfied by BrewBox to meet any hobbyist knowledge and capacity.

.. note::

   BrewBox requirements are *not set in stone* and specification documentation is *not exhaustive*. Any comments or improvement proposals are welcome.


Class model
============

Here is a list of class used in the specification model :

.. toctree::
  :maxdepth: 2

  model/index


.. _non-functional-requirements:

Non functional requirements
===========================

.. Non-functional requirements describe what the system must be

..
  .. topic:: Qu'est-ce qu'un capteur ?

  Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des
  grandeurs physiques essentielles au brassage telles que la température du
  moût, la température de la cuve d'ébullition ou encore la consommation
  électrique. Il s'agit en général de capteurs électriques qui diffèrent selon
  de la grandeur physique mesurée, leur précision et la méthode de mesure. Ils
  se différencient également par les caractéristiques du signal électrique
  produit en réponse à un changement de la grandeur physique mesurée. Les
  capteurs peuvent donc être classés en plusieurs catégories :

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
