:hide-toc:

.. _chap2:

Identifier Patterns
===================

.. raw:: html

   <h2>Abstract</h2>


The single most important part of the Linked Data
approach is the adoption of web-scale identifiers (URIs)
to identify things of interest: people, events, places,
statistical observations, colours. Anything that we want
to publish data about on the web needs to have a URI,
allowing it to be referenced, browsed and linked using
existing web tools. The existing tools of the web of
documents are already designed to work well with things
that have URIs. We can "like" them, discuss them, and
refer to them in documents.

In RDF we capture data as statements about resources. RDF
allows resources to have global identifiers or to be
un-named "blank nodes". While blank nodes may offer
flexibility for some use cases, in a Linked Data context
blank nodes limit our ability to collaboratively annotate
data. A blank node cannot be the target of a link and we
can't annotate it with new information from new sources.
As one of the biggest benefits of the Linked Data
approach is that "anyone can say anything anywhere", use
of blank nodes undermines some of the advantages we can
gain from wide adoption of the RDF model. Even within the
closed world of a single application dataset, use of
blank nodes can quickly become limiting when integrating
new data.

Successful publishing of Linked Data requires the careful
selection of good, clean, stable URIs for the resources
in a dataset. This means that the most important first
step in any Linked Data project is deciding on an
appropriate identifier scheme: the conventions for how
URIs will be assigned to resources. This is not to say
that conventions won't evolve or be extended over time,
but some upfront thought about identifiers is always
beneficial.

This chapter introduces a collection of design patterns
that promote some principled ways to assign identifiers
within a dataset. All of these patterns are in wide use
today and so are tried and tested in the field.

Many of these patterns are also prevalent in modern web
frameworks and are more generally applicable to URL
design for web applications.

.. rubric:: **Table Of Contents**

.. toctree::
   :maxdepth: 1
   :numbered:

   Hierarchical URIs <hierarchical-uris>
   Literal Keys <literal-keys>
   Natural Keys <natural-keys>
   Patterned URIs <patterned-uris>
   Proxy URIs <proxy-uris>
   Rebased URI <rebased-uri>
   Shared Keys <shared-keys>
   URL Slug <url-slug>