.. _composite-descriptions:

Composite Descriptions
======================

               :name: composite-descriptions
               :class: title

   *How do we declare the underlying dataset for a page involving custom
   subsets or views of the data?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      When integrating data from heterogenous sources it is sometimes
      necessary to synthesise page URIs non-algorithmically from the
      underlying data. Alternatively views of data may be required that
      follow a clustering or structure that does not have a simple 1:1
      correspondence with underlying data URIs.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Create data about your description pages and include foaf:topic
      and foaf:primaryTopic properties to link the page to the resources
      that it describes. When rendering these pages obtain the data
      describing the page then bring in descriptions of each resource
      referenced with ``foaf:topic`` and ``foaf:primaryTopic`` to build
      the base dataset for the page.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      The BBC programme pages include information on a primary topic
      supplemented with additional data about other related topics. The
      data included on each page may vary depending on factors other
      than the type of resource being described.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Most database driven pages on the Web involve more than one type
      of data and augment a base dataset with related information by
      using multiple database queries. In many cases it is possible for
      the publisher to anticipate these arrangements and describe them
      as linked data. This can reduce multiple queries to a single query
      describing the resource and any related resources. The resulting
      dataset can be passed directly to a templating system for
      rendering.

      The topics associated with a page do not need to be closely
      related in the underlying data or even connected at all. The page
      description gathers together a group of resources according to the
      precise context specified by the publisher without reliance on
      particular relationships pre-existing in the data.

      Changing the level of detail for classes of page or even of
      specified individual pages can be done simply by updating the
      description of those pages and allowing the templating system to
      work with the new dataset.

      An additional benefit is that the page structure of the site can
      also be made queryable so it would be possible to discover which
      pages include information about a specific subject, thereby
      presenting the possibility of automatic cross-linking.

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <bounded-d     | `Up <applicati       |  `Next <follo        |
   | escription.html>`__  | on-patterns.html>`__ | w-your-nose.html>`__ |
   +----------------------+----------------------+----------------------+
   | Bounded Description  | `Ho                  |  Follow Your Nose    |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
