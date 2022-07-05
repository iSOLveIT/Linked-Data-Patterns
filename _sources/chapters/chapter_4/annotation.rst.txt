.. _annotation:

Annotation
==========

               :name: annotation
               :class: title

   *How can data about third-party resources be published as part of a
   dataset?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Datasets are rarely completely self-contained. They will often
      contain facts or data about third-party resources. These may be
      entities from other systems or existing web documents that are
      part of an external system or website. It should be possible to
      surface this information alongside the data that originates in the
      dataset.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Just publish RDF documents containing the statements about the
      external resources

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      Linked Data available from ``http://www.example.org/author/john``
      when retrieved might contain the following data which contains
      annotations about two additional resources:

      .. code:: programlisting


         <http://www.example.org/author/john> a foaf:Person.

         <http://wiki.example.net/page/UbuntuTips>
           dc:title "Ubuntu Tips";
           dc:creator <http://www.example.org/author/john>.

         <http://publisher.example.org/authors/1234>
           owl:sameAs <http://www.example.org/author/john>.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      With RDF Anyone can say Anything Anywhere, there are no
      restrictions about who may make statements about a resource;
      although clearly a processing application might want to pick its
      sources carefully.

      It is entirely consistent with the Linked Data principles to make
      statements about third-party resources. While in some cases it is
      useful to use the `Proxy URIs <proxy-uris.html>`__ pattern, in
      many cases simply making statements about external resources,
      whether these are entities (e.g. a person) or documents (e.g. a
      web page) is sufficient.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Proxy URIs <proxy-uris.html>`__
         -  `Topic Relation <topic-relation.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <publishin     | `Up <publishi        |  `Next <au           |
   | g-patterns.html>`__  | ng-patterns.html>`__ | todiscovery.html>`__ |
   +----------------------+----------------------+----------------------+
   | C                    | `Ho                  |  Autodiscovery       |
   | hapter 4. Publishing | me <index-2.html>`__ |                      |
   | Patterns             |                      |                      |
   +----------------------+----------------------+----------------------+
