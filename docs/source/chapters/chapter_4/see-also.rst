.. _see-also:

See Also
========

               :name: see-also
               :class: title

   *How can RDF documents be linked together to allow crawlers and user
   agents to navigate between them?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Linked Data is typically discoverable by de-referencing URIs.
      Starting with a single URI a user agent can find more data by
      discovering other URIs returned by progressively retrieving
      descriptions of resources referred to in a dataset. However in
      some cases it is useful to provide additional links to other
      resources or documents. These links are not semantic relations per
      se, just hypertext links to other sources of RDF.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use the ``rdfs:seeAlso`` property to link to additional RDF
      documents.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The Linked Data published by the BBC Wildlife Finder application
      includes data about ecozones. The data about an individual
      ecozone, e.g. the `Nearctic
      Ecozone <http://www.bbc.co.uk/nature/ecozones/Nearctic_ecozone.rdf>`__
      refers to the habitats it contains and the species that live in
      that ecozone. A semantic web agent can therefore begin traversing
      the graph to find more related data. The RDF document returned
      from that URI also includes a seeAlso relationship to another
      document that lists all ecozones.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      The ``rdfs:seeAlso`` relationship is intended to support some
      hypertext links between RDF documents on the web. There are no
      explicit semantics for the property other than that a user agent
      might expect to find additional, relevant RDF data about a
      resource at the indicated location. Using this relationship allows
      documents to be linked together without requiring semantic
      relations to be specified between resources where none exists.

      By ensuring that data from a Linked Data site is robustly linked
      together, it helps semantic web crawlers and user agents to
      traverse the site to find all relevant material. The
      ``rdfs:seeAlso`` relation is therefore well-suited for publishing
      simple directories of links for a crawler to follow.

      The relation can also be used to refer to other documents on the
      web, e.g. published by third-parties, that may contain additional
      useful `Annotation <annotation.html>`__ data.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Annotation <annotation.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <progressive-  | `Up <publishi        |  `Next               |
   | enrichment.html>`__  | ng-patterns.html>`__ |  <unpublish.html>`__ |
   +----------------------+----------------------+----------------------+
   | Progressive          | `Ho                  |  Unpublish           |
   | Enrichment           | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
