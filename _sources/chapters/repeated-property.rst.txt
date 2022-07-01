.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Repeated Property    |                      |                      |
   +======================+======================+======================+
   | `Prev <reified       | Chapter 3. Modelling |  `Next <top          |
   | -statement.html>`__  | Patterns             | ic-relation.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Repeated Property
               :name: repeated-property
               :class: title

   *How can properties that have multiple values be expressed?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      A resource may have multiple values for a specific property. E.g.
      a set of keywords associated with a research paper. RDF offers
      several options for modelling these multi-valued relations.
      Sometimes these multi-valued relations have an explicit ordering
      that should be preserved in the data, e.g. the order of authors.
      In other cases an explicit ordering is not required

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Simply repeat the property of the resource multiple times.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      For example a research paper may have multiple keywords. The
      ordering of these keywords is not important, so using the Dublin
      Core subject property, we can express this multi-valued relation
      as:

      .. code:: programlisting


         _:doc 
           dc:subject "RDF"; 
           dc:subject "Semantic Web".

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Repeating properties is the simplest approach to handling
      multi-valued relations. The alternatives all have their downsides.
      One alternative would be to use a structured value for the
      literal, e.g:

      .. code:: programlisting


         _:doc dc:subject "RDF, Semantic Web".

      But structured values limit the ability for applications to query
      for specific data items, e.g. documents that have a specific
      keyword. With a structured value a regular expression would be
      required to test for the values in the literal.

      Another alternative would have been to use an RDF Container
      (Sequence, Bag, or Alt) or Collection (RDF List). Some of these
      structures imply ordering (Sequence, List) while others (Bag, Alt)
      don't imply an ordering over their members. This means that the
      keywords could have been expressed as:

      .. code:: programlisting


         _:doc dc:subject ( "RDF", "Semantic Web" )

      There are several downsides to using Containers and Collections.
      Firstly they can be difficult to use as they can be hard to query.
      Secondly, when combining data from different sources the
      Containers and Collections won't be merged together to create a
      single structure; the lists will remain separate.

      On the whole, the simplest way to express multi-valued relations
      is to use a simple Repeated Property. Collections and Containers
      are best used only when ordering is significant.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Ordered List <ordered-list.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <reified       | `Up <modelli         |  `Next <top          |
   | -statement.html>`__  | ng-patterns.html>`__ | ic-relation.html>`__ |
   +----------------------+----------------------+----------------------+
   | Reified Statement    | `Ho                  |  Topic Relation      |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
