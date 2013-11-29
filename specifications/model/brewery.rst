#######
Brewery
#######


Brewery class is the representation of a brewery in BrewBox. This is the central object for accessing equipments, sensors, actuators and data.

.. yuml::
    :align: center
    :style: plain

    [Brewer]1-1>[Brewery|name;description;start_date;status{bg:cyan}]
    [Brewery]<>-*>[Equipment]

Attributes
==========

=================  =========================================================================================
Field              Description
=================  =========================================================================================
name			   Short descriptive name for the brewery
description 	   Longer description for the brewery (optional)
start_date		   Date when the brewery has been used for the first time
status			   Brewery status. Can be something like *idle*, *running batch*, *running fermentation*, ...
=================  =========================================================================================

Relations
=========

* *Equipments* : a list of :doc:`equipments` describing the brewery composition.
* *Brewer* : link to the home :doc:`brewer <brewer>` using the brewery.

Rules
=====

BrewBox can monitor and control only one brewery. There can only exist one instance of Brewery class. 