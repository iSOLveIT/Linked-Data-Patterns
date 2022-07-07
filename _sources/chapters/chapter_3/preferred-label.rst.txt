.. _preferred-label:

Preferred Label
===============

*How can a simple unambiguous label be provided for a resource?*

Context
#######

There are many different RDF properties that can be used for
expressing a label, including generic properties such as
rdfs:label and more domain specific labels such as foaf:name. This
presents a variety of choices to the data provider, and can be
confusing for application authors.

Solution
########

Use ``skos:prefLabel`` to publish the preferred display label for a resource

Example(s)
##########

A library system publishes Linked Data about authors. The
preferred mechanism for specifying author names is using a
normalized form, e.g Surname, First Name. This preferred label can
be specified using ``skos:prefLabel``, but the authors full name,
and part names can be published using properties from FOAF. A
simple Linked Data browser may use the preferred label, whereas an
Address Book application browsing the same data may choose to
assemble display labels according to user defined preferences,
e.g. First Name, Surname.

Discussion
##########

The ``skos:prefLabel`` property, whilst defined in the SKOS
ontology, is a general purpose property that identifies the
preferred label for a resource. By standardising on this property
for labelling data providers and consumers can converge on a
common mechanism for expressing labels of resources.

Having a single preferred property for display labels encourages
convergence but doesn't preclude the use of more specific
properties for other purposes. For example the literal value of
the ``skos:prefLabel`` property can be formatted for display,
leaving other properties, e.g. ``rdfs:label``, ``foaf:name``, etc
to express alternatives or variations in labels or naming. A
client that is aware of the meaning of specific predicates may
choose to build labels using alternate logic, but having a label
unambiguously specified simplifies application development.
