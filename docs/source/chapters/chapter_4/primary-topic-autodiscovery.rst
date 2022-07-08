.. _primary-topic-autodiscovery:

Primary Topic Autodiscovery
===========================

*How can people identify the principal subject of a given web page?*

Context
#######

Often a web page is concerned with a particular physical object or
other resource. To assist discovery and aggregation of pages about
particular topics the publisher wants to indicate the URI of this
resource.

Solution
########

When publishing a web page include a link element in the head of
the web page pointing to the URI of the page's primary topic. Use
a rel attribute value of "primarytopic".

``<link rel="primarytopic" href="http://dbpedia.org/resource/London"/>``

Example(s)
##########

Associating a wikipedia page with the equivalent dbpedia resource.

Discussion
##########

Many pages on the Web are explicitly about a single subject.
Examples include Amazon product pages, Wikipedia entries, blogs
and company home pages. Without an explicit link, content
aggregators must resort to heuristic inference of the topic which
is prone to classification error. Often the original publisher
knows the specific topic and would like to provide this as a hint
to aggregators and other content consumers.

Even when the page is about several topics there can be a single
primary topic that can be linked to directly.

Related
#######

- :ref:`Autodiscovery <autodiscovery>`
