.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Blackboard           |                      |                      |
   +======================+======================+======================+
   | `Prev <asser         | Ch                   |  `Next <bounded-     |
   | tion-query.html>`__  | apter 6. Application | description.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Blackboard
               :name: blackboard
               :class: title

   *How can the task of compiling or constructing a dataset be divided
   up into smaller tasks?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Applications consuming Linked Data commonly need to compile a
      dataset by collecting data from a number of distributed sources,
      e.g. other Linked Data datasets, SPARQL endpoints, or converting
      data from other legacy systems. A monolithic approach to
      constructing an aggregated dataset can be slow, fragile, and
      complex to implement. Dividing up tasks into smaller units of work
      can help parallelize the compilation of the data.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create a number of separate processes that are each specialised to
      a particular task. Each process runs independently from each of
      the others, allowing each to be as simple or as complex as
      necessary. The processes all co-ordinate in the `Progressive
      Enrichment <progressive-enrichment.html>`__ of a single dataset,
      but are not triggered in any particular sequence. Instead each
      process looks for specific patterns in the underlying dataset,
      triggering the processing of the data, the results are then
      written back to the dataset.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      An application is written to monitor twitter for uses of a
      particular hash tag. The application provides a simple RDF view of
      each tweet, including its author, text, timestamp. The RDF is
      written into a shared RDF dataset that serves as the Blackboard
      for a number of other processes. Additional processes are then
      written that query the dataset to discover new tweets. These
      processes carry out discrete tasks. The results of the tasks may
      trigger further processing by other tasks, or may be used to
      directly drive specific application behaviour. The tasks may
      include steps such as:

      .. container:: itemizedlist

         -  Looking for profile information about the author of each
            tweet
         -  Attempting to find a FOAF profile for each author
         -  Extracting hash tags from new tweets
         -  Extracting URLs from individual tweets
         -  Discovering metadata associated with URLs mentioned in
            tweets

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The Blackboard pattern is an existing design pattern that has been
      used in a number of existing systems, it works well when applied
      to the task of aggregating RDF and Linked Data due to the ease
      with which a dataset can be enriched over time.

      The RDF dataset used as the "blackboard" shared by the independent
      processes may be short-lived, e.g. an in-memory datastore used to
      respond to a particular request or task, or permanent, e.g. an
      on-going aggregation of data on a particular topic or theme.

      The decomposition of the data aggregation & conversion tasks into
      smaller units makes it easier to explore different approaches for
      implementing the desired behaviour, e.g. to explore alternate
      technologies or algorithms. The overall result of the processes
      co-operating to compile and enrich the dataset can be extremely
      complex but without requiring any overall co-ordination effort.
      Additional processes steps, e.g. to acquire data from additional
      sources, can easily be added without impacting on the overall
      system, making the architecture extensible.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Progressive Enrichment <progressive-enrichment.html>`__
         -  `Parallel Loading <parallel-loading.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <asser         | `Up <applicati       |  `Next <bounded-     |
   | tion-query.html>`__  | on-patterns.html>`__ | description.html>`__ |
   +----------------------+----------------------+----------------------+
   | Assertion Query      | `Ho                  |  Bounded Description |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
