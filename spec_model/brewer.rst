######
Brewer
######

Brewer is used for storing personal information concerning the brewer, user of the brewery.

.. image:: /images/CD_Brewer.png
    :align: center

Attributes
==========

* *FirstName* : Brewer first name
* *LastName* : Brewer last name
* *Email* : Brewer email, which can be used to send automatic email notifications
* *PhoneNumber* : Brewer phone number, which can be used to send automatic SMS notifications (if available)
* *Language* : Brewer prefered language
* *Country* : Brewer country location

Relations
=========

* *Brewery* : link to the :doc:`brewery <brewery>` owned and managed by BrewBox.

Rules
=====

FirstName, LastName and Email are mandatory.