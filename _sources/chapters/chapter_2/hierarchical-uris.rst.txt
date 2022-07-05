.. _hierarchical-uris:

Hierarchical URIs
=================

               :name: hierarchical-uris
               :class: title

   *How should URIs be assigned to a group of resources that form a
   natural hierarchy?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      It is often the case that a collection of resources may form a
      natural hierarchy. E.g. the chapters within a book, or the
      departments within an organization. Reflecting this strict
      hierarchy within the URI structure makes those URIs more hackable
      allowing users/developers to "navigate" up the hierarchy by
      pruning the URI.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Where a natural hierarchy exists between a set of resources use
      `Patterned URIs <patterned-uris.html>`__ that conform to the
      following pattern:

      ``:collection/:item/:sub-collection/:item``

      E.g. in a system which is publishing data about individual books
      and their chapters, we might use the following identifier for
      chapter 1 of a specific book:

      ``/books/12345/chapters/1``

      The ``/chapters`` URI will naturally reflect to the collection of
      all chapters within a specific book. The ``/books`` URI maps to
      the collection of all books within a system, etc.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The discogs dataset in dataincubator uses hierarchical uris of the
      form:

      ``http://discogs.dataincubator.org/release/22530/track/1-01``

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      This technique is best suited to scenarios where the items in the
      sub-collections (chapters) are always associated with a single
      parent item. Other relationships might exist, e.g. the chapter may
      be included in another but the chapter is always associated with
      at least one book: they do not exist in isolation. In
      circumstances where this doesn't hold true, then it is best to
      just use simple Patterned URIs.

      The same applies to circumstances where the hierarchy may change
      over time.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Patterned URIs <patterned-uris.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <identifie     | `Up <identifi        |  `Next <l            |
   | r-patterns.html>`__  | er-patterns.html>`__ | iteral-keys.html>`__ |
   +----------------------+----------------------+----------------------+
   | C                    | `Ho                  |  Literal Keys        |
   | hapter 2. Identifier | me <index-2.html>`__ |                      |
   | Patterns             |                      |                      |
   +----------------------+----------------------+----------------------+
