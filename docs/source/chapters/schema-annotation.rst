.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Schema Annotation    |                      |                      |
   +======================+======================+======================+
   | `Prev <resour        | Ch                   |  `Nex                |
   | ce-caching.html>`__  | apter 6. Application | t <smushing.html>`__ |
   |                      | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Schema Annotation
               :name: schema-annotation
               :class: title

   *How can application-specific processing rules be externalized?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Data driven applications typically end up with built-in processing
      rules for handling particular types of data, e.g. validation
      constraints, preferences for specific properties or types, etc.
      These rules are often encapsulated in procedural code, making them
      difficult to change. Externalizing these rules as declarative
      configuration can make an application easier to customize. How can
      this be achieved with applications that consume Linked Data?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Externalize constraints using annotation properties that are used
      to drive processing rules or constraints by annotating classes and
      properties in a vocabulary

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      .. code:: programlisting

            
         ex:RequiredProperty a rdfs:Property;
            rdfs:comment "must be completed on data entry form".

         ex:IgnoredProperty a rdfs:Property;
            rdfs:comment "never shown when displaying data".

         <http://xmlns.com/foaf/0.1/name>
            a ex:RequiredProperty.

         <http://xmlns.com/foaf/0.1/dnaChecksum>
            a ex:IgnoredProperty.
            
           

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Simple annotations of classes and properties is a simple and easy
      way to externalize some common types of application configuration.
      RDF vocabularies are easily extended with additional properties,
      making them suitable for extension in this way. Using this
      approach applications can be very easily tailored to work with a
      range of different vocabularies.

      Annotations may encode a wide range of configuration options
      including: display preferences, validation constraints, identifier
      assignment rules for classes, and local labelling for classes and
      properties. Annotation may even be used to tailor inferencing over
      specific vocabularies to allow for more local customisation and
      control over how inferencing is applied; for example a local
      schema annotation might declare that two classes were equivalent,
      or that a specific property is an inverse-functional-property,
      triggering data to be merged.

      Schema annotations would typically form part of the overall
      application configuration and would be applied locally, rather
      than being published to the open web.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Annotation <annotation.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <resour        | `Up <applicati       |  `Nex                |
   | ce-caching.html>`__  | on-patterns.html>`__ | t <smushing.html>`__ |
   +----------------------+----------------------+----------------------+
   | Resource Caching     | `Ho                  |  Smushing            |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
