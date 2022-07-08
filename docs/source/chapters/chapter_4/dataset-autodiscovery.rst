.. _dataset-autodiscovery:

Dataset Autodiscovery
=====================

*How can an application discover the datasets (and any associated APIs) published by a website?*

Context
#######

A Linked Data application might apply the :ref:`Follow Your Nose <follow-your-nose>`
pattern to discover additional
data about resources in an RDF graph. But the application may need
to discover additional metadata about the dataset to which the
resource belongs, such as its license. The application may also
need access to additional facilities, such as a SPARQL endpoint,
in order to extract any additional data it requires.

Solution
########

Use the Vocabulary of Interlinked Datasets (VoiD) vocabulary to
publish a description of a dataset. Make this description
available from the standard location at the domain of the website,
i.e. ``/.well-known/void``.

Example(s)
##########

An application discovers the URI
``http://data.example.org/thing/1`` in a dataset. De-referencing
that URI will yield a description of that resource. In order to
discover a SPARQL endpoint for that dataset, the application
performs a GET request on
``http://data.example.org/.well-known/void``. This URL returns a
description of the dataset published at that domain.

Discussion
##########

RFC 5785 defines a means for declaring well known URIs for a
website. A registry of well known URIs is maintained by the IETF,
and a registration has been made for ``/.well-known/void``. As the
VoiD specification indicates, this URI should return a description
of all datasets available from the specified domain.

Providing such as description allows a consuming application to
bootstrap its knowledge of available datasets, their licensing,
and the means of interacting with them. This can greatly simplify
working with unknown data sources. For example an application
could discover a SPARQL endpoint or data dump that would allow it
to more efficiently harvest some required data.

Related
#######

- :ref:`Autodiscovery <autodiscovery>`

Further Reading
###############

- `VoiD Dataset Auto-discovery <#>`__
- `RFC5785 - Defining Well-Known URIs <https://datatracker.ietf.org/doc/html/rfc5785>`__
