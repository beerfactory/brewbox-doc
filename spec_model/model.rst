############
Object model
############

This section contains documentation for model classes used along the project :doc:`specifications </specifications>`.

.. yuml::
    :align: center
    :style: plain
    :scale: 80

    [Brewer|FirstName;LastName;Email;PhoneNumber;Language;Country]1-1>[Brewery|Name;Description;Status;StartDate]
    [Brewery]<>-*>[Equipement|Name;Description]
    [Equipement]1-*>[Sensor|Name;Description;Status]
    [Equipement]1->[<<enum>>;EquipmentType]
    [Sensor]1->[<<enum>>;SensorType]
    [Sensor]1-*>[Sample|Timestamp;Rawdata]
    [Sensor]1-1>[SamplingConfiguration]
    [Sensor]1-1>[ConversionConfiguration]

.. image:: /images/ClassDiagram.png
    :align: center

Model classes
=============

.. toctree::
  :maxdepth: 1
  
  brewer
  brewery
  sensor
  samplingconfiguration