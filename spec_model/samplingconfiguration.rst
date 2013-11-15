======================
SamplingConfiguration
======================

SamplingConfiguration class holds configuration attributes used by BrewBox to compute :doc:`sensors </spec_model/sensor>` scheduling. Sampling configuration can be `basic`, `interval based` or `cron-based`. 

.. image:: /images/CD_SamplingConfiguration.png
    :align: center

SamplingConfiguration
#####################

SamplingConfiguration is an abstract class holding configuration attributs common to all sampling methods. 

Attributes
----------

* *Lifetime* : Sampling lifetime. Values can be :

  * FOREVER : sampling will occur since BrewBox is started and until it shutdowns
  * BATCH : sampling will occur only during brewing batchs.

IntervalSamplingConfiguration
#############################

Attributes
----------

CronBasedSamplingConfiguration
##############################

Attributes
----------
