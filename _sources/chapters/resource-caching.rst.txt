.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Resource Caching     |                      |                      |
   +======================+======================+======================+
   | `Prev <parameter     | Ch                   |  `Next <schema       |
   | ised-query.html>`__  | apter 6. Application | -annotation.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Resource Caching
               :name: resource-caching
               :class: title

   *How can an application that relies on loading data be more tolerant
   of network failures and/or reduce use of bandwidth*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Linked Data applications will typically need to discover and load
      data and schemas from the web. A user may request that extra data
      is displayed from specific locations, and the loading of a new
      data source may trigger loading of additional schemas, e.g. to
      discover labels for properties and types, or to pass to a reasoner
      for infering additional data and relationships. Some resources and
      vocabularies may be very commonly used, e.g. the RDF, RDF Schema
      and OWL vocabularies, while others may only be encountered during
      run-time.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Build a local cache of retrieved resources, refreshing the cache
      only when source data has changed.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Retrieving resources from the web, like any other network access,
      is prone to failure. Repeated fetching of the same resources is
      waste-ful of bandwidth on the client and the server: a large
      number of clients can easily overload resources on a system
      serving up popular vocabularies.

      Applications should cache remote resources wherever possible. The
      cache may be handled entirely in-memory but with sufficient
      permissions and access to the local file-system an application
      could also build a persistent cache. Desktop application may ship
      with a pre-seeded cache of commonly retrieved resources such as
      ontologies. Efficient use of HTTP request can ensure that cached
      versions need only be updated when the remote copy of the resource
      has been updated. Certain vocabularies, e.g. RDF Schema, will only
      change rarely, if at all. These could be cached for longer
      periods, if not permanently.

      Ideally applications should provide configuration to support the
      user in managing the amount of local resources (memory or disk
      space) that can be used by the cache. Control over the location in
      which cached data will be stored is also useful.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Follow Your Nose <follow-your-nose.html>`__
         -  `Parallel Retrieval <parallel-retrieval.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <parameter     | `Up <applicati       |  `Next <schema       |
   | ised-query.html>`__  | on-patterns.html>`__ | -annotation.html>`__ |
   +----------------------+----------------------+----------------------+
   | Parameterised Query  | `Ho                  |  Schema Annotation   |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
