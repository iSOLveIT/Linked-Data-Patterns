.. _document-type:

Document Type
=============

*How can some context be provided about a set of RDF triples published to the web?*

Context
#######

While the web of Linked Data is, in its broadest sense, a set of
RDF triples, there are often circumstances in which it is useful
to describe a smaller grouping of triples. RDF statements are
published to the web as documents conforming to a particular
syntax, e.g. RDF/XML, Turtle, or XHTML+RDFa. These documents may
be directly inter-linked using :ref:`See Also <see-also>`
relations. To enable user agents to select between links it is
useful to indicate the type of document which a link is
referencing.

Solution
########

Define a document type describing a conceptual or physical
grouping of triples. Indicate where a specific document is of a
particular type, including a :ref:`Topic Relation <topic-relation>`
such as ``foaf:primaryTopic`` to
relate the document to the resource(s) it is describing.

Example(s)
##########

.. code-block::

   #document type
   foaf:PersonalProfileDocument a foaf:Document.

   #specific instance of document, with indication of its topic
   <http://www.example.org/doc/john> a foaf:PersonalProfileDocument;
      foaf:primaryTopic <http://www.example.org/doc/john#me>.

   <http://www.example.org/doc/john#me> a foaf:Person;
      foaf:name "John".

Discussion
##########

XML is a document format and XML schemas describe the valid
structure of documents. In contrast RDF is defined in terms of
sets of triples and schemas are used to support inferencing and
description of data structures. It is often useful to describe
specific collections of triples. For example within a triple store
it is often useful to group triples into
:ref:`Named Graphs <named-graphs>`. These collections can be usefully
annotated in various ways, e.g. indicating their provenance,
creation date, origin, etc.

Collections of triples may be published to the web using a variety
of syntax's and mechanisms. It can be useful to partition data
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
with the :ref:`See Also <see-also>` and
:ref:`Annotation <annotation>` patterns. It could also usefully
be applied when referencing a :ref:`Link Base <link-base>`,
allowing a user agent to more easily discover
:ref:`Equivalence Links <equivalence-links>` related to a specific
resource(s).

Related
#######

- :ref:`Named Graphs <named-graphs>`
- :ref:`See Also <see-also>`
