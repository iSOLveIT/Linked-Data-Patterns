.. _index-resources:

Index Resources
===============

*How can ordered collections or indexes be published as RDF?*

Context
#######

It is often the case that a web application will provide its users
with a number of alternative ways to navigate. This might be an
A-Z list of resources, or a list ordered based on creation date or
"interestingness". These collections are useful resources in their
own right that should be published as Linked Data.

Solution
########

Create resources for each "index" and associate the index with the
items that it contains. An rdf:List or rdf:Seq is best used here
as these structured include the notion of ordering that is an
essential aspect of an index.

Example(s)
##########

The BBC music website publishes an A-Z list of artists. But this
does not use a sequence to indicate ordering.

Discussion
##########

By creating separate resources and links between these indexes and
their contents we avoid the need to publish the algorithms that
are used to generate the indexes, we can instead allow machines to
navigate the collection just as a human user would do. This
approach is particularly useful to ensure that data can be crawled
by a semantic web search engine.

If a collection may be unmanageably large, then it can be
decomposed into smaller groupings. E.g. a large A-Z index may be
decomposed into smaller collections: A-C, D-F, etc.

By using an rdf:List or rdf:Seq to order the association between
the index and its contents we retain the notion of ordering. Where
the index is a permanent collection, with all contents known at
the time of publishing, then an rdf:List is the best structure.
Otherwise use an rdf:Seq. These RDF data structures can easily be
generated and maintained using an asynchronous indexing system,
avoiding the need to rebuild all the indexes whenever the
underlying data changes. However for a large number of different
indexes or variations the time spent building these indexes can be
expensive.

Related
#######

- :ref:`Hierarchical URIs <hierarchical-uris>`
- :ref:`Composite Descriptions <composite-descriptions>`
