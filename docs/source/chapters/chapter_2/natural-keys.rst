.. _natural-keys:

Natural Keys
============

*How can we create unique URIs from data that already has unique identifiers?*

Context
#######

It is often the case that a group of resources already have a
unique identifier. This might be a local system identifier derived
from, e.g. a database key; or a global non-URI identifier, e.g. an
ISBN.

Solution
########

Mint URIs that are algorithmically derived from the existing
non-URI identifier. This can be as simple as concatenating the
existing identifier or key with a suitable base URI. The existing
identifier may need to be URL encoded before creating the URI. It
is common to combine this technique with Patterned URIs.

Example(s)
##########

The BBC programmes website uses URIs that are derived from its
existing "programme id" or pid.

Discussion
##########

Where resources are already associated with existing keys, it is
likely that the creation and management of those identifiers will
already be supported by a specific technology or process. There is
a need to be able to create global URI based identifiers for these
resources without creating unnecessary additional overheads in
creating entirely new identifiers and/or mapping between URIs and
existing keys.

By deriving the URI from the natural key for the identifier we
avoid the need to create a new process for assigning identifiers
and largely eliminate the need to have a mapping between the two
identification systems.

Related
#######

- :ref:`Patterned URIs <patterned-uris>`
