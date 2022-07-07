.. _qualified-relation:

Qualified Relation
==================

*How can we describe or qualify a relationship between two resources?*

Context
#######

In some cases relationships need to be qualified or annotated in
some way. There are a number of different use cases that required
this capability. E.g. to indicate the date when a specific
relationship was made, or to indicate its source, or perhaps
associate it with a probability or other similar qualifier. RDF
only allows binary relations between resources, so how can these
additional qualified relations be expressed?

Solution
########

Create a class for the relationship and create instances of that
resource to relate together the resources that are involved in the
relation. The relationship resource can then be annotated to
qualify the relation further.

Example(s)
##########

Marriage is a relationship that could be modelled as a simple
relationship between two people. But that simplistic approach
doesn't let us capture the date that the marriage started (or
ended). Modelling the marriage as a relationship allows the
relationship to be annotated:

.. code-block::

   eg:bob a foaf:Person.
   eg:mary a foaf:Person.

   _:bobMaryMarriage a ex:Marriage;
       ex:partner eg:bob;
       ex:partner eg:mary;
       ex:date "2009-04-01"^^xsd:date.

A diagnosis can be viewed as a relationship between a person and a
disease. A diagnosis needs to be qualified with a probability. By
creating a class to model the diagnosis explicitly, as well as
additional properties for relating the diagnosis to a patient and
a disease, it becomes possible to annotate the relationship with
qualifying properties:

.. code-block::

   eg:bob a foaf:Person.

   eg:measles a ex:Disease.

   _:bobDiagnosis a ex:Diagnosis;
       ex:patient eg:bob;
       ex:disease eg:meases;
       ex:probability "high";
       ex:diagnostician ex:drhouse.

Discussion
##########

Modelling relationships as resources works around the limitations
of simple binary predicates. Creating a resource for the
relationship allows much more flexibility in qualifying or
describing the relationships between resources. Any number of
additional properties may be used to annotate the relation. When
the relationship is between two resources we refer to it as a
qualified relation, when it is between several resources, each of
which are equally involved in the relationship then we have an
:ref:`N-Ary Relation <nary-relation>`.

If modelling relationships as classes is useful, then why not use
this pattern for all non-trivial relationships in a model? The
main reason is that it causes explosion in the number of terms in
a vocabulary, e.g. each predicate is replaced with two predicates
and a class. A vocabulary can quickly become unwieldy, so the
value of the extra modelling structure needs to be justified with
clear requirements for needing the extra complexity. As described
here, the primary reason is to qualify the relation.

The only alternative to this approach would be to have another
independent property whose value is intended to be interpreted
alongside one or more other properties of the same resource, e.g.:

.. code-block::

   eg:bob a foaf:Person.
   eg:mary a foaf:Person.

   eg:bob ex:partner eg:mary.
   eg:bob ex:weddingDay "2009-04-01"^^xsd:date.
   eg:mary ex:weddingDay "2009-04-01"^^xsd:date.


In the above alternative the marriage relationship between two
people is expressed using the ``ex:partner`` relation and the date
of the wedding with the separate ``ex:weddingDay`` property. On
the surface this seems simpler but loses flexibility and clarity.
Firstly there could be a large number of additional properties
associated with the marriage relation, all of these would need to
be added to the model, and applications would need to know that
this collection of properties were all related in some way (i.e.
were about a marriage). It also fails to model divorces and
re-marriages. Adding a relation resource deals with this better as
we have greater clarity in the model about the relationship and
its specific properties.

There are a number of cases where adding resources into a data
model in this way can aid expressive, understanding when and
when not to apply the pattern is an important part of RDF
modelling.

Related
#######

- :ref:`N-Ary Relation <nary-relation>`
