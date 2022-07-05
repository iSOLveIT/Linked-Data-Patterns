.. _natural-keys:

Natural Keys
============

               :name: natural-keys
               :class: title

   *How can we create unique URIs from data that already has unique
   identifiers?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      It is often the case that a group of resources already have a
      unique identifier. This might be a local system identifier derived
      from, e.g. a database key; or a global non-URI identifier, e.g. an
      ISBN.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Mint URIs that are algorithmically derived from the existing
      non-URI identifier. This can be as simple as concatenating the
      existing identifier or key with a suitable base URI. The existing
      identifier may need to be URL encoded before creating the URI. It
      is common to combine this technique with Patterned URIs.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The BBC programmes website uses URIs that are derived from its
      existing "programme id" or pid.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Where resources are already associated with existing keys, it is
      likely that the creation and management of those identifiers will
      already be supported by a specific technology or process. There is
      a need to be able to create global URI based identifiers for these
      resources without creating unnecessary additional overheads in
      creating entirely new identifiers and/or mapping between URIs and
      existing keys.

      By deriving the URI from the natural key for the identifier we
      avoid the need to create a new process for assigning identifiers
      and largely eliminate the need to have a mapping between the two
      identification systems.

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
   | `Prev <li            | `Up <identifi        |  `Next <pat          |
   | teral-keys.html>`__  | er-patterns.html>`__ | terned-uris.html>`__ |
   +----------------------+----------------------+----------------------+
   | Literal Keys         | `Ho                  |  Patterned URIs      |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
