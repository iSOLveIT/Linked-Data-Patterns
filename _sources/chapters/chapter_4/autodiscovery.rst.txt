.. _autodiscovery:

Autodiscovery
=============

               :name: autodiscovery
               :class: title

   *How can people find the underlying linked data for a given web
   page?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Currently the Web is predominately built from interlinked HTML
      pages. Linking directly to linked data documents from HTML
      presents the risk of confusion for non-technical audiences.
      However the publisher requires that the underlying data be
      discoverable by linked data aware tools and indexable by search
      engines.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      When publishing a web page derived from linked data include a link
      element in the head of the web page pointing to the original data.

      ``<link rel="meta" type="application/rdf+xml" title="Raw Data" href="http://example.com/data.rdf"/>``

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The FOAF Vocabulary recommends linking a homepage to an equivalent
      FOAF profile using the link element.

      The Semantic Radar Firefox plugin uses the autodiscovery pattern
      to detect the presence of linked data related to the web page the
      user is viewing.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Until web browsers become fully linked data aware it may not be
      satisfactory to link directly to linked data pages from the body
      of an HTML page. HTML provides the link element to allow
      publishers to include links to information and resources that may
      be relevant in addition to the main content of the page. Web
      browsers may choose to display these links in their user
      interface. Web search engines can use these links to discover
      additional information that may make their search more relevent
      for the user.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Primary Topic
            Autodiscovery <primary-topic-autodiscovery.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <              | `Up <publishi        |  `Next <dataset-au   |
   | annotation.html>`__  | ng-patterns.html>`__ | todiscovery.html>`__ |
   +----------------------+----------------------+----------------------+
   | Annotation           | `Ho                  |  Dataset             |
   |                      | me <index-2.html>`__ | Autodiscovery        |
   +----------------------+----------------------+----------------------+
