.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Ordered List         |                      |                      |
   +======================+======================+======================+
   | `Prev <nar           | Chapter 3. Modelling |  `Next <orderi       |
   | y-relation.html>`__  | Patterns             | ng-relation.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Ordered List
               :name: ordered-list
               :class: title

   *How do we specify an ordering over a collection of resources?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Sometimes ordering is an important aspect of some collection of
      data. E.g. the list of authors associated with an academic paper,
      or the placings on a scoreboard. RDF offers a several different
      ways to capture ordering across some portion of a graph.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use an ``rdf:List`` to describe a ordered list of resources.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      .. code:: programlisting


         <http://www.example.com/docs/1> ex:authors (
            <http://www.example.com/author/joe>
            <http://www.example.com/author/bob>
           ).

         <http://www.example.com/author/joe> 
           foaf:name "Joe".

         <http://www.example.com/author/bob> 
           foaf:name "Bob".

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      RDF offers several modelling options for defining collections of
      resources. Formally these are the RDF Containers (Sequence, Bag,
      and Alternates) and the RDF Collections (List). For this purposes
      of this pattern an RDF Sequence and an RDF List are very similar:
      both describe an ordered list of resources. Semantically the two
      structures differ in that a sequence is open ended (i.e. other
      members may exist, but aren't itemized) while a list is closed
      (i.e. the members are complete).

      In practice though there is no real difference between the
      structures as data cannot be easily merged into an existing
      sequence, e.g. to append values. Both also suffer from being
      poorly handled in SPARQL 1.0: there is no way to query or
      construct an arbitrary sized list or sequence without extensions;
      SPARQL 1.1 property paths will remedy the querying aspects.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Repeated Property <repeated-property.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <nar           | `Up <modelli         |  `Next <orderi       |
   | y-relation.html>`__  | ng-patterns.html>`__ | ng-relation.html>`__ |
   +----------------------+----------------------+----------------------+
   | N-Ary Relation       | `Ho                  |  Ordering Relation   |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
