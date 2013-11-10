#######
Brewery
#######


Brewery class is the representation of a brewery in BrewBox. This is the central object for accessing equipments, sensors actuators and data.

.. image:: /images/CD_Brewery.png
    :align: center

Attributes
==========

* *Name* : a short descriptive name for the brewery
* *Description* (optional): a longer description for the brewery
* *Status* : Status of the brewery. Value can be one of :

  * ACTIVE : Active status points the brewery being used by BrewBox for monitoring and controling.
  * INACTIVE : Status used for breweries known by BrewBox but not currently in use for monitoring or control. 
  * PLANNED : Status for breweries being configured.
  * RETIRED : Status used for breweries not used anymore.
* *StartDate* : Date when the brewery has been used for the first time

Rules
=====

BrewBox can manage several breweries but only one can be used (ie. monitored or controled) at the same time. There can be therefore several instances of Brewery class but only with ``status==ACTIVE``.