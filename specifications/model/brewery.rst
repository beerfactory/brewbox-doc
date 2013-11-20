#######
Brewery
#######


Brewery class is the representation of a brewery in BrewBox. This is the central object for accessing equipments, sensors, actuators and data.

.. yuml::
    :align: center
    :style: plain
    :scale: 80

    [Brewery|Name;Description;Status;StartDate]

Attributes
==========

* *Name* : a short descriptive name for the brewery
* *Description* : a longer description for the brewery (optional)
* *StartDate* : Date when the brewery has been used for the first time

Relations
=========

* *Equipments* : a list of :doc:`equipments` describing the brewery composition.
* *Brewer* : link to the home :doc:`brewer <brewer>` using the brewery.

Rules
=====

BrewBox can monitor and control only one brewery. There can only exist one instance of Brewery class. 