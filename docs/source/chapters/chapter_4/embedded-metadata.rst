.. _embedded-metadata:

Embedded Metadata
=================

*How do we add structured data to an existing document or file?*

Context
#######

There are two related aspects to this pattern

Firstly, many web sites that are using frameworks or content
management systems that are either difficult to customize or are
operated by organizations that have little or no in-house
technical staff. How can these sites be updated, with a minimum of
effort, to support publishing of structured data?

Secondly, documents or files may be shared and copied across the
web. This can result in a broken connection between the document
and it's metadata which might only be available from the source
website. How can the metadata be made available to anyone
discovering a copy or mirror of the document?

Solution
########

Embed the structured data directly in the document itself rather
than, or in addition to, publishing that data separately.

The most common scenario here is instrumenting an existing webpage
to add some "semantic markup" that will enable a client to extract
data directly from the HTML source. This typically involves
changing just the templates used ot generate the web pages. By
changing a small number of resources, it becomes possible to
quickly and easily publish data about a large number of resources.

A less common scenario involves embedding data within a different
document format. Typically this relies on using an existing
extension mechanism that has been defined for that format. A tool
may then inspect the file directly to discover the metadata or a
link to its location.

Example(s)
##########

At the time of writing there are a number of competing proposals
for embedding metadata in XHTML/HTML documents, including RDFa,
microdata and microformats. RDFa can also be used to embedded
metadata in other XML formats

Options vary for embedding metadata in other formats, but `Adobe XMP <https://www.adobe.com/products/xmp.html>`__
provides an option that can be used in a variety of formats.

Discussion
##########

Embedding metadata into existing resources, rather than requiring
changes to how content and data is published to the web is often
much easier to achieve. At the time of writing there are a number
of competing approaches for embedding metadata in XHTML/HTML.
These typically offer the same basic features but vary in how much
they require specific markup extensions in the original document.

While it can be very easy to quickly instrument a website with
embedded metadata, the requirement to introduce all data into the
same template means that it can become awkward to manage the
competing concerns: e.g. clean, well-structured markup for styling
and presentation, versus rich, detailed, semantic markup for
machines. For more complex use cases its may be better to simply
publish the metadata separately, or embedded only a subset of the
data with links to additional resources.

Related
#######

- :ref:`Primary Topic Autodiscovery <primary-topic-autodiscovery>`
- :ref:`See Also <see-also>`

