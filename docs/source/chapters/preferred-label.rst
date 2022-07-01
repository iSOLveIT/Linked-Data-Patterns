.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Preferred Label      |                      |                      |
   +======================+======================+======================+
   | `Prev <orderin       | Chapter 3. Modelling |  `Next <qualifi      |
   | g-relation.html>`__  | Patterns             | ed-relation.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Preferred Label
               :name: preferred-label
               :class: title

   *How can a simple unambiguous label be provided for a resource?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      There are many different RDF properties that can be used for
      expressing a label, including generic properties such as
      rdfs:label and more domain specific labels such as foaf:name. This
      presents a variety of choices to the data provider, and can be
      confusing for application authors.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use ``skos:prefLabel`` to publish the preferred display label for
      a resource

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      A library system publishes Linked Data about authors. The
      preferred mechanism for specifying author names is using a
      normalized form, e.g Surname, First Name. This preferred label can
      be specified using ``skos:prefLabel``, but the authors full name,
      and part names can be published using properties from FOAF. A
      simple Linked Data browser may use the preferred label, whereas an
      Address Book application browsing the same data may choose to
      assemble display labels according to user defined preferences,
      e.g. First Name, Surname.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The ``skos:prefLabel`` property, whilst defined in the SKOS
      ontology, is a general purpose property that identifies the
      preferred label for a resource. By standardising on this property
      for labelling data providers and consumers can converge on a
      common mechanism for expressing labels of resources.

      Having a single preferred property for display labels encourages
      convergence but doesn't preclude the use of more specific
      properties for other purposes. For example the literal value of
      the ``skos:prefLabel`` property can be formatted for display,
      leaving other properties, e.g. ``rdfs:label``, ``foaf:name``, etc
      to express alternatives or variations in labels or naming. A
      client that is aware of the meaning of specific predicates may
      choose to build labels using alternate logic, but having a label
      unambiguously specified simplifies application development.

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <orderin       | `Up <modelli         |  `Next <qualifi      |
   | g-relation.html>`__  | ng-patterns.html>`__ | ed-relation.html>`__ |
   +----------------------+----------------------+----------------------+
   | Ordering Relation    | `Ho                  |  Qualified Relation  |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
