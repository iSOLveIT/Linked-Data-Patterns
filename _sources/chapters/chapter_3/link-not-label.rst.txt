.. _link-not-label:

Link Not Label
==============
*How do we model a dataset to maximise benefits of a graph based model?*

Context
#######

Most datasets are centred around a few core resources types that
are central to that dataset. For example a social network dataset
would be centred on people, groups and organizations, whereas a
publishing dataset would be centred on authors, publications and
publishers.

However every dataset typically has some additional resource types
that are less "central". E.g areas or topics of interest, spoken
or print languages, publication formats, etc. Often these
resources are over-looked during modelling and are often only
represented as simple literal values. This can make it less
efficient to query a dataset, e.g. to group resources based on
shared characteristics (e.g. everyone with same interests, all
hardback books). It can also limit the
:ref:`annotate <annotation>` these aspects of a dataset, e.g. in
order to add :ref:`equivalence links <equivalence-links>`.

Many common modelling approaches or industry standard models often
re-inforce a less expressive modelling approach. For example many
publishing and library standards, while encouraging use of
controlled terms and authority files, focus largely on
publications as the only important entity in a data model, leaving
subject categories and authors as little more than labels
associated with a work.

Solution
########

Ensure that all resources in a dataset are modelled as resources
rather than simple literal values. Relate resources together to
create a richer graph model. Use the literal values as the labels
of the new resources.

A good approach is to look for any controlled vocabularies,
keywords, tags, or annotations and dimensions in a dataset and
model them as resources. Even structured literal values like dates
might be more usefully modelled as resources.

Example(s)
##########

Example of potential resources that might get overlooked:

- Languages
- Country codes
- Tags, categories, or subject headings
- Gender
- Genres
- Formats

A simple example:

.. code-block::

   #Rather than this:
   <http://www.example.org/book/1>
     dc:format "Hardback";
     dc:lang "en"
     dc:subject "RDF", "SPARQL".

   #Use a richer model:
   <http://www.example.org/book/1>
     dcterms:format <http://example.org/formats/hardback>;
     dcterms:lang <http://www.lingvoj.org/lingvo/en>;
     dcterms:subject <http://example.org/category/rdf>;
     dcterms:subject <http://example.org/category/sparql>.

   <http://example.org/formats/hardback>
     rdfs:label "Hardback".

   <http://example.org/category/rdf>
     rdfs:label "RDF".

   <http://example.org/category/sparql>
     rdfs:label "SPARQL".

   #Categories could later be related to other sources
   <http://example.org/category/rdf>
     owl:sameAs <http://id.loc.gov/authorities/sh2003010124#concept>;
     owl:sameAs <http://rdf.freebase.com/ns/authority.us.gov.loc.sh.sh2003010124>.

Discussion
##########


Creating a rich graph of relationships within a dataset will yield
more flexibility and value from adopting Linked Data.

For example, as RDF triple stores are optimized for storing and
querying relationships and graph patterns, creating resources for
common dimensions in a dataset will allow for faster and more
flexible querying. By representing these dimensions are resources
in their own right, then they can be more easily annotated, e.g.
to qualify them with additional data, or relate them to external
sources.

In many cases existing resources in publicly available datasets
can be used instead of creating new URIs. By using resources, and
reusing identifiers, it becomes easier to correlate and traverse
different datasets. For example it becomes possible to draw in
external data to enrich an existing application, e.g. an author
profile or related works in another collection.

Related
#######

- :ref:`Annotation <annotation>`
- :ref:`Equivalence Links <equivalence-links>`

Further Reading
###############


- `Why Resources in Linked Data are Good <#>`__
