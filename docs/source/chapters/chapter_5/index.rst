:hide-toc:

.. _chap5:

Data Management Patterns
========================

.. raw:: html

   <h2>Abstract</h2>

While the statements in an RDF dataset describe a direct
graph of connections between resources, the collection of
triples itself has no structure: it is just a set of RDF
statements. This lack of structure is not a problem for
many simple RDF applications; the application code and
behaviour is focused on exploring the connections in the
graph. But for more complex systems that involve
integrating data from many different sources it becomes
useful to be able to partition a graph into a collection
of smaller sub-graphs.

One reason for partitioning of the graph, is to support
data extraction. Creating a useful view over one or more
resources in a graph, e.g. to drive a user interface.
There are a number of different partitioning mechanisms
that can be used and these are covered in the :ref:`Bounded-Description <bounded-description>` pattern
described in the next chapter.

A very important reason for wanting to partition a graph
is to make data management simpler. By partitioning a
graph according to its source or the kinds of statements
it contains we can make it easier to organise and update
a dataset. Managing smaller graphs gives more affordance
to the data, allowing entire collections of statements to
be manipulated more easily.

The means by which this affordance is created is by
extending the core triple model of RDF to include an
extra identifier. This allows us to identify collections
of RDF triples, known as :ref:`Named Graphs <named-graphs>`. The patterns captured in
this chapter describe different approaches for managing
RDF data using Named Graphs. The patterns cover different
approaches for deciding on the scope of individual
graphs, as well as how to annotate individual graphs, as
well as ultimately re-assembling graphs back into a
useful whole.

It should be apparent that Named Graphs is essentially a
document-oriented approach to managing RDF data. Each
document contains a collection of RDF statements. This
means that we can benefit from thinking about good
document design when determining the scope of each graph,
as well as more general document management practices in
deciding how to organise our data.

The beauty of the RDF model is that it is trivial to
manage a triple store as a collection of documents
(graphs) whilst still driving application logic from the
overall web of connections described by the statements
contained in those documents. An XML database might also
offer facilities for managing collections of XML
documents, but there is no standard way in which the
content of those documents can be viewed or manipulated.
In contrast the data merging model described by RDF
provides a principled way to merge data across documents
(Union Graph).

This flexibility provides some powerful data management
options for RDF applications.


.. rubric:: **Table Of Contents**

.. toctree::
   :maxdepth: 1
   :numbered:

   Graph Annotation <graph-annotation>
   Graph Per Aspect <graph-per-aspect>
   Graph Per Resource <graph-per-resource>
   Graph Per Source <graph-per-source>
   Named Graph <named-graphs>
   Union Graph <union-graph>
