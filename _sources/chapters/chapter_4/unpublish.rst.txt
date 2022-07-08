.. _unpublish:

Unpublish
=========

*How do we temporarily or permanently remove some Linked Data from the web?*

Context
#######

It is sometimes necessary to remove a Linked Data set from the
web, either in whole or in part. A dataset might be published by
an organisation who can no longer commit to its long term
availability. Or a dataset might be transferred to a new
authority. This applies to scenarios where a third-party has done
a proof-of-concept conversion of a dataset that is later replaced
by an official version.

In practical terms a dataset might also be temporarily unavailable
for any number of technical reasons.

How can the temporary or permanent removal of some data be
communicated? And, in cases where it has been replaced or
superseded, how can the new authoritative copy be referenced.

Solution
########

Use an appropriate HTTP status code to indicate the temporary or
permanent removal of a resource, or its migration to a new
location.

Where a resource has moved to a new location, publish :ref:`Equivalence Links <equivalence-links>`
between the old and the new resources.

Example(s)
##########

A dataset has been published by a developer illustrating the
benefits of a Linked Data approach to data publishing. The
developer has used URIs based on a domain of
``http://demo.example.net``. At a later date the original owner of
the data decides to embrace Linked Data publishing. The new
dataset will be published at ``http://authority.example.org``.

The developer therefore reconfigures his web server to redirect
all URIs for ``http://demo.example.net`` to return a ``301``
redirect to the new domain. Consuming applications are then able
to determine that the data has been permanently moved to a new
location.

The developer also creates a data dump that contains a series of
RDF statements that indicate that all of the resources originally
available from ``http://demo.example.net`` are ``owl:sameAs`` the
new official URIs.

Discussion
##########

Movement or removal of web resources is not specific to Linked
Data, and so HTTP offers several status codes that are applicable
to the circumstances described in this pattern. Using the correct
HTTP status code is important to ensure that clients can
differentiate between the different scenarios. An HTTP status code
of ``503`` indicates that a resource is temporarily unavailable;
``410`` that a resource has been deleted; and ``301`` that a
resource has been moved to a new location. Returning ``404`` for a
resource that is only temporarily unavailable, or has been moved
or deleted is bad practice.

Where data has been replaced, e.g. new URIs have been minted
either at the same authority or a new one, then publishing RDF
assertions that relate the two URIs together is also useful. An
``owl:sameAs`` statement will communicate that two URIs are
equivalent and will ensure that any historical annotations
associated with the URI can be united with any newly published
data.

Lastly, in case of complete removal of a dataset, it is important
to consider archiving scenarios. If licensing permits, then data
publishers should provide a data dump of a complete dataset. Doing
so will mean that consumers, or intermediary services, can host
local caches of the data to support continued URI resolution (e.g.
via a URI Resolver). This mitigates impacts on downstream
consumers.

Related
#######

- :ref:`Equivalence Links <equivalence-links>`
- :ref:`URI Resolver <uri-resolver>`
