.. container:: navheader

   +----------------------+----------------------+----------------------+
   | URL Slug             |                      |                      |
   +======================+======================+======================+
   | `Prev <s             | C                    |  `Next <modelli      |
   | hared-keys.html>`__  | hapter 2. Identifier | ng-patterns.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: URL Slug
               :name: url-slug
               :class: title

   *How can we create URLs from arbitrary text or keywords?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      When generating a URI for an identifier we may not always have a
      simple numeric `Natural Key <natural-keys.html>`__ for a resource.
      In some cases, e.g. for documents, keywords, categories, we may
      only have a title or name.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Apply the `Patterned URI <patterned-uris.html>`__ pattern to
      create a common root URI and generate a simple URL "slug" by from
      the available text or keywords

      There are several potential algorithms for normalising a string to
      create a URL slug. A typical algorithm would be:

      .. container:: itemizedlist

         -  Lowercase the string
         -  Remove any special characters and punctuation that might
            require encoding in the URL
         -  Replace spaces with a dash

      The original text is then preserved by using it to
      `label <label-everything.html>`__ the resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      For example if we are generating a URI for a category called
      "Heavy Metal" we might generate a URI as follows

      .. code:: programlisting


         #Generate a patterned URI with a simple URL slug from "Heavy Metal"
         <http:www.example.org/category/heavy-metal>
           rdfs:label "Heavy Metal" 

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Clean URLs are easier to work with. If a dataset (or any website)
      has an inconsistent policy about the casing and encoding used in
      URLs then it can be more difficult to generate links to that
      dataset.

      The use of URL slugs is prevalent in a number of different web
      frameworks already, e.g. blogging platforms. So this approach is
      already well-deployed.

      Normalization of text strings can be problematic if it results in
      the same URL slug being generated for different resources. In some
      systems names and titles may be unique so this might not be an
      issue. Using patterned URIs to divide the URI space into different
      "sections" for different types of resources can help avoid
      unwanted collisions. Obviously in some cases collisions might be
      useful, e.g. to ensure that user input, which might vary in
      casing, is normalized into a standard form.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Patterned URI <patterned-uris.html>`__
         -  `Natural Key <natural-keys.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Slug (web publishing) on Wikipedia <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <s             | `Up <identifi        |  `Next <modelli      |
   | hared-keys.html>`__  | er-patterns.html>`__ | ng-patterns.html>`__ |
   +----------------------+----------------------+----------------------+
   | Shared Keys          | `Ho                  |                      |
   |                      | me <index-2.html>`__ | Chapter 3. Modelling |
   |                      |                      | Patterns             |
   +----------------------+----------------------+----------------------+
