.. _nary-relation:

N-Ary Relation
==============

*How can a complex relation, involving several resources, be modelled as RDF?*

Context
#######

An RDF triple expresses a relationship between at most two
resources. However some relationships are not binary and involve
the equal participation of several different resources. This is
most common in the case of events, where the event is a relation
between several resources, e.g. a Purchase is an n-ary
relationship between a Person, a Product, and a Seller. All of
those participants are key to the relationship.

Solution
########

Create a class for the relationship, and create instances of that
resource to relate together the other resources that are involved
in the relation.

Example(s)
##########

.. code-block::

   ex:bob a foaf:Person.
   ex:mary a foaf:Person.
   ex:conferenceCentre a ex:Building.
   ex:legoinc a foaf:Organization.

   _:event1 a ex:Conference;
     dc:title "Lego Hack Day";
     ex:organizer ex:mary;
     ex:attendee ex:bob;
     ex:sponsor ex:legoinc;
     ex:location ex:conferenceCentre.

Discussion
##########

:ref:`Qualified Relation <qualified-relation>` pattern as both involve the
same basic solution: modelling a relationship as a resource rather
than a property. They differ in their context. In the Qualified
Relation pattern the desire is to annotate a relationship between
two resources, whereas in the N-ary Relation pattern the goal is
to represent a complex relation between several resources.

Related
#######

- :ref:`Qualified Relation <qualified-relation>`

Further Reading
###############

- `Defining N-ary Relations on the Semantic Web <https://www.w3.org/TR/swbp-n-aryRelations/>`__
