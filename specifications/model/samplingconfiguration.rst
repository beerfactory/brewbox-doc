======================
SamplingConfiguration
======================

SamplingConfiguration class holds configuration attributes used by BrewBox to compute :doc:`sensors <sensor>` scheduling. Sampling configuration can be `basic`, `interval based` or `cron-style`. 

.. yuml::
    :align: center
    :style: plain

    [SamplingConfiguration|start]^-[IntervalSamplingConfiguration|interval;unit]
    [SamplingConfiguration]^-[CronStyleSamplingConfiguration|year;month;day;week;day_of_week;hour;minute;second]

SamplingConfiguration
#####################

SamplingConfiguration is an abstract class holding configuration attributes common to all sampling methods. 

Attributes
----------

=================  =========================================================================================
Field              Description
=================  =========================================================================================
start              Sensor sampling lifetime. Value can be :

                   * FOREVER : sampling will occur once BrewBox is started and never stop until it shutdowns
                   * BATCH : sampling will occur only during brewing batchs.
=================  =========================================================================================

IntervalSamplingConfiguration
#############################

IntervalSamplingConfiguration holds configuration attributes for interval sampling. Interval sampling is a basic sampling method where samples are taken on repeated intervals.

Attributes
----------

=================  =========================================================================================
Field              Description
=================  =========================================================================================
interval	         Sampling interval value
unit               Interval value unit. Value can be:

                   * ``second``
                   * ``minute``
                   * ``hour``
                   * ``day``
                   * ``week``
                   * ``month``
                   * ``year``
=================  =========================================================================================

Rules
-----

Example : An IntervalSamplingConfiguration instance with Interval=5 and Unit=MINUTE will setup a sensor sampling every 5 minutes.


CronStyleSamplingConfiguration
##############################

CronStyleSamplingConfiguration allows to setup sampling configuration based on `cron-style expressions <http://apscheduler.readthedocs.org/en/latest/cronschedule.html>`_.

Attributes
----------

=================  =========================================================================================
Field              Description
=================  =========================================================================================
year               4-digit year number
month              month number (1-12)
day                day of the month (1-31)
week               ISO week number (1-53)
day_of_week        number or name of weekday (0-6 or mon,tue,wed,thu,fri,sat,sun)
hour               hour (0-23)
minute             minute (0-59)
second             second (0-59)
=================  =========================================================================================

Rules
-----

Sampling will occur every time the time and date match the cron expression given by the attributes values.