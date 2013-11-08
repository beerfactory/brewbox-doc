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

Collecting data from sensors process is based on `sampling sensors signal <Sensors sampling>`_ at regular interval and `converting these samples <Signal conversion>`_ into an information representing some physical quantity. Some special cases may require `sampling interruption <Interruptions management>`_ in order to convert some signal as a priority. In both cases data generated during this process are stored and available for further use.

.. note::

   The way signals are physically sampled depend on sensors type and is addressed in the :ref:`non functionnal requirements <non-functional-requirements>` section.

Sensors sampling
----------------

Signal conversion
-----------------

Interruptions management
------------------------

