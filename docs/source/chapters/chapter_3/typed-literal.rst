.. _typed-literal:

Typed Literal
=============

*How can a datatype be associated with an RDF literal?*

Context
#######

Data items are generally of a specific type, e.g. a date, floating
point value, or decimal. This type information is important for
consuming applications as it provides flexibility when querying,
formatting, displaying and converting data.

Solution
########

Always associate a data type with an RDF literal that contains a
structured value.

Example(s)
##########

TODO

Discussion
##########

The RDF allows a literal value to be associated with a data type.
RDF itself does not have a built-in type system, it defers to the
XML Schema datatypes to define a useful common set of data types
and their legal lexical values. By using this facility data
publishers can ensure that consumers can more easily manipulate
and process the published data. Use of standard data types
encourages interoperability between systems. It also supports
internationalization of data as client applications can more
easily process the value to present it for display in a specific
locale

In some cases XML Schema does not define an existing data type. It
is therefore common practice to define a
:ref:`Custom Datatype <custom-datatype>`

Related
#######

- :ref:`Custom Datatype <custom-datatype>`
