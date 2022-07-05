.. _named-query:

Named Query
===========

               :name: named-query
               :class: title

   *How can details of the SPARQL protocol be hidden from clients?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      SPARQL protocol URLs quickly become complex when dealing with any
      non-trivial query. Very large queries can be so long that some
      clients or browsers may have issues with length of the URLs. The
      only solution in this case is to switch from a GET request to a
      POST request. But as a query is an idempotent operation it is
      better to use GET, with appropriate caching headers, rather than a
      POST.

      In other circumstances a service might want to restrict the set of
      queries that can be invoked against a SPARQL endpoint. Or the use
      of SPARQL might be entirely hidden from calling clients. In both
      of those cases removal of direct access to the SPARQL endpoint may
      be desirable.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Assign a short URL to the SPARQL protocol request. The URL maps
      directly to a SPARQL query that is executed on request. Clients
      can use the short URL instead of the full SPARQL protocol request
      to extend the query.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      An application exposes a SPARQL endpoint at
      ``http://api.example.org/sparql`` and a collection of named
      queries from ``http://app.example.org/queries``.

      One example query that clients might potentially execute is:

      .. code:: programlisting

             SELECT ?uri ?homepage WHERE {
                 ?uri foaf:homepage ?homepage.
             }

      Rather than requiring clients to compose the full SPARQL protocol
      request for that URL it could instead be defined as a named query
      for the service. The query could be associated with the following
      URL: ``http://api.example.org/sparql/list-homepages``. A GET
      request to that URL would be equivalent to the SPARQL protocol
      request to the endpoint, i.e. would execute the configured SPARQL
      query and return a response in one of the standard SPARQL protocol
      formats.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Named queries is useful in a number of circumstances. Assigning
      short URLs to queries can remove issues with dealing with lengthy
      SPARQL queries that might get accidentally truncated in emails or
      be rejected by older HTTP clients or browsers. By providing tools
      for users of a service to create new named queries then a
      community can share and publish a useful set of queries.

      Another benefit of binding queries to URLs, i.e. by creating new
      web resources, a service can implement additional optimisations
      that can improve response time of queries. E.g. query results
      might be generated asynchronously and the cached results supplied
      to clients rather than the query being executed on demand.

      One way to protect a SPARQL endpoint is to reduce the legal set of
      queries to an approved list, e.g. that won't cause performance
      issues for the service. Named queries provide a way to provide a
      set of legal queries which are then bound to URLs. Direct access
      to the SPARQL endpoint can then be disabled, or limited to a
      white-listed set of client applications.

      There are some additional nuances to consider when implementing
      this pattern. For example the SPARQL protocol could be extended to
      support `Parameterised queries <parameterised-query.html>`__ by
      injecting query string parameters into the query before it is
      executed. Additional parameters could be used to invoke additional
      kinds of pre- or post-processing behaviour including
      transformation of SPARQL protocol responses into alternate formats

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Parameterised Query <parameterised-query.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `SPARQL Stored Procedure <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <missing-i     | `Up <applicati       |  `Next <paral        |
   | snt-broken.html>`__  | on-patterns.html>`__ | lel-loading.html>`__ |
   +----------------------+----------------------+----------------------+
   | Missing Isn't        | `Ho                  |  Parallel Loading    |
   | Broken               | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
