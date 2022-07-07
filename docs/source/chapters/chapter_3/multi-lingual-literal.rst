.. _multi-lingual-literal:

Multi-Lingual Literal
=====================

*How can internationalized text be expressed in RDF?*

Context
#######

It is increasingly common for data to contain internationalized
text, e.g. translated titles for a document. This alternate
language text needs to be associated with the relevant resource in
a clearly identifiable way

Solution
########

Multi-lingual versions of a literal property can be expressed as a
simple :ref:`Repeated Property <repeated-property>` with the
addition of a language code to distinguish between the alternate
versions.

Example(s)
##########

``_:greeting a ex:LoginGreeting; skos:prefLabel "Hello!"; skos:prefLabel "Hola!"@es.``

Discussion
##########

RDF allows a literal value to be associated with a language code.
This code indicates the language in which the value of the literal
has been expressed. RDF uses the ISO standard language codes,
including regional variants. This capability lowers the bar to
internationalizing data that is published as RDF. All
serializations support this functionality and the SPARQL query
language provides several functions for matching and manipulating
language codes.

Related
#######

- :ref:`Repeated Property <repeated-property>`
