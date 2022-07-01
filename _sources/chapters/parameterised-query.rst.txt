.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Parameterised Query  |                      |                      |
   +======================+======================+======================+
   | `Prev <parallel      | Ch                   |  `Next <resou        |
   | -retrieval.html>`__  | apter 6. Application | rce-caching.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Parameterised Query
               :name: parameterised-query
               :class: title

   *How to avoid continual regeneration and reparsing of SPARQL queries
   that differ only in a few bound variables?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Many applications continually execute a small number of queries
      which differ only in terms of a few parameters. For example
      generating a `Bounded Description <bounded-description.html>`__ of
      a resource might involve a standard query that varies only by the
      resource URI being referenced. Other queries might vary based on
      date ranges, page offsets, etc. Re-generating queries as text
      strings can be fiddly and makes for messy application code. This
      is particularly true when the query then needs to be serialised
      and submitted over the SPARQL protocol: URL encoding issues can
      easily cause problems. In addition a query engine incurs extra
      overhead when repeatedly parsing the same query.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Define each repeated query as as query template which can be
      parsed once by the query engine. The query should define variables
      for those aspects of the query that might vary. The variables can
      then be bound to the query before execution. Supplying the values
      for these parameters will typically involve an engine specific API
      call.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      Apache Jena uses a ``QueryExecutionFactory`` to support creation
      of queries. Query objects can be pre-compiled. An initial set of
      bindings for a query can be provided in order to `create a
      specific QueryExecution <#>`__. These initial bindings are simply
      a map from variable name to value.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      This pattern is well understood in the SQL database world:
      Prepared Statements have been in use for many years. SPARQL
      processors are now starting to add similar features, which
      simplifies working with queries from application code.

      At present the SPARQL Protocol does not support specification of
      initial bindings as additional query string parameters. However
      some Linked Data publishing platforms have added support for
      parameterised queries, as extensions to the core protocol,
      allowing additional query parameters to be automatically injected
      into the query prior to execution. This makes it simpler for users
      to share queries and adjust their parameters.

      SPARQL 1.1 provides `a ``BINDINGS`` keyword <#>`__ which can be
      used to declare that certain variables should be injected into a
      graph pattern. This was added primarily to support federated query
      use cases, but can also be used to support some parameterisation
      of queries.

      A map of named-value pairs which describe some initial query
      bindings can also be interpolated directly into a query by looking
      for appropriately named query variables. This interpolation has
      been done in several ways:

      .. container:: itemizedlist

         -  Using some additional custom syntax to mark up the variable,
            e.g. ``%{var}``. This means that the query is no longer
            valid SPARQL into variables have been substituted
         -  By using the fact that SPARQL provides to naming syntaxes
            for variables, and defining ``$var`` to be those that are
            bound before execution and ``?var`` those that are bound
            during execution (or vice versa). This relies on local
            convention.
         -  By binding any query variable using any valid SPARQL syntax.
            The downside to this option is that additional external
            context is required to identify those variables that must be
            bound prior to execution. The other options allow these to
            be identified from just the query itself, although in
            practice it is often useful to be able to known the expect
            type, format or legal values for a parameter which will
            require additional configuration anyway.

      Parameterised Queries are a core feature of the `Named
      Query <named-query.html>`__ pattern.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Named Query <named-query.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `SPARQL 1.1. Bindings <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <parallel      | `Up <applicati       |  `Next <resou        |
   | -retrieval.html>`__  | on-patterns.html>`__ | rce-caching.html>`__ |
   +----------------------+----------------------+----------------------+
   | Parallel Retrieval   | `Ho                  |  Resource Caching    |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
