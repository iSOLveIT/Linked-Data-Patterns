.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Index Resources      |                      |                      |
   +======================+======================+======================+
   | `Prev <custo         | Chapter 3. Modelling |  `Next <label        |
   | m-datatype.html>`__  | Patterns             | -everything.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Index Resources
               :name: index-resources
               :class: title

   *How can ordered collections or indexes be published as RDF?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      It is often the case that a web application will provide its users
      with a number of alternative ways to navigate. This might be an
      A-Z list of resources, or a list ordered based on creation date or
      "interestingness". These collections are useful resources in their
      own right that should be published as Linked Data.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create resources for each "index" and associate the index with the
      items that it contains. An rdf:List or rdf:Seq is best used here
      as these structured include the notion of ordering that is an
      essential aspect of an index.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The BBC /music website publishes an A-Z list of artists. But this
      does not use a sequence to indicate ordering.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      By creating separate resources and links between these indexes and
      their contents we avoid the need to publish the algorithms that
      are used to generate the indexes, we can instead allow machines to
      navigate the collection just as a human user would do. This
      approach is particularly useful to ensure that data can be crawled
      by a semantic web search engine.

      If a collection may be unmanageably large, then it can be
      decomposed into smaller groupings. E.g. a large A-Z index may be
      decomposed into smaller collections: A-C, D-F, etc.

      By using an rdf:List or rdf:Seq to order the association between
      the index and its contents we retain the notion of ordering. Where
      the index is a permanent collection, with all contents known at
      the time of publishing, then an rdf:List is the best structure.
      Otherwise use an rdf:Seq. These RDF data structures can easily be
      generated and maintained using an asynchronous indexing system,
      avoiding the need to rebuild all the indexes whenever the
      underlying data changes. However for a large number of different
      indexes or variations the time spent building these indexes can be
      expensive.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Hierarchical URIs <hierarchical-uris.html>`__
         -  `Composite Descriptions <composite-descriptions.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <custo         | `Up <modelli         |  `Next <label        |
   | m-datatype.html>`__  | ng-patterns.html>`__ | -everything.html>`__ |
   +----------------------+----------------------+----------------------+
   | Custom Datatype      | `Ho                  |  Label Everything    |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
