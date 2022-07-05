.. _typed-literal:

Typed Literal
=============

               :name: typed-literal
               :class: title

   *How can a datatype be associated with an RDF literal?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Data items are generally of a specific type, e.g. a date, floating
      point value, or decimal. This type information is important for
      consuming applications as it provides flexibility when querying,
      formatting, displaying and converting data.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Always associate a data type with an RDF literal that contains a
      structured value.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      TODO

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

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
      is therefore common practice to define a `Custom
      Datatype <custom-datatype.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Custom Datatype <custom-datatype.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <topi          | `Up <modelli         |  `Next <publishi     |
   | c-relation.html>`__  | ng-patterns.html>`__ | ng-patterns.html>`__ |
   +----------------------+----------------------+----------------------+
   | Topic Relation       | `Ho                  |  C                   |
   |                      | me <index-2.html>`__ | hapter 4. Publishing |
   |                      |                      | Patterns             |
   +----------------------+----------------------+----------------------+
