.. _equivalence-links:

Equivalence Links
=================


*How do we indicate that different URIs refer to the same resource or concept?*

Context
#######

Linked Data is published in a de-centralised way with multiple
people and organisations collectively publishing data about the
same resources. While it is a goal to reuse identifiers wherever
possible this may not always be achievable. If data has been
published in this way, how can links be built between datasets in
order to identify that distinct URIs refer to the same resource?

Solution
########

Use ``owl:sameAs``, ``skos:exactMatch``, or similar specialised
relation, to indicate that two URIs are equivalent.

Example(s)
##########

.. code-block::

   #Statement from Data Set 1
   ex:bob a foaf:Person.

   #Statement from Data Set 2, with equivalence
   ex:otherBob a foaf:Person.
   ex:otherBob owl:sameAs ex:bob.

Discussion
##########

Distributed publishing is a fact of life on the web. Semantic web
technologies have built-in support for handling distributed
publishing of both data and schemas by standardising specific
relations for bringing together disparate datasource's. The most
important of these facilities is the ``owl:sameAs`` relation,
which indicates that two URIs are equivalent. According to the
semantics defined in the OWL standard, the two URIs are synonyms
of each other and all statements made about one of those URIs is
also considered to be true of the other.

With support from a reasoner the ``owl:sameAs`` relation allows a
semantic web application to query and interact with a single view
across any number of datasets. This allows data to be integrated,
without requiring any merging or re-processing of the data. It
also avoids the need for up-front convergence on standard
identifier schemes.

However ``owl:sameAs`` is only one possible equivalence relation
that could be stated between resources. Other vocabularies may
choose to define additional relationships that have less strong
semantics associated with them. For example SKOS defines two
additional properties, ``skos:closeMatch`` and
``skos:exactMatch``, that can be used to state equivalences
between concepts in a thesaurus. The relations allow for more
fuzzy notions of equivalence and have weaker semantics:
``skos:exactMatch`` declares two concepts to be the same but
doesn't imply that all statements about one concept are also true
of another.

OWL also defines some additional specialised equivalence relations
for relating together classes (``owl:equivalentClass``) and
properties (``owl:equivalentProperty``). These should be used
instead of ``owl:sameAs`` when relating together terms in an
ontology.

Related
#######

- :ref:`Proxy URIs <proxy-uris>`
- :ref:`Link Base <link-base>`
