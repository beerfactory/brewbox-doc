#########################
Collect data from sensors
#########################

This use case describes how BrewBox collects signals from sensors fitted in a micro brewery and converts them into data usable for monitoring and control.

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

BrewBox maintains a list of :doc:`sensors </spec_model/sensor>` fitted in the :doc:`equipements </spec_model/equipment>` composing the :doc:`brewery </spec_model/brewery>`. Each sensor is associated with a sampling configuration describing how and when sampling may occur :

.. TODO : Add an class diagram showing relation between brewery and sensors

.. image:: /images/CD_BrewerySensorsList.png
    :align: center

At startup, BrewBox reads the sampling configuration for all active sensors (ie. sensor instances with Status==ACTIVE).

Signal conversion
-----------------

Interruptions management
------------------------

