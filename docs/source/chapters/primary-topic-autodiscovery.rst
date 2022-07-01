.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Primary Topic        |                      |                      |
   | Autodiscovery        |                      |                      |
   +======================+======================+======================+
   | `Prev <materialize-  | C                    |  `Next <progressive  |
   | inferences.html>`__  | hapter 4. Publishing | -enrichment.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Primary Topic Autodiscovery
               :name: primary-topic-autodiscovery
               :class: title

   *How can people identify the principal subject of a given web page?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Often a web page is concerned with a particular physical object or
      other resource. To assist discovery and aggregation of pages about
      particular topics the publisher wants to indicate the URI of this
      resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      When publishing a web page include a link element in the head of
      the web page pointing to the URI of the page's primary topic. Use
      a rel attribute value of "primarytopic".

      ``<link rel="primarytopic" href="http://dbpedia.org/resource/London"/>``

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      Associating a wikipedia page with the equivalent dbpedia resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Many pages on the Web are explicitly about a single subject.
      Examples include Amazon product pages, Wikipedia entries, blogs
      and company home pages. Without an explicit link, content
      aggregators must resort to heuristic inference of the topic which
      is prone to classification error. Often the original publisher
      knows the specific topic and would like to provide this as a hint
      to aggregators and other content consumers.

      Even when the page is about several topics there can be a single
      primary topic that can be linked to directly.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Autodiscovery <autodiscovery.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <materialize-  | `Up <publishi        |  `Next <progressive  |
   | inferences.html>`__  | ng-patterns.html>`__ | -enrichment.html>`__ |
   +----------------------+----------------------+----------------------+
   | Materialize          | `Ho                  |  Progressive         |
   | Inferences           | me <index-2.html>`__ | Enrichment           |
   +----------------------+----------------------+----------------------+
