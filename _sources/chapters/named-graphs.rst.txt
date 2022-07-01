.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Named Graph          |                      |                      |
   +======================+======================+======================+
   | `Prev <graph-        | Chapter 5. Data      |  `Next <             |
   | per-source.html>`__  | Management Patterns  | union-graph.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Named Graph
               :name: named-graph
               :class: title

   *How can we identify a useful sub-set of RDF triples within a triple
   store?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      A triplestore is a set of RDF triples. Upon loading some RDF data
      into such a collection we lose the ability to be able to identify
      a sub-set of RDF triples, e.g. to identify their source of origin.
      We also lose knowledge of whether a single triple was asserted
      once or multiple times, e.g. by separate distinct sources. While
      it is possible to extract triples based on particular graph
      patterns, e.g. all triples with the same subject, predicate, or
      object there is no way to recover the original contect.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use URIs to identify collections of statements. Where necessary
      associate a triple with this URI to create a *quad*

      By assigning a URI to a set of triples and my retaining that
      additional identifier in the store (a *quad store*), we can either
      treat the whole collection as a single set of triples, or work
      with an subset based on its graph identifier.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The following example shows an RDF graph using the TRiG notation
      (Turtle plus graphs)

      .. code:: programlisting


         @prefix ex: <http://www.example.org/> .

         #Named graph in TRiG
         <http://www.example.org/graph/1> { 
                 <http://www.example.org/document/7> rdfs:label "Example". 
         }

      The following example shows an RDF graph using the NQuads notation
      (N-Triples plus graphs)

      .. code:: programlisting


         <http://www.example.org/document/7> rdfs:label "Example" <http://www.example.org/graph/1>. 

      In both cases the graphs contain a single RDF triple

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The idea of extending the triple into a quad, through the addition
      of an additional URI has been around for many years. The Many
      early triple stores supported the notion of a quad, with the
      majority now supporting named graphs as a key feature. SPARQL 1.0
      was the first semantic web specification to directly reference the
      concept, allowing queries to be addressed to an individual named
      graph or a collection of graphs. Syntaxes for serialising named
      graphs also exist, allowing quads to be exchanged between systems.
      The most commmonly used quad syntaxes are TRiG (a derivative of
      Turtle) and NQuads (a derivative of NTriples.

      By extending the core RDF model from a triple to a quad, Named
      graphs provide a useful extra degree of freedom when managing an
      RDF dataset. A useful analogy when thinking about a quad store is
      that of a collection of documents: each named graph is a separate
      "document" in the database that can be manipulated independently
      from any others. However the document identifier (the graph URI)
      can be ignored when working with data, relying on RDF graph
      merging rules to provide a view across all documents. A graph
      store therefore offers a useful way to manage sets of statements
      without losing the ability to easily merge data from across
      sources.

      Graphs have been usefully applied to solving a number of different
      data management problems in RDF applications. Some recorded uses
      for Named Graphs include:

      .. container:: itemizedlist

         -  *Tracking provenance of RDF data* — here the extra URI is
            used to track the source of the data; especially useful for
            web crawling scenarios
         -  *Replication of RDF graphs* — triples are grouped into sets,
            labelled by a URI, that may then be separately exchanged and
            replicated
         -  *Managing RDF datasets* — here the set of triples may be an
            entire RDF dataset, e.g. all of dbpedia, or all of
            musicbrainz, making it easier to identify and query subsets
            within an aggregation
         -  *Versioning* — the URI identifies a set of triples, and that
            URI may be separately described, e.g. to capture the
            creation & modification dates of the triples in that set,
            who performed the change, etc.
         -  *Access Control* — by identifying sets of triples we can
            then record access control related metadata

      The lack of standardisation about what the graph URI associated
      with a named graph identifies means that different applications
      have used it for different purposes. For example one application
      might simply use the URI as a local identifier for a set of
      triples, whereas another might associate extra semantics with the
      URI, e.g. using it to hold the URL from which the data was
      originally retrieved.

      The simplest way to thing about the graph URI is as a simple
      identifier or label that can be associated with some triples. The
      fact that the identifier is a URI has some added benefits. For
      example we could then capture RDF statements to describe the
      graph. This has been applied as an alternative to
      `reification <reified-statement.html>`__ for handling versioning
      and provenance in datasets, but `graph
      annotation <graph-annotation.html>`__ is useful in a number of
      scenarios.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Reified Statement <reified-statement.html>`__
         -  `Graph Annotation <graph-annotation.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <graph-        | `Up <data-manageme   |  `Next <             |
   | per-source.html>`__  | nt-patterns.html>`__ | union-graph.html>`__ |
   +----------------------+----------------------+----------------------+
   | Graph Per Source     | `Ho                  |  Union Graph         |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
