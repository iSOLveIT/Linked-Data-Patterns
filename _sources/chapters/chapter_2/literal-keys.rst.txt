.. _literal-keys:

Literal Keys
============

               :name: literal-keys
               :class: title

   *How do we publish non-global identifiers in RDF?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      The `Natural Keys <natural-keys.html>`__ pattern encourages the
      creation of URIs from existing non-global identifiers. While this
      provides a way to begin identifying a resource so that we can
      describe it in RDF, it does not address the issue of how to
      publish these existing identifiers. Nor does it address situations
      where natural keys change over time, e.g. the move from ISBN-10 to
      ISBN-13 in the publishing world.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create a custom property, as a sub-class of the dc:identifier
      property for relating the existing literal key value with the
      resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The nasa dataset in dataincubator uses `Patterned
      URIs <patterned-uris.html>`__ based on the NSSDC international
      designator, but includes these as literal values associated with
      each spacecraft using a custom property.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      While hackable URIs are a useful short-cut they don't address all
      common circumstances. For example different departments within an
      organization may have different non-global identifiers for a
      resource; or the process and format for those identifiers may
      change over time. The ability to algorithmically derive a URI is
      useful but limiting in a global sense as knowledge of the
      algorithm has to be published separately to the data.

      By publishing the original "raw" identifier as a literal property
      of the resource we allow systems to look-up the URI for the
      associated resource using a simple SPARQL query. If multiple
      identifiers have been created for a resource, or additional
      identifiers assigned over time, then these can be added as
      additional repeated properties.

      For systems that may need to bridge between the Linked Data and
      non-Linked Data views of the world, e.g. integrating with legacy
      applications and databases that do not store the URI, then the
      ability to find the identifier for the resource provides a useful
      integration step.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Patterned URIs <patterned-uris.html>`__
         -  `Natural Keys <natural-keys.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <hierarc       | `Up <identifi        |  `Next <n            |
   | hical-uris.html>`__  | er-patterns.html>`__ | atural-keys.html>`__ |
   +----------------------+----------------------+----------------------+
   | Hierarchical URIs    | `Ho                  |  Natural Keys        |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
