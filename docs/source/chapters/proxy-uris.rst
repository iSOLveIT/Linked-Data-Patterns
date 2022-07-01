.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Proxy URIs           |                      |                      |
   +======================+======================+======================+
   | `Prev <patt          | C                    |  `Next <             |
   | erned-uris.html>`__  | hapter 2. Identifier | rebased-uri.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Proxy URIs
               :name: proxy-uris
               :class: title

   *How do we deal with lack of standard identifiers for third-party
   resources?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      While it is a goal to reuse identifiers across datasets wherever
      possible, this is often difficult to achieve in practice. An
      authority for some specific data, e.g. ISO, may not have assigned
      unique URIs to resources in their dataset. Datasets also appear
      online at different times, making reuse difficult until more
      authoritative data appears and convergence happens on common
      identifiers. In these circumstances, how should identifiers be
      created for these third-party resources.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Treat third-party resources identically to those in your own data
      and assign them URIs within your domain.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      There is still no agreed standard way of generating URIs for
      Internet Media Types. IANA have adopted RDF for publishing
      descriptions of registered media types. A data set containing
      descriptions of images may therefore use locally minted URIs for
      those media types:

      .. code:: programlisting


         ex:anImage a foaf:Image;
           dc:format <http://www.example.org/media-types/image/jpeg>

           

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      A publisher should focus on their immediate goal of opening up
      their data, ensuring that the published data is internally
      consistent and has identifiers for all key concepts. If existing
      identifiers exist then these should be reused. Where they don't
      then new locally minted URIs should be created from `Shared
      Keys <shared-keys.html>`__.

      Once the data has been published, some alignment can take place
      within a community to achieve agreement on standard URIs for
      shared identifiers. One approach for achieving this alignment is
      to publish `Equivalence Links <equivalence-links.html>`__.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Shared Keys <shared-keys.html>`__
         -  `Equivalence Links <equivalence-links.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <patt          | `Up <identifi        |  `Next <             |
   | erned-uris.html>`__  | er-patterns.html>`__ | rebased-uri.html>`__ |
   +----------------------+----------------------+----------------------+
   | Patterned URIs       | `Ho                  |  Rebased URI         |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
