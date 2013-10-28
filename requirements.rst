########################
Requirements
########################

BrewBox aims at helping home brewers in monitoring and controling a micro brewery. `Functional requirements`_ section describes features needed by the system to achieve this goal. `Non-functional requirements`_ describes requirements the system must meet in order to operate in home environment by hobbyist.

Functional requirements
=======================

.. Functional requirements describes what the system is supposed to *do*.

The diagram below shows the use-cases covered by BrewBox in the home brewing process. Next sections details each uses-case scenarios and requirements.

.. image:: images/UseCaseDiagram.png
    :align: center

Collect sensors data
--------------------

Sensors are electric equipments fitted in a micro brewery used to measure physical quantities like mash temperature, boiling water or electric power consumption. Sensors differs depending on the physical quantity measured, precision or measurement method. They also differs from the electric signals produced in response to physical quantity change which can be of different types:

+ *Passive sensors* are sensors which electric characteristic varies significantly when some physical quantity varies. This variation can be measured by current or voltage drop and converted.

Thermistor are resistor which resistance caries with the temperature.
+ *Active sensors*
  + analog sensors
  + digital sensors


Control actuators
-----------------

Monitor brewing process
-----------------------

Run batch
---------

Setup brewing batch
-------------------

Configure interface with sensors/actuators
------------------------------------------



Non-functional requirements
===========================

.. Non-functional requirements describes what the system is supposed to *be*.
