.. _hierarchical-uris:

Hierarchical URIs
=================

*How should URIs be assigned to a group of resources that form a natural hierarchy?*

Context
#######
It is often the case that a collection of resources may form a
natural hierarchy. E.g. the chapters within a book, or the
departments within an organization. Reflecting this strict
hierarchy within the URI structure makes those URIs more hackable
allowing users/developers to "navigate" up the hierarchy by
pruning the URI.

Solution
########

Where a natural hierarchy exists between a set of resources use
:ref:`Patterned URIs <patterned-uris>` that conform to the
following pattern:

.. code-block::

   :collection/:item/:sub-collection/:item

E.g. in a system which is publishing data about individual books
and their chapters, we might use the following identifier for
chapter 1 of a specific book:

.. code-block::

   /books/12345/chapters/1

Example(s)
##########

The discogs dataset in data-incubator uses hierarchical uris of the
form:

.. code-block::

   http://discogs.dataincubator.org/release/22530/track/1-01

Discussion
##########

This technique is best suited to scenarios where the items in the
sub-collections (chapters) are always associated with a single
parent item. Other relationships might exist, e.g. the chapter may
be included in another but the chapter is always associated with
at least one book: they do not exist in isolation. In
circumstances where this doesn't hold true, then it is best to
just use simple Patterned URIs.

The same applies to circumstances where the hierarchy may change
over time.

Related
#######

* :ref:`Patterned URIs <patterned-uris>`
