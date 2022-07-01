.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Topic Relation       |                      |                      |
   +======================+======================+======================+
   | `Prev <repeate       | Chapter 3. Modelling |  `Next <ty           |
   | d-property.html>`__  | Patterns             | ped-literal.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Topic Relation
               :name: topic-relation
               :class: title

   *How can a web page or document be associated with a resource?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      There is often a need to associate a resource with a page or
      document that provides further, human-readable content about the
      resource. This information may often be present in a content
      management system or dataset as "further reading" links. How can
      these relations be published as RDF, clearly identifying the
      relationship between the document and the resource being
      described?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Use the ``foaf:topic`` and/or ``foaf:primaryTopic`` relationships
      to associate a resource with a page(s) in which it is featured or
      discussed

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      In a dataset describing Paris, some additional further reading
      links may be available:

      .. code:: programlisting


         <http://www.example.org/place/Paris> a ex:Place;
            skos:prefLabel "Paris"@fr.

         <http://travel.example.com/blog/a-paris-guide>
            foaf:primaryTopic <http://www.example.org/place/Paris>.

         <http://travel.example.com/blog/top-europe-cities>
            foaf:topic <http://www.example.org/place/Paris>.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      There will always be a mix of unstructured documents and
      structured data on the Semantic Web. There are many kinds of
      relations that could be expressed between a document and a
      resource, but a very common relation is one of categorisation,
      e.g. identifying when a document or page has a specific focus or
      theme. The FOAF topic terms, ``foaf:topic`` and
      ``foaf:primaryTopic`` provide a means to link a document directly
      with a resource which features as a topic in that document.

      Other vocabularies provide similar related properties that may be
      more useful in some scenarios. For example Dublin Core defines the
      ``dc:subject`` property, but this is best used to relate a
      document to an entry in a controlled vocabulary, e.g. a subject
      heading, rather than a "real world" resource.

      Because the Topic Relation pattern involves making statements
      about other resources on the web, it is an application of the
      `Annotation <annotation.html>`__ pattern.

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
   | `Prev <repeate       | `Up <modelli         |  `Next <ty           |
   | d-property.html>`__  | ng-patterns.html>`__ | ped-literal.html>`__ |
   +----------------------+----------------------+----------------------+
   | Repeated Property    | `Ho                  |  Typed Literal       |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
