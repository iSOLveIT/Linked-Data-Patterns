.. _literal-keys:

Literal Keys
============

*How do we publish non-global identifiers in RDF?*

Context
#######

The :ref:`Natural Keys <natural-keys>` pattern encourages the
creation of URIs from existing non-global identifiers. While this
provides a way to begin identifying a resource so that we can
describe it in RDF, it does not address the issue of how to
publish these existing identifiers. Nor does it address situations
where natural keys change over time, e.g. the move from ISBN-10 to
ISBN-13 in the publishing world.

Solution
########

Create a custom property, as a sub-class of the dc:identifier
property for relating the existing literal key value with the
resource.

Example(s)
##########

The nasa dataset in data-incubator uses :ref:`Patterned URIs <patterned-uris>` based on the NSSDC international
designator, but includes these as literal values associated with
each spacecraft using a custom property.

Discussion
##########

While hackable URIs are a useful short-cut they don't address all
common circumstances. For example different departments within an
organization may have different non-global identifiers for a
resource; or the process and format for those identifiers may
change over time. The ability to algorithmically derive a URI is
useful but limiting in a global sense as knowledge of the
algorithm has to be published separately to the data.

By publishing the original "raw" identifier as a literal property
of the resource we allow systems to look-up the URI for the
associated resource using a simple SPARQL query. If multiple
identifiers have been created for a resource, or additional
identifiers assigned over time, then these can be added as
additional repeated properties.

For systems that may need to bridge between the Linked Data and
non-Linked Data views of the world, e.g. integrating with legacy
applications and databases that do not store the URI, then the
ability to find the identifier for the resource provides a useful
integration step.

Related
#######

- :ref:`Patterned URIs <patterned-uris>`
- :ref:`Natural Keys <natural-keys>`
