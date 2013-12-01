#########################
Collect data from sensors
#########################

This documentation describes how BrewBox collects signals from sensors fitted in a micro brewery and converts them into data usable for monitoring and control.

Use case description
====================

Collecting data from sensors is a process based on `sampling sensors signal <Sensors sampling>`_ at regular interval and `converting these samples <Signal conversion>`_ into information representing some physical quantity. Some special cases may require `sampling interruption <Interruptions management>`_ in order to convert and process some signal as a priority. In both cases data generated during this process are stored and available for further use.

.. note::

   The way signals are physically sampled depends on sensors types and electronic circuitry configuration. This problematic is addressed in the :ref:`non functionnal requirements <non-functional-requirements>` section.

Sensors sampling
----------------

BrewBox maintains a list of :doc:`sensors </specifications/model/sensor>` fitted in :doc:`equipements </specifications/model/equipment>` composing the :doc:`brewery </specifications/model/brewery>`. Each sensor is associated with a sampling configuration describing how and when sampling may occur :

.. yuml::
    :align: center
    :style: plain
    :scale: 80

    [Brewery|Name;Description;Status;StartDate]<>-*>[Equipement|Name;Description]
    [Equipement]1-*>[Sensor|Name;Description;Status]
    [Sensor]1-1>[SamplingConfiguration]
    [Sensor]1-1>[ConversionConfiguration]

At startup, BrewBox reads the sampling configuration for all active sensors (ie. sensor instances with Status==ACTIVE).

Signal conversion
-----------------

Interruptions management
------------------------

Preconditions
=============

Data collection starts once the sensors fitted in the brewery are *on* and connected to BrewBox system.

Postconditions
==============

Data collections runs in background throughout the brewing process, until sensors are switched *off*.
