.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Missing Isn't Broken |                      |                      |
   +======================+======================+======================+
   | `Prev <follow        | Ch                   |  `Next <             |
   | -your-nose.html>`__  | apter 6. Application | named-query.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Missing Isn't Broken
               :name: missing-isnt-broken
               :class: title

   *How do we handle the potentially messy or incomplete data we use
   from the web?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      In RDF anyone can say anything, anywhere. In other words anyone
      can make statements about a resource and publish that to the web
      for others to use. There is no requirement about how much data
      needs to be published: there are no validation rules that require
      a minimum amount of data. This means that data on the web may be
      of varying quality or of varying detail.

      This variation is partly a factor of the flexibility of the model,
      but is really also a fact of life when dealing with any data or
      content found on the web: even within well-defined standards there
      may be varying levels of detail available.

      How do we deal with this in our Linked Data applications?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Recognise that "missing isn't broken"

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      An application might chose to render as much of a FOAF profile
      (for example) as it can, even though individual profiles might be
      of varying details.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      This pattern is really just a restatement of `Postel's Law <#>`__:
      *Be conservative in what you send; be liberal in what you accept*.
      This advice is particularly applicable when dealing with any data
      or content obtained from the web. Applications ought to be
      tolerant of missing or invalid data and make best effort to
      process or render what is available

      In a Linked Data context this advice is particularly applicable as
      the flexibility of the RDF model means that there is greater
      chance for variation in detail across data sources. Rather than
      rely on schema or document validation, as in XML or relational
      database systems, to identify and reject data, applications should
      be designed to be more tolerant.

      Of course an application may require some minimum data in order to
      do anything useful with some data. Although if a data publisher
      has followed the `Label Everything <label-everything.html>`__
      pattern then at a minimum a data browser, for example, may still
      be able to render the name of the resource.

      Unlike other approaches, where data is found to be missing, Linked
      Data provides additional opportunities for finding more data by
      supplementing the available data with additional sources, E.g. by
      using the `Follow Your Nose <follow-your-nose.html>`__ pattern.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Follow Your Nose <follow-your-nose.html>`__
         -  `Label Everything <label-everything.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Missing Isn't Broken <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <follow        | `Up <applicati       |  `Next <             |
   | -your-nose.html>`__  | on-patterns.html>`__ | named-query.html>`__ |
   +----------------------+----------------------+----------------------+
   | Follow Your Nose     | `Ho                  |  Named Query         |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
