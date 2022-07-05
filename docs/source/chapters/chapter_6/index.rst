:hide-toc:

.. _chap6:

Application Patterns
====================

.. raw:: html

   <h2>Abstract</h2>

Application architecture has always been a rich source of
design patterns. Much of the design pattern literature
covers useful architectural and code design patterns that
can lead to the creation of more maintainable and
revolvable software.

We are still at the early stages of exploring how best to
create Linked Data applications. Indeed there is still
much debate about what constitutes a Linked Data
application at all. Is it any application that uses RDF,
perhaps entirely based on a local triple store? Or must
it be an application that is capable of continually
discovering new information from across the web of data?

We still have much to learn about how to create
applications that are truly flexible enough to process
and display a wide variety of different data types. This
covers everything from software architecture, design and
user experience. Over time we might expect to see more
research and development of Linked Data browsers. Or,
perhaps web browsers will simply become more data aware
and develop ways to help users make more of the data that
is increasingly embedded in or linked from web pages.

Regardless of the type of applications we are
constructing, there are a number of ways that specific
features of RDF, SPARQL, or HTTP accessible Linked Data
can be exploited to create flexible software architecture
or simply useful behaviour. This chapter captures a
variety of design patterns that relate to a number of
different aspects of application development.

The existing patterns literature is at our disposal for
helping to create Linked Data applications, but which
features of semantic web technology can help us to better
solve problems or meet requirements?


.. rubric:: **Table Of Contents**

.. toctree::
   :maxdepth: 1
   :numbered:

   Assertion Query <assertion-query>
   Blackboard <blackboard>
   Bounded Description <bounded-description>
   Composite Descriptions <composite-descriptions>
   Follow Your Nose <follow-your-nose>
   Missing Isn't Broken <missing-isnt-broken>
   Named Query <named-query>
   Parallel Loading <parallel-loading>
   Parallel Retrieval <parallel-retrieval>
   Parameterised Query <parameterised-query>
   Resource Caching <resource-caching>
   Schema Annotation <schema-annotation>
   Smushing <smushing>
   Transformation Query <transformation-query>
   URI Resolver <uri-resolver>
