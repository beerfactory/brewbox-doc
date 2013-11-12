#######
Brewery
#######


Brewery class is the representation of a brewery in BrewBox. This is the central object for accessing equipments, sensors, actuators and data.

.. image:: /images/CD_Brewery.png
    :align: center

Attributes
==========

* *Name* : a short descriptive name for the brewery
* *Description* : a longer description for the brewery (optional)
* *StartDate* : Date when the brewery has been used for the first time

Relations
=========

* *Equipments* : a list of :doc:`equipments` describng the brewery composition.
* *Brewer* : link to the home :doc:`brewer <brewer>` using the brewery.

Rules
=====

BrewBox can manage several breweries but only one can be used (ie. monitored or controled) at the same time. There can be therefore several instances of Brewery class but only with ``status==ACTIVE``.