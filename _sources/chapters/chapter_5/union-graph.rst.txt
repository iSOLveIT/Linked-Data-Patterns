.. _union-graph:

Union Graph
===========

               :name: union-graph
               :class: title

   *How can we generate a simple view over the statements in a
   collection of named graphs?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      The `Named Graph <named-graphs.html>`__ pattern describes an
      approach for managing RDF statements as a collection of graphs.
      The `Graph Annotation <graph-annotation.html>`__ pattern
      illustrates how to capture information about these graphs. However
      for many use cases, a consuming application may need to ignore the
      graph structure of a dataset and instead work on a single
      consistent view of the data. In other circumstances we may only
      want to query a certain set of graphs (e.g. just the data, or just
      the annotations). So how do we gain the benefits of named graphs
      without having to teach all applications about the internal
      structure of our triple store?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Write queries against a "union graph" that provides a simple view
      over a collection of named graphs by relying on RDFs data merging
      rules.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      See below

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Named graphs are a useful way to structure a store to simplify the
      compilation and maintenance of a dataset. But we might consider
      that the graph structure of a dataset -- i.e. how it is composed
      of a number of named graphs -- to be an implementation detail that
      needn't concern applications built on that data.

      The RDF data model provides rules for merging of RDF statements
      into a set. Those rules can be applied to create a simple
      synthetic view over a collection of named graphs that ignores the
      graph structure completely. A union graph is the RDF merge of one
      or more named graphs.

      Most RDF triple stores offer the ability to create or use union
      graphs in some form. SPARQL also provides some options for
      creating additional "union graphs" (otherwise known as "synthetic"
      or "view" graphs).

      We can think of a quad store as a set of named graphs, each of
      which has an identifier. All triples are therefore associated with
      a specific named graph. However when applying some pattern
      matching, e.g. in a query, or inferencing rules, we can safely
      ignore the graph URI component of the quad, this result in a
      simple triple based view of the data. This is a simple union over
      all the graphs. Some stores allow this union to be referenced in a
      query or application code, in order to allow graph-agnostic
      processing.

      In SPARQL a dataset consists of a default graph, which doesn't
      have an identifier, plus zero or more named graphs which each have
      a URI. Triple stores that are geared towards SPARQL may similarly
      offer a default graph in which triples can be stored and the
      ability to store data in additional named graphs. TDB (part of
      Apache Jena) provides such a facility. Triples may be added to a
      dataset and these are then stored in the default, unnamed graph.
      In a SPARQL query, triples patterns are matched only against this
      graph. However TDB also offers a way to address the union graph of
      the store: i.e a view over all of the named graphs in the store
      (plus the default). TDB may also be configured to not allow
      updates to the default graph. In this case the default graph is
      automatically constructed from the union graph.

      Other triple stores do not support an default unnamed graph,
      requiring all triples to be associated with some graph. In this
      case when executing a SPARQL query the default graph will be
      selected based on some system wide default (e.g. the union of all
      graphs) or by the query itself using a FROM clause.

      The SPARQL FROM clause provide another way to define custom union
      graphs. The FROM clause is used to identify the default graph for
      a query. The most typical use is to identify a single RDF graph.
      However if multiple FROM clauses are specified in a query then the
      contents of those graphs are merged (typically in-memory) to
      provide a union graph that will form the default graph for the
      query. This feature of SPARQL can therefore provide another way to
      assemble a useful graph-agnostic view of a dataset.

      The options here are on the surface confusing. But they offer some
      useful further options for managing and querying datasets. The
      important part is to understand that some options are provided by
      the underlying storage, whereas others are a function of the
      SPARQL query language:

      .. container:: itemizedlist

         -  a triple store may manage data either as a collection of
            named graphs, or directly as a SPARQL dataset, i.e. a
            default graph plus zero or more named graphs. In the latter
            case triples can be added/removed from the default graph
         -  a triple store may provide a view over its entire contents,
            regardless of the partitioning into graphs. This is the most
            common form of union graph. It is also likely to be
            efficient for pattern matching, etc. This union graph may be
            in addition to whatever basic storage options the store
            provides
         -  a triple store may offer options for how a sparql dataset is
            created for a given query, or it may enforce a specific
            structure. E.g. a store may enforce that the default graph
            is a specific stored graph, or that it is a union graph
            providing a view of all of its contents
         -  a triple store may offer some additional flexibility for a
            sparql query to define its dataset including specifying a
            single graph as the default, the store-wide union graph, or
            a query specific union graph which is populated by merging
            together a number of named graphs identified in the FROM
            clause of the query

      Not all triple stores offer this kind of flexibility but many
      offer at least some options for querying the whole store as a
      union graph.

      There is scope here for further innovation on the part of store
      implementors, e.g. to offer additional ways to either statically
      or dynamically create union graphs over a store. For example an
      application may want to identifier the most recently updated
      graphs; graphs with a particular kind of content; public and
      "private" graphs, etc.

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

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Managing RDF using Named Graphs <#>`__
         -  `TDB Datasets <#>`__
         -  `TDB Dynamic Datasets <#>`__
         -  `SPARQL 1.1 Specifying RDF Datasets <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <na            | `Up <data-manageme   |  `Next <applicati    |
   | med-graphs.html>`__  | nt-patterns.html>`__ | on-patterns.html>`__ |
   +----------------------+----------------------+----------------------+
   | Named Graph          | `Ho                  |  Ch                  |
   |                      | me <index-2.html>`__ | apter 6. Application |
   |                      |                      | Patterns             |
   +----------------------+----------------------+----------------------+
