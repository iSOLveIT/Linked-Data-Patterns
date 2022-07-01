.. container:: navheader

   +----------------------+----------------------+----------------------+
   | N-Ary Relation       |                      |                      |
   +======================+======================+======================+
   | `Prev <multi-lingu   | Chapter 3. Modelling |  `Next <o            |
   | al-literal.html>`__  | Patterns             | rdered-list.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: N-Ary Relation
               :name: n-ary-relation
               :class: title

   *How can a complex relation, involving several resources, be modelled
   as RDF?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      An RDF triple expresses a relationship between at most two
      resources. However some relationships are not binary and involve
      the equal participation of several different resources. This is
      most common in the case of events, where the event is a relation
      between several resources, e.g. a Purchase is an n-ary
      relationship between a Person, a Product, and a Seller. All of
      those participants are key to the relationship.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create a class for the relationship, and create instances of that
      resource to relate together the other resources that are involved
      in the relation.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      .. code:: programlisting


         ex:bob a foaf:Person.
         ex:mary a foaf:Person.
         ex:conferenceCentre a ex:Building.
         ex:legoinc a foaf:Organization.

         _:event1 a ex:Conference;
           dc:title "Lego Hack Day";
           ex:organizer ex:mary;
           ex:attendee ex:bob;
           ex:sponsor ex:legoinc;
           ex:location ex:conferenceCentre.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The N-ary Relation pattern is similar to the `Qualified
      Relation <qualified-relation.html>`__ pattern as both involve the
      same basic solution: modelling a relationship as a resource rather
      than a property. They differ in their context. In the Qualified
      Relation pattern the desire is to annotate a relationship between
      two resources, whereas in the N-ary Relation pattern the goal is
      to represent a complex relation between several resources.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Qualified Relation <qualified-relation.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Defining N-ary Relations on the Semantic
            Web <http://www.w3.org/TR/swbp-n-aryRelations/>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <multi-lingu   | `Up <modelli         |  `Next <o            |
   | al-literal.html>`__  | ng-patterns.html>`__ | rdered-list.html>`__ |
   +----------------------+----------------------+----------------------+
   | Multi-Lingual        | `Ho                  |  Ordered List        |
   | Literal              | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
