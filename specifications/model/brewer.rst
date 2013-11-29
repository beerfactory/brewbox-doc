######
Brewer
######

Brewer is used for storing personal information concerning the brewer, user of the brewery.

.. yuml::
    :align: center
    :style: plain

    [Brewer|first_name;last_name;email;phone_number;language;country]1-1>[Brewery]

Attributes
==========

=================  =========================================================================================
Field              Description
=================  =========================================================================================
first_name		   Brewer first name (mandatory)
last_name*		   Brewer last name (mandatory)
email 			   Brewer email (mandatory), which can be used to send automatic email notifications 
phone_number	   Brewer phone number, which can be used to send automatic SMS notifications (if available)
language		   Brewer prefered language
country			   Brewer country location
=================  =========================================================================================

Relations
=========

* *Brewery* : link to the :doc:`brewery <brewery>` owned and managed by BrewBox.
