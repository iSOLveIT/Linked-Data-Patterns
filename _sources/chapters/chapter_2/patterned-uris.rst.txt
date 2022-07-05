.. _patterned-uris:

Patterned URIs
==============

*How can we create more predictable, human-readable URIs?*

Context
#######

Clean, clear URIs can be easier to remember and easier for
developers to work with. This is especially true if the URIs can
be algorithmically constructed or follow a common pattern. This
allows URIs to be constructed or hacked in order to create new
entry points into the dataset, e.g. determining the URI for a
collection of similar resources based on knowledge of a single
example URI.

Solution
########

Create URIs that follow a simple naming pattern. For applications
generating Linked Data one technique for building patterned URIs
is to use the pluralized class name as part of the URI pattern.

For example if an application will be publishing data about book
resources, which are modelled as the rdf:type ex:Book. One might
construct URIs of the form:

.. code-block::

   /books/12345

Where /books is the base part of the URI indicating "the
collection of books", and the 12345 is an identifier for an
individual book.

If multiple classes share a common base class, then it is also
possible to use the name of the common base class, rather than
generating separate URIs for each derived type

Example(s)
##########

The BBC website uses /programmes to group together URIs that
relate to series, brands and episodes, all of which are subclasses
of the rdf:type po:Programme

Discussion
##########

There are clear benefits from having human-readable, hackable
URIs. This solution achieves that by ensuring the same naming
scheme that applies to the underlying data also applies to the
URIs. This provides a clear relation between the URI and the type
of thing that it describes.

Related
#######

- :ref:`Hierarchical URIs <hierarchical-uris>`
- :ref:`Natural Keys <natural-keys>`
