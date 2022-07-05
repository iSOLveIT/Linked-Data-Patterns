.. _transformation-query:

Transformation Query
====================

               :name: transformation-query
               :class: title

   *How can we normalize or transform some RDF data so that it conforms
   to a preferred model?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      There are a broad range of different vocabularies in use on the
      Linked Data web. While there has been convergence on common
      vocabularies in a number of domains, there will always be some
      variations in how data is presented, e.g. using slightly different
      modelling styles and vocabularies. Schemas will also evolve over
      time and certain properties may be refined or replaced. How can a
      consuming application normalize these different models into a
      single preferred representation that matches expectations or
      requirements of the application code?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use a SPARQL ``CONSTRUCT`` query, or collection of queries, to
      generate a normalized view of the data, saving the results back
      into the triple store.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The following query normalizes any one of three different naming
      or labelling properties into ``rdfs:label`` properties.

      .. code:: programlisting


         PREFIX foaf: <http://xmlns.com/foaf/0.1/>
         PREFIX vCard: <http://www.w3.org/2001/vcard-rdf/3.0#>
         PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
         PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
         CONSTRUCT {
           ?s rdfs:label ?o.
         }
         WHERE {
           {  ?s foaf:name ?o. }
           UNION
           {  ?s vCard:FN ?o. }
           UNION
           {  ?s skos:prefLabel ?o. }
         }

           

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Writing application code to normalize data patterns can be tedious
      and difficult to maintain in the face of changes. SPARQL
      ``CONSTRUCT`` queries provide a way to generate arbitrary RDF
      graphs from existing data. They therefore provide a way to carry
      out transformations on RDF graph. These transformations can be
      used to infer new data based on existing patterns and this covers
      the generation of normalized data models. SPARQL therefore
      provides a declarative syntax for describing graph
      transformations. The increased expressivity of SPARQL 1.1 will
      allow more complex transformations to be specified.

      An application may apply one or more Transformation Queries to its
      data source either during execution, e.g. to extract a graph of a
      known structure, or during assembly of the underlying dataset,
      e.g. as part of the `Blackboard <blackboard.html>`__ pattern.

      Each transformation query may cover one specific normalization
      task. However, as shown in the example above, several operations
      can be combined using a ``UNION`` query. This allows the graph
      pattern of the query to match for a number of different variants,
      resulting in the generation of a single standard output graph.

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev                | `Up <applicati       |  `Next <u            |
   |  <smushing.html>`__  | on-patterns.html>`__ | ri-resolver.html>`__ |
   +----------------------+----------------------+----------------------+
   | Smushing             | `Ho                  |  URI Resolver        |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
