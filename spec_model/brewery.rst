#######
Brewery
#######


Brewery class is the representation of a brewery in BrewBox. This is the central object for accessing equipments, sensors actuators and data.


Class diagram
=============

Attributes
==========

* *name* : 
* *description* : 
* *status* : active, inactive, planned or retired

Rules
=====

BrewBox can manage several breweries but only one can be used at the same time. There can be therefore several instances of Brewery class but only with ``status==active``.