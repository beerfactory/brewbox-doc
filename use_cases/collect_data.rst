#########################
Collect data from sensors
#########################

This use case describes how BrewBox collects signals coming from sensors fitted in a micro brewery and converts them into data usable for monitoring and control.

Preconditions
=============

Data collection starts once the sensors fitted in the brewery are *on* and connected to BrewBox system.

Postconditions
==============

Data collections runs in background throughout the brewing process, until sensors are switched *off*.

Use case description
====================

Collecting data from sensors process is based on `sampling sensors signal <Sensors sampling>`_ at regular interval and `converting these samples <Signal conversion>`_ into information representing some physical quantity. Some special cases may require `sampling interruption <Interruptions management>`_ in order to convert some signal as a priority. In both cases data generated during this process are stored and available for further use.

.. note::

   The way signals are physically sampled depends on sensors types and is addressed in the :ref:`non functionnal requirements <non-functional-requirements>` section.

Sensors sampling
----------------

BrewBox maintains a list of sensors fitted in the :doc:`brewery`. Each sensor is defined by the following attributes:

.. TODO : Add an class diagram showing relation between brewery and sensors

.. image:: images/TODO.png
    :align: center


* *name* : a short descriptive name for the sensor
* *description* : a longer description for the sensor (role, placement, etc.)
* *type* : type of sensor
* *status* :
* *physical address* : 

Signal conversion
-----------------

Interruptions management
------------------------

