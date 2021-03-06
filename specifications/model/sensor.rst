======
Sensor
======

Sensor class is used for storing characteristics of sensors used in :doc:`breweries <brewery>`.

.. yuml::
    :align: center
    :style: plain

    [Equipment]1-*>[Sensor|name;description;status{bg:cyan}]
    [Sensor]1-1>[SamplingConfiguration]
    [Sensor]1-1>[ConversionConfiguration]

Attributes
==========

=================  =========================================================================================
Field              Description
=================  =========================================================================================
name 			   Short descriptive name for the sensor
description 	   Longer description for the sensor (optional)
status			   Current status of the sensor in the brewery. Can be one of :

				   * ``PLANNED`` : sensor is defined in BrewBox but not yet fitted in the brewery equipment
				   * ``INSTALLED`` : sensor is fitted in brewery but doesn't provide any information yet
				   * ``ACTIVE`` : sensor is active and ready for collecting data
			 	   * ``DISABLED`` : sensor is disabled for some reason and can't be used for collecting data
				   * ``UNREACHABLE`` : sensor is supposed to be active but not signals can be read by BrewBox.
=================  =========================================================================================

Relations
=========

* :doc:`SamplingConfiguration <samplingconfiguration>` : link to the sampling configuration used for this sensor.
* :doc:`ConversionConfiguration <conversionconfiguration>` : link to the conversion configuration used for this sensor.

Rules
=====

All status can be set manually by the user. Some status can also be set automatically by BrewBox :

* UNREACHABLE is set by BrewBox when some problem occurs when collecting data
* DISABLED is set by BrewBox when to many errors occurs when collecting data. Some user action is necessary to reset sensor status.

DISABLED sensors are not processed by BrewBox during sampling process.