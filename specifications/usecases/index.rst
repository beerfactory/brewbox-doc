#############
Use cases
#############

.. toctree::

  collect_data


.. image:: /images/UseCaseDiagram.png

Home brewer activities
----------------------

     [Brewer]-(Setup batch)
     [Brewer]-(Monitor brewing process)
     [Brewer]-(Configure brewery equipements)
     (Monitor brewing process)>(Collect data from sensors{bg:beige})
     (Monitor brewing process)>(Control actuators{bg:beige})

 :doc:`Home brewer <model/brewer>` uses BrewBox for :

 * configuring BrewBox system in order to operate sensor and actuators fitted in its home brewery;
 * setting up batch steps and characteristics in order to build a batch program;
 * monitoring brewing process in order to compare actual and planned characteristics. This activity which includes:

   * :doc:`collecting data from sensors <usecases/collect_data>` for monitoring purposes;
   * controling actuators for follow batch program.


Brewery activities
------------------

     [Brewery]-(Run batch)
     (Run batch)>(Collect data from sensors{bg:beige})
     (Run batch)>(Control actuators{bg:beige})

 :doc:`Brewery <model/brewery>` is used by BrewBox in activites which involve brewery sensors or actuators. This happen when running a batch program setup by the :doc:`Home brewer <model/brewer>` which includes:

 * :doc:`collecting data from sensors <usecases/collect_data>` for monitoring purposes;
 * controling actuators for follow batch program.
