.. _link-base:

Link Base
=========

*How can outbound links from a dataset be managed separately from the core data?*

Context
#######

When publishing Linked Data it is common to undertake the
inter-linking of newly published data with existing sources as a
final step in the publishing process. Linking strategies range
from manual methods through to automated link discovery. The
volume of out-bound links may vary over time, e.g. as new links
are discovered to existing sources, or new links are made to other
new datasets. Over time, due to "semantic drift", it may be
necessary to remove links to some external resource.

The linking data within a dataset may therefore have different
quality assurances associated with it, as well as a different rate
of change to the core dataset.

Solution
########

Partition the data into two datasets: the core data and the
linking data. Publish linking data as a separate set of documents.
Use :ref:`See Also <see-also>` links to tie the data together.

Example(s)
##########

.. code-block::

   #Core Data
   <http://www.example.org/places/Paris> a ex:Place;
     skos:prefLabel "Paris";
     rdfs:seeAlso <http://www.example.org/links/Paris>.

   #Linking Data
   <http://www.example.org/links/Paris>
     owl:sameAs <http://dbpedia.org/resource/Paris>.

           

Discussion
##########

Partitioning links from core data has a number of advantages in
terms of both how it is published and how it is consumed.

For the publisher, partitioning links allows the linking data to
be revised and improved separately to the publication of the core
reference data. This is particularly useful where the linking data
is generated automatically using heuristics. The quality of the
generated links may need to be refined and iterated over time. As
new datasets are published, the linking data can get updated to
include additional relationships. Managing the typically smaller
subset of links distinctly from the core data, e.g. in a separate
triple store, allows more flexibility in managing the data.

For a consumer, the partitioning of links into a separate dataset
allows more choice in what data is to be consumed. Because the
quality characteristics of linking data may vary considerably from
that of the core data, the ability to selectively consume only the
core data is an important one. If the linking data is presented as
part of the core dataset, then this requires the consumer to
filter the data to remove the unneeded triples.

Related
#######

- :ref:`Equivalence Links <equivalence-links>`
