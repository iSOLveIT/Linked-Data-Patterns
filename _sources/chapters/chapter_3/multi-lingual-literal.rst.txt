.. _multi-lingual-literal:

Multi-Lingual Literal
=====================

               :name: multi-lingual-literal
               :class: title

   *How can internationalized text be expressed in RDF?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      It is increasingly common for data to contain internationalized
      text, e.g. translated titles for a document. This alternate
      language text needs to be associated with the relevant resource in
      a clearly identifiable way

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Multi-lingual versions of a literal property can be expressed as a
      simple `Repeated Property <repeated-property.html>`__ with the
      addition of a language code to distinguish between the alternate
      versions.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      ``_:greeting a ex:LoginGreeting;    skos:prefLabel "Hello!";    skos:prefLabel "Hola!"@es.``

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      RDF allows a literal value to be associated with a language code.
      This code indicates the language in which the value of the literal
      has been expressed. RDF uses the ISO standard language codes,
      including regional variants. This capability lowers the bar to
      internationalizing data that is published as RDF. All
      serializations support this functionality and the SPARQL query
      language provides several functions for matching and manipulating
      language codes.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Repeated Property <repeated-property.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <link          | `Up <modelli         |  `Next <na           |
   | -not-label.html>`__  | ng-patterns.html>`__ | ry-relation.html>`__ |
   +----------------------+----------------------+----------------------+
   | Link Not Label       | `Ho                  |  N-Ary Relation      |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
