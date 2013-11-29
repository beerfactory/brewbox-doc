##############
Specifications
##############

This documentation is divided into four parts :

* `context`_ in which BrewBox can help. 
* description of `functional requirements`_ achieved by BrewBox. 
* description of `class model`_ used in these specifications.
* description of `non functional requirements`_ which must be satisfied by BrewBox to meet any hobbyist knowledge and capacity.

.. note::

   BrewBox requirements are *not set in stone* and specification documentation is *not exhaustive*. Any comments or improvement proposals are welcome.

Context
========

BrewBox tries to answer the **need of monitoring and controling** a micro brewery. Usually, brewers motivations are :

* being able to ensure a constant quality of the beer produced.
* improving brew process efficiency as quantities produced increase.

Monitoring is usually achieved by fitting the micro brewery with sensors, mostly for temperature follow-up during mash and boiling steps. Controling requires more components and knowledges for building control panel with displays, switches or PID controller. Finally complete automation may require professional equipments like programmable logic controller and good knowledge in electronic and electricity.

The goal of BrewBox is to help home brewers to achieve this goal by providing a system :

* flexible enough to fit with sensors any configurations of brewery equipements.
* offering a large set of features for monitoring, controling and automate the brewery activity.

Functional requirements
=======================

.. Functional requirements describe what the system must do

BrewBox functional requirements are described through :doc:`use cases <usecases/index>` representing activities available to BrewBox users.


Home brewer activities
----------------------

.. yuml::
    :align: center
    :type: usecase
    :style: plain

    [Brewer]-(Setup batch)
    [Brewer]-(Monitor brewing process)
    [Brewer]-(Configure brewery equipements)
    (Monitor brewing process)>(Collect data from sensors{bg:beige})
    (Monitor brewing process)>(Control actuators{bg:beige})

:doc:`Home brewer <model/brewer>` uses BrewBox for :

* configuring BrewBox system in order to operate sensor and actuators fitted in its home brewery;
* setting up batch steps and characteristics in order to build a batch program;
* monitoring brewing process in order to compare actual and planned characteristics. This activity which includes:

  * :doc:`collecting data from sensors <usecases/collect_data>` for monitoring purposes;
  * controling actuators for follow batch program.


Brewery activities
------------------

.. yuml::
    :align: center
    :type: usecase
    :style: plain

    [Brewery]-(Run batch)
    (Run batch)>(Collect data from sensors{bg:beige})
    (Run batch)>(Control actuators{bg:beige})

:doc:`Brewery <model/brewery>` is used by BrewBox in activites which involve brewery sensors or actuators. This happen when running a batch program setup by the :doc:`Home brewer <model/brewer>` which includes:

* :doc:`collecting data from sensors <usecases/collect_data>` for monitoring purposes;
* controling actuators for follow batch program.


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