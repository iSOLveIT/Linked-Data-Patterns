.. _graph-per-resource:

Graph Per Resource
==================


*How can we organise a triple store in order to make it easy to manage the statements about an individual resource?*

Context
#######

Web applications typically offer forms for editing the description
of an individual resource, e.g. the title, description and tags
that apply to a specific photo. RESTful APIs typically support
replacing the description of a resource using a PUT operation. In
both cases it would be useful to be able to serialize all of the
statements relating to a given resource, including any edits, and
directly replace the relevant triples in a triple store backing
the application or API.

Solution
########

Store the description of each resource in a separate
:ref:`Named Graph <named-graphs>` using a graph URI derived from the
resource URI as the graph URI. When the resource is updated,
simply replace the contents of that graph with the latest state of
the resource.

Example(s)
##########

A user is editing the description of
``http://example.org/picture/1``. The application delivers a web
form to the authorised user which presents the current description
of the resource in an interactive editing form. When the client
submits the changes back to the server, it does so by serializing
the state of the form as RDF which is then processed by the
server.

On receiving the update from the client, the server-side code
computes the graph URI for the resource being edited. For this
application graph URIs are derived from resource URIs by a simple
rewrite. For example the data for ``http://example.org/picture/1``
is stored in ``http://data.example.org/graphs/picture/1``.

To apply the update the server-side code simply determines the
appropriate graph URI and then stores the data in a
`SPARQL 1.1. Graph Store Protocol <https://www.w3.org/TR/sparql11-http-rdf-update/>`__ enabled store using a simple PUT
operation.

Discussion
##########

Partitioning the triple store by resource rather than by
:ref:`source <graph-per-source>` provides an easy way to quickly
access the description of an individual resource without having to
use a SPARQL query. This is particularly true if the graph URI for
a resource can be derived using a simple algorithm, e.g. rewriting
to a different base URI, pre-pending a known prefix, etc.

The `SPARQL 1.1. Graph Store Protocol <https://www.w3.org/TR/sparql11-http-rdf-update/>`__ provides a way for
code to find and update the description of a resource without
needing further knowledge of the data stored about any specific
resource. This allows server-side code to remain relatively
generic: it doesn't need to know details about what kinds of data
is captured about individual resources, it just needs to know
where to persist the data its given.

When applying this pattern it is common to store a
:ref:`bounded description <bounded-description>` of the resource in each
graph ensuring that each graph has a clear scope.

While this pattern makes it easy to manage a bounded description
for a resource, including its relationships to other resource, it
doesn't help with managing references to the resource elsewhere in
the store. E.g. if a resource is deleted (by removing its graph),
there may still be statements relating to that resource elsewhere
in the graph. Additional SPARQL Update operations, for example,
would be needed to remove these statements. Depending on the
complexity of the graph structure and the needs of the application
these overheads might make this pattern unsuitable.

In circumstances where additional context is required, e.g.
in-bound relations, for an application view, a fall-back to SPARQL
queries over a :ref:`Union Graph <union-graph>` of the store can
provide additional flexibility. However for the simplest cases of
serving Linked Data pages, this pattern makes for very simple and
light-weight application code.

For very simple use cases the graph URI of the graph holding the
description of the resource could in fact be the resource URI.
However in practice this can limit system evolution. As explained
in the :ref:`Graph Annotation <graph-annotation>` pattern, the
ability to store additional graph metadata can be useful. And in
that case a separate graph URI is essential to avoid potential
confusion around the scope of individual statements.

In some applications several different processes might contribute
to the creation of a description of a resource. Using a single
graph per resource might therefore involve contention around
several processes. The
:ref:`Graph Per Aspect <graph-per-aspect>` pattern allows this contention
to be removed by using multiple graphs per resource.

Related
#######

- :ref:`Named Graph <named-graphs>`
- :ref:`Graph Annotation <graph-annotation>`
- :ref:`Graph Per Source <graph-per-source>`
- :ref:`Graph Per Aspect <graph-per-aspect>`

Further Reading
###############

- `Named Graph (Wikipedia) <https://en.wikipedia.org/wiki/Named_graph>`__
- `Managing RDF using Named Graphs <https://blog.ldodds.com/2009/11/05/managing-rdf-using-named-graphs/>`__
