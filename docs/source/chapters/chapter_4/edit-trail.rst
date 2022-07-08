.. _edit-trail:

Edit Trail
==========

*How can people be encouraged to improve or fix up open data?*

Context
#######


Community maintained or managed information sources often underpin
a particular set of data. However by publishing the data in a
machine-readable form the data may become dissociated from the
community tools or forum that is used to create and maintain the
data. Without a clear association from the data to the tools,
users may be discouraged from using due to a perception of poor
quality, when it is often within their means to fix up or improve
the data.

Solution
########

Use the ex:editform property to associate a resource with a form,
or other entry point into an application that can be used to
correct the raw data.

Example(s)
##########

Associating a dbpedia resource page with the wikipedia page from
which its data is derived.

Discussion
##########

The "Edit This Page" concept is well embedded into a number of
community maintained websites, and particularly those based on a
wiki platform. A convention has grown up on those sites that
involves providing a machine-readable link in the HTML page that
allows a user agent to provide the user with a way to
auto-discover links to the associated editing form.

The ex:editform property applies this concept to Linked Data
resources. In this case the association is from the resource to
editing form, allowing a more direct link from to be made from an
information resource to a data management tool that can be used to
edit its properties.

By associating the property directly with the resource, as opposed
to the related page of which it is a primary topic, we aim to
ensure that even the link remains even if only a fragment of the
dataset is re-published.
