.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Shared Keys          |                      |                      |
   +======================+======================+======================+
   | `Prev <r             | C                    |  `Nex                |
   | ebased-uri.html>`__  | hapter 2. Identifier | t <url-slug.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Shared Keys
               :name: shared-keys
               :class: title

   *How do we simplify the inter-linking of datasets?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      It is common to carry out inter-linking of datasets as a separate
      activity following the initial modelling and data conversion
      exercises have been completed. How can the final stage of
      inter-linking be simplified?

      It is also common that within a specific domain there will be a
      set of non-web identifiers that are standardised across different
      applications and publishers. How can the inter-linking of those
      datasets be simplified, encouraging convergence on web
      identifiers?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create `Patterned URIs <patterned-uris.html>`__ by applying the
      `Natural Keys <natural-keys.html>`__ pattern, but prefer public,
      standard identifiers rather than internal system specific codes.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The BBC have created URIs for artists that are algorithmically
      related to the MusicBrainz URIs using a common Shared Key.
      MusicBrainz URIs are `Patterned URIs <patterned-uris.html>`__
      built from a "MusicBrainz ID", e.g.
      ``a74b1b7f-71a5-4011-9441-d0b5e4122711``. The MusicBrainz and BBC
      URIs are shown below:

      .. code:: programlisting

         http://www.bbc.co.uk/music/artists/a74b1b7f-71a5-4011-9441-d0b5e4122711
         http://musicbrainz.org/artist/a74b1b7f-71a5-4011-9441-d0b5e4122711

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Predictable URIs structures make it easy for application
      developers and toolkits to build URIs from simple templates. By
      using URIs that are constructed from public identifiers, that
      already have scope outside of the immediate application, it
      increases the ease with which inter-linking can take place. For
      example, the pattern may avoid the need to look-up URIs in a
      SPARQL endpoint, allowing a developer to simplify use a URI
      template.

      The Shared Keys pattern is best suited to situations where the
      shared identifiers are stable and rarely change.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Patterned URIs <patterned-uris.html>`__>
         -  `Natural Keys <natural-keys.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <r             | `Up <identifi        |  `Nex                |
   | ebased-uri.html>`__  | er-patterns.html>`__ | t <url-slug.html>`__ |
   +----------------------+----------------------+----------------------+
   | Rebased URI          | `Ho                  |  URL Slug            |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
