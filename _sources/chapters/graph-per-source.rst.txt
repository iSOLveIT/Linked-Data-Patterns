.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Graph Per Source     |                      |                      |
   +======================+======================+======================+
   | `Prev <graph-pe      | Chapter 5. Data      |  `Next <n            |
   | r-resource.html>`__  | Management Patterns  | amed-graphs.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Graph Per Source
               :name: graph-per-source
               :class: title

   *How can we track the source of some triples in an RDF dataset?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      A common application requirement is to create a local cache of RDF
      data which originates from other sources. For example an
      application might crawl or harvest data from the Linked Data cloud
      and store it local triple store. Data from relational databases or
      other sources might also be regularly converted into RDF and added
      to a triple store.

      While the applications directly consuming this data may not need
      any knowledge of their origin when querying the dataset, the
      applications doing the data management activities (e.g. crawling
      or data conversions) will need to be able to clearly identify
      which triples came from which source dataset or URL.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use a separate `named graph <named-graphs.html>`__ for each data
      source. For the named graph URI either use a well-known URI for
      each data source, e.g. the URI of the dataset, or simply the URL
      from which the data was retrieved.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      An application is harvesting RDF documents from the web. Upon
      discovering the URL ``http://www.example.org/person.rdf`` the
      application does a GET request to retrieve the document. The RDF
      statements found in that document are then stored in the
      applications triple store in a new named graph with the source URI
      as the graph identifier:

      .. code:: programlisting

         #Named graph URI is source document
         <http://www.example.org/person.rdf> { 
           #Triples from source document
           <http://www.example.org/person/joe> foaf:name "Joe Bloggs". 
         }

      The harvesting application can easily determine whether it has
      already harvested a URL by checking to see whether a named graph
      with that URI exists in the store. The next time that the
      application retrieves the content of the URL, e.g. as part of a
      cache refresh, the contents of just that graph can be replaced.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The URI that labels a `named graph <named-graphs.html>`__ can be
      used in several different ways. One very common approach is to use
      the label to hold the URL from which a set of triples was
      retrieved. By using the graph URI to identify the source of the
      data it becomes possible to track the provenance of the data
      within the store. This can simplify common dataset construction
      scenarios, e.g. mirroring of data harvested from the web.

      Checking for the presence of a graph within a store can be
      achieved using a simple `assertion
      query <assertion-query.html>`__:

      .. code:: programlisting

             ASK WHERE {
                 <http://www.example.org/person.rdf> { ?s ?p ?o. }
             }

      The query will return true if there are any statements associated
      with a graph with the specified identifier

      An application may need to be present to an end-user the list of
      locations from which some RDF statements have been found. This too
      can be achieved using a simple SPARQL query:

      .. code:: programlisting

             SELECT ?graph WHERE {
                 ?graph { 
                     <http://www.example.org/person/joe> foaf:name "Joe Bloggs". 
                 }
             }

      In the above example the query will return the URIs of all graphs
      that contain the specified RDF triple; "which sources say that
      ``http://www.example.org/person/joe`` has a ``foaf:name`` of "Joe
      Bloggs".

      It is often important to capture some additional information about
      the source of the URL. For example a web crawler might want to
      record the retrieval data and HTTP headers associated with the
      original web request. This would allow for more efficient cache
      maintenance. The `Graph Annotation <graph-annotation.html>`__
      pattern describes this in more detail.

      It is worth noting that in some cases a direct application of this
      pattern can make graph annotation more awkward: by using the
      source URL as the graph URI we can no longer distinguish between
      statements made about the *graph* and statements made about the
      *source document*. E.g. the date of creation of the graph and the
      date of creation of the document. This may be an issue for some
      application scenarios, although for others (e.g. simple
      aggregation) this may not be an problem.

      As described in the `Graph Annotation <graph-annotation.html>`__
      pattern the solution to this issue is to use a different
      identifier for the graph, e.g. a `Patterned
      URI <patterned-uris.html>`__ derived from the source URL. The
      source URL of the graph can then be captured as an annotation.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Named Graph <named-graphs.html>`__
         -  `Graph Annotation <graph-annotation.html>`__
         -  `Graph Per Resource <graph-per-resource.html>`__

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
   | `Prev <graph-pe      | `Up <data-manageme   |  `Next <n            |
   | r-resource.html>`__  | nt-patterns.html>`__ | amed-graphs.html>`__ |
   +----------------------+----------------------+----------------------+
   | Graph Per Resource   | `Ho                  |  Named Graph         |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
