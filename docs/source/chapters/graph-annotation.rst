.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Graph Annotation     |                      |                      |
   +======================+======================+======================+
   | `                    | Chapter 5. Data      |  `Next <graph        |
   | Prev <data-managemen | Management Patterns  | -per-aspect.html>`__ |
   | t-patterns.html>`__  |                      |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Graph Annotation
               :name: graph-annotation
               :class: title

   *How can we capture some metadata about a collection of triples?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      There are a number of scenarios where it is useful to capture some
      metadata about a collection of statements in a triplestore. For
      example we may want to capture:

      .. container:: itemizedlist

         -  publication metadata, such as the date that the triples were
            asserted or last updated
         -  provenance metadata, e.g. who asserted those triples, or how
            they were generated
         -  access control data, e.g. which user(s) or role(s) can
            access those triples

      The `Named Graph <named-graphs.html>`__ pattern allows us to
      identify a set of triples, via a URI.But how do we then capture
      information about that graph?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Treat the `Named Graph <named-graphs.html>`__ like any other
      resource in your dataset and make additional RDF statements about
      the graph itself. Those additional statements can themselves be
      stored in a further named graph.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      A triple store contains a Named Graph that is used to store the
      results of transforming a local database into RDF. The Named Graph
      has been given the identifier of
      ``http://app.example.org/graphs/my-database`` to label the triples
      resulting from that conversion process. As the source is a live,
      regularly updated database it is useful to know when the RDF
      conversion was last executed and the data stored. It is also
      useful to know which version of the conversion software was used,
      to track potential bugs. This additional metadata could be
      captured as follows:

      .. code:: programlisting

         @prefix ex: <http://www.example.org/> .

         #Named graph containing results of database conversion
         <http://app.example.org/graphs/my-database> { 
            ...triples from conversion...
         }

         #Metadata graph
         <http://app.example.org/graphs> { 
           #Description of a named graph in this dataset
           <http://app.example.org/graphs/my-database> dct:source <http://app.example.org/database/customers>
           <http://app.example.org/graphs/my-database> dct:created "2012-05-28"^^xsd:date.
           <http://app.example.org/graphs/my-database> foaf:generatorAgent <http://app.example.org/converter/0.0.5>.

           ...descriptions of other graphs...
         }

      In the above example there are two graphs in the dataset: the
      graph containing the data from the conversion and a second graph
      containing metadata about the first. An application that needed to
      identify the date that some triples were asserted can easily do
      this by querying the metadata graph.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The majority of `Named Graph <named-graphs.html>`__ uses cases
      require some additional context to be captured about the set of
      triples labelled with a graph URI. Describing named graphs in RDF,
      by using the graph URI as the subject of additional RDF
      statements, provides a simple way to capture additional metadata
      relevant to an application.

      As shown in the above example, a specific "well-known" named graph
      in the dataset can be designated as the location in which these
      extra statements are recorded. However it is also possible to use
      multiple named graphs. In this case we might have one graph for
      the data and one "parallel" graph that captures the context. For
      example if we could adjust the above example as follows:

      .. code:: programlisting

         @prefix ex: <http://www.example.org/> .

         #Named graph containing results of database conversion
         <http://app.example.org/graphs/my-database> { 
            ...triples from conversion...
         }

         #"Parallel" metadata graph
         <http://app.example.org/metadata-graphs/my-database> { 
           #Description of  named graph in this dataset
           <http://app.example.org/graphs/my-database> dct:source <http://app.example.org/database/customers>
           <http://app.example.org/graphs/my-database> dct:created "2012-05-28"^^xsd:date.
           <http://app.example.org/graphs/my-database> foaf:generatorAgent <http://app.example.org/converter/0.0.5>.
         }
         ...other named graphs
         }

      Using a pair of named graphs per source can quickly lead to a very
      large number of graphs in a dataset. Some triple stores may not be
      optimized to deal with a very large number of graphs. However the
      approach does benefit from flexibility of adding and removing both
      source graphs and their metadata.

      Care should be taken when choosing graph URIs. If an application
      uses the source document URL of some RDF as the named graph URI
      then this can lead to confusing statements as illustrated below:

      .. code:: programlisting

         @prefix ex: <http://www.example.org/> .

         #Named graph containing results of HTTP crawl
         <http://example.org/person/joe.rdf> { 
           #statements contained in the document, about itself
           <http://example.org/person/joe.rdf> foaf:primaryTopic <http://example.org/person/joe>.
           #date the FOAF document was created
           <http://example.org/person/joe.rdf> dct:created "2010-06-01".

           <http://example.org/person/joe> foaf:name "Joe Bloggs".
         }

         #Metadata graph, describing results of crawl
         <http://app.example.org/graphs/> { 
             #date the named graph was created
             <http://example.org/person/joe.rdf> dct:created "2012-05-28".
         }

      In the above example there are two ``dct:created`` properties
      associated with the resource
      ``http://example.org/person/joe.rdf``. That document is a FOAF
      description which describes its primary topic and the date it was
      generated. The second date was added by a hypothetical web crawler
      that captured the date it stored that information in a named
      graph. It is possible for a SPARQL query applied to the `union
      graph <union-graph.html>`__ for this dataset to return conflicting
      information, suggesting that the use of the source URL as a graph
      identifier is a poor choice. A better alternative would be to add
      some indirection:

      .. code:: programlisting

         @prefix ex: <http://www.example.org/> .

         #Named graph containing results of HTTP crawl
         <http://app.example.org/graphs?source=http://example.org/person/joe.rdf> { 
           #statements contained in the document, about itself
           <http://example.org/person/joe.rdf> foaf:primaryTopic <http://example.org/person/joe>.
           #date the FOAF document was created
           <http://example.org/person/joe.rdf> dct:created "2010-06-01".

           <http://example.org/person/joe> foaf:name "Joe Bloggs".
         }

         #Metadata graph, describing results of crawl
         <http://app.example.org/graphs> { 
             #date the named graph was created
             <http://app.example.org/graphs?source=http://example.org/person/joe.rdf> dct:created "2012-05-28".
             #source of the graph
             <http://app.example.org/graphs?source=http://example.org/person/joe.rdf> dct:source <http://example.org/person/joe.rdf>.
         }

      In the revised example a new URI is associated with the results of
      the web crawl. The web crawler then uses this URI to record the
      required metadata. By adding an ``dct:source`` property (or
      similar) it is still possible to identify which named graph was
      derived from which source URL. As can be seen a `Patterned
      URI <patterned-uris.html>`__ is used to generate the graph
      identifier, giving a predictable structure to the store.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Named Graph <named-graphs.html>`__
         -  `Graph Per Resource <graph-per-resource.html>`__
         -  `Graph Per Source <graph-per-source.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Named Graph (Wikipedia) <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `                    | `Up <data-manageme   |  `Next <graph        |
   | Prev <data-managemen | nt-patterns.html>`__ | -per-aspect.html>`__ |
   | t-patterns.html>`__  |                      |                      |
   +----------------------+----------------------+----------------------+
   | Chapter 5. Data      | `Ho                  |  Graph Per Aspect    |
   | Management Patterns  | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
