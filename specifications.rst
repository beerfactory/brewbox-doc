##############
Specifications
##############

Content :

* the first part of this documentation describes the `context`_ in which BrewBox can help.
* second part addresses the description of the `functional requirements`_ BrewBox must meet.
* last part describes `non functional requirements`_ which must be satisfied by BrewBox in order to be implemented by any hobbyist having some time and a minimum of knwoledge in electronic and computing.

.. note::

   BrewBox are not *set in stone*. Any comments or improvement proposals are welcome.

Context
========

BrewBox tries to answer the need, which comes in every home brewer's mind, of monitoring and controling a micro brewery. Usually, main reasons for that are :

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

En première approche, le diagramme suivant présente les cas d'utilisation de BrewBox dans le contexte du brassage amateur. Les paragraphes suivants décriront chaque cas d'utilisation afin d'en faire apparaitre les fonctionnalités détaillées.


.. image:: images/UseCaseDiagram.png
    :align: center

Collect data from sensors
-------------------------

Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des grandeurs physiques essentielles au brassage telles que la température du moût, la température de la cuve d'ébullition ou encore la consommation électrique.

Control actuators
-----------------

Monitor brewing process
-----------------------

Run batch
---------

Setup batch
-----------

Configure interfaces with sensors/actuators
-------------------------------------------



Non functional requirements
===========================

.. Non-functional requirements describe what the system must be

.. topic:: Qu'est-ce qu'un capteur ?

  Les capteurs installés dans une pico-brasserie ont pour rôle de mesurer des grandeurs physiques essentielles au brassage telles que la température du moût, la température de la cuve d'ébullition ou encore la consommation électrique. Il s'agit en général de capteurs électriques qui diffèrent selon de la grandeur physique mesurée, leur précision et la méthode de mesure. Ils se différencient également par les caractéristiques du signal électrique produit en réponse à un changement de la grandeur physique mesurée. Les capteurs peuvent donc être classés en plusieurs catégories :

  + les **capteurs passifs** sont des capteurs dont les caractéristiques électriques varient significativement lorsque la grandeur physique mesurée varie. Cette variation peut être captée par une mesure de courant et/ou de tension et convertie en information. La `thermistance <http://fr.wikipedia.org/wiki/Thermistance>`_ est un exemple de capteur passif: sa résistance varie en fonction de la température. Cette variation peut-être mesurée par la chute de tension créée aux bornes de la termistance.
  + les **capteurs actifs** sont des capteurs qui produisent un signal électrique en réponse à une variation de la grandeur physique mesurée. Ce signal peut être capté et convertie en information.

    + *capteurs analogiques*
    + *capteurs numériques*
