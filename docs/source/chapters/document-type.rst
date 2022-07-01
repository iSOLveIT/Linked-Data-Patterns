.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Document Type        |                      |                      |
   +======================+======================+======================+
   | `Prev <dataset-aut   | C                    |  `Next               |
   | odiscovery.html>`__  | hapter 4. Publishing | <edit-trail.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Document Type
               :name: document-type
               :class: title

   *How can some context be provided about a set of RDF triples
   published to the web?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      While the web of Linked Data is, in its broadest sense, a set of
      RDF triples, there are often circumstances in which it is useful
      to describe a smaller grouping of triples. RDF statements are
      published to the web as documents conforming to a particular
      syntax, e.g. RDF/XML, Turtle, or XHTML+RDFa. These documents may
      be directly inter-linked using `See Also <see-also.html>`__
      relations. To enable user agents to select between links it is
      useful to indicate the type of document which a link is
      referencing.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Define a document type describing a conceptual or physical
      grouping of triples. Indicate where a specific document is of a
      particular type, including a `Topic
      Relation <topic-relation.html>`__ such as ``foaf:primaryTopic`` to
      relate the document to the resource(s) it is describing.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      .. code:: programlisting



         #document type
         foaf:PersonalProfileDocument a foaf:Document.

         #specific instance of document, with indication of its topic
         <http://www.example.org/doc/john> a foaf:PersonalProfileDocument;
            foaf:primaryTopic <http://www.example.org/doc/john#me>.

         <http://www.example.org/doc/john#me> a foaf:Person;
            foaf:name "John".

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      XML is a document format and XML schemas describe the valid
      structure of documents. In contrast RDF is defined in terms of
      sets of triples and schemas are used to support inferencing and
      description of data structures. It is often useful to describe
      specific collections of triples. For example within a triple store
      it is often useful to group triples into `Named
      Graphs <named-graphs.html>`__. These collections can be usefully
      annotated in various ways, e.g. indicating their provenance,
      creation date, origin, etc.

      Collections of triples may be published to the web using a variety
      of syntaxes and mechanisms. It can be useful to partition data
      into a number of different documents, e.g. to simplify the
      publishing process or usefully present data to user agents. By
      annotating the documents to indicate their type we can usefully
      allow user agents to select specific collections that are more
      likely to contain information of interest. This can help target
      crawler behaviour or prioritise documents for de-referencing.

      Using document types does not imply that a user agent can make
      assumptions about the structure or format of the data that will be
      retrievable. The document may contain information about any number
      of different resources, or use any RDF syntax.

      Two well deployed examples of document typing in use today are RSS
      1.0 and FOAF. RSS 1.0 is defined as both an XML and an RDF
      vocabulary and as such has a strict definition of document that
      aligns with its use in an XML context. FOAF however is an RDF
      vocabulary, but has still found it useful to define the notion of
      a ``foaf:PersonalProfileDocument`` which indicates that a document
      primarily describes a particular person (but may include
      additional data).

      The Document Type pattern is most commonly used in conjunction
      with the `See Also <see-also.html>`__ and
      `Annotation <annotation.html>`__ patterns. It could also usefully
      be applied when referencing a `Link Base <link-base.html>`__,
      allowing a user agent to more easily discover `Equivalence
      Links <equivalence-links.html>`__ related to a specific
      resource(s).

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Named Graphs <named-graphs.html>`__
         -  `See Also <see-also.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <dataset-aut   | `Up <publishi        |  `Next               |
   | odiscovery.html>`__  | ng-patterns.html>`__ | <edit-trail.html>`__ |
   +----------------------+----------------------+----------------------+
   | Dataset              | `Ho                  |  Edit Trail          |
   | Autodiscovery        | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
