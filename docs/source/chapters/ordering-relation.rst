.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Ordering Relation    |                      |                      |
   +======================+======================+======================+
   | `Prev <or            | Chapter 3. Modelling |  `Next <pref         |
   | dered-list.html>`__  | Patterns             | erred-label.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Ordering Relation
               :name: ordering-relation
               :class: title

   *How can we specify an ordering relationship between two or more
   resources?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Ordering is important in many data models. Often that ordering can
      be implicit in the properties of resources, e.g. publication dates
      of Articles. In some cases the ordering needs to be more explicit,
      describing a fixed ordering relationship between the resources,
      e.g. a sequence of events, or stops on a delivery route.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create ordering properties, e.g. "previous" and "next", for
      specifying the relationship between the ordered resources.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The following example describes the bus route, consisting of a
      number of bus stops. A stop may be preceeded by a previous stop
      and may be followed by another stop. Custom relations have been
      defined to identify the previous and next relationships between
      the bus stops.

      .. code:: programlisting


         ex:bus10 a ex:Bus;
            ex:route ex:stop1.

         ex:stop1 a ex:BusStop;
           ex:number 1;
           ex:nextStop ex:stop2.

         ex:stop2 a ex:BusStop;
           ex:number 2;
           ex:previousStop ex:stop1;
           ex:nextStop ex:stop2.

         ex:stop3 a ex:BusStop;
           ex:number 3;
           ex:previousStop ex:stop2.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      RDF provides several ways to implicitly and explicitly defining
      ordering in a dataset. Resources often have literal properties
      that implicitly define an ordering relationship between resources.
      E.g. time stamps on events, publication dates, or in the above
      example the numbers of each of the bus stops. Application code can
      use a query to extract this implicit ordering from the date.
      However its otherwise not defined in the model.

      Another, more explicit way to define order is by using an RDF
      collection to create an `Ordered List <ordered-list.html>`__.
      Using an Ordered List, the above example could have been expressed
      as:

      .. code:: programlisting


         ex:bus10 a ex:Bus;
            ex:route ( ex:stop1 ex:stop2 ex:stop3 ).

      Lists are useful when there is no explicit relationship between
      the resources in the ordered collection. The above example has
      lost the fact that Bus Stop 2 is preceeded by Bus Stop 1, other
      than their arrangement in a list. An application could still
      discover this relation using a query, but this can be difficult,
      and is certainly less explicit than the original example.

      An ordering relation provides an explicit relationship between the
      ordered resources; in effect the ordering relations define a
      linked list that connects the resources together. Ordering
      relations are also simple to query and manipulate. For example, it
      would be very simple to adjust the ordered relation approach to
      modelling a bus route to add an extra stop, whereas the list based
      approach is more difficult as the entire list needs to be re-built
      requiring more changes to the graph.

      The trade-offs between using an Ordering Relation versus an
      Ordered List depends on the specific data model. Continuing the
      above example, if the ordering of stops is generally fixed, then
      it is appropriate to using an Ordering Relation. However, if new
      bus routes are constructed by selecting from the available bus
      stops then an Ordered List may be more appropriate as there is no
      longer a fixed relationship between the stops.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Ordered List <ordered-list.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Defining N-ary Relations on the Semantic
            Web <http://www.w3.org/TR/swbp-n-aryRelations/#pattern2>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <or            | `Up <modelli         |  `Next <pref         |
   | dered-list.html>`__  | ng-patterns.html>`__ | erred-label.html>`__ |
   +----------------------+----------------------+----------------------+
   | Ordered List         | `Ho                  |  Preferred Label     |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
