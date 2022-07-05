.. _parallel-retrieval:

Parallel Retrieval
==================

               :name: parallel-retrieval
               :class: title

   *How can we improve performance of an application dynamically
   retrieving Linked Data?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      An application that draws on data from the web may typically be
      retrieving a number of different resources. This is especially
      true if using the `Follow Your Nose <follow-your-nose.html>`__
      pattern to discover data

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use several workers to make parallel GET requests, with each work
      writing into a shared RDF graph

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      Most good HTTP client libraries will support parallelisation of
      HTTP requests. E.g. PHP's `curl_multi <#>`__ or Ruby's
      `typhoeus <#>`__ library.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Parallelisation of HTTP requests can greatly reduce retrieval
      times, e.g. to time of the single longest GET request.

      By combining this approach with `Resource
      Caching <resource-caching.html>`__ of the individual responses, an
      application can maintain a local cache of the most requested data,
      which are then combined and parsed into a single RDF graph for
      driving application behaviour.

      Parallelisation is particularly useful for AJAX based applications
      as browsers are particularly well optimized for making a large
      number of parallel HTTP requests.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Follow Your Nose <follow-your-nose.html>`__
         -  `Parallel Loading <parallel-loading.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <parall        | `Up <applicati       |  `Next <paramete     |
   | el-loading.html>`__  | on-patterns.html>`__ | rised-query.html>`__ |
   +----------------------+----------------------+----------------------+
   | Parallel Loading     | `Ho                  |  Parameterised Query |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
