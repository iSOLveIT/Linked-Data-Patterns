.. _smushing:

Smushing
========

               :name: smushing
               :class: title

   *How do we merge data about resources that may not be consistently
   identified?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      It will often be the case that different data publishers have used
      different identifiers for the same resource. In some cases there
      may be direct `Equivalence Links <equivalence-links.html>`__
      between resources. In others their equivalence might be inferred
      based on other data, e.g. common properties.

      How can we merge statements made about these distinct resources
      into a single description?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Apply the technique of "smushing" to manipulate an RDF graph
      containing the descriptions of each of the resources. Broadly a
      smushing algorithm will consist of the following steps:

      .. container:: itemizedlist

         -  Decide on the URI for the resource that will hold the final
            description, i.e. the *target resource* -- this could be one
            randomly selected from available URIs, or one from a local
            dataset
         -  Identify all *equivalent resources* -- i.e. by finding
            `Equivalence Links <equivalence-links.html>`__ such as
            ``owl:sameAs`` statements, or by property values that
            indicate that two resources are similar (e.g. Inverse
            Functional Properties, see below).
         -  Iterate over the *equivalent resources* and for each RDF
            statement for which it is the *subject*, assert a new
            statement with the same predicate and object but using the
            *target resource* as the subject
         -  Iterate over the *equivalent resources* and for each RDF
            statement for which it is the *object*, assert a new
            statement with the same subject and predicate but using the
            *target resource* as the object

      The end result will be an modified RDF graph with all properties
      of the *equivalent resources* being "copied" to the *target
      resource*. In addition, any references to the *equivalent
      resources* will also be made to the target resource

      By applying this to all resources in a graph, the available data
      can be normalized into a consistent set of descriptions based on a
      known set of resources. An application may then generate a
      `Bounded Description <bounded-description.html>`__ of any resource
      and guarantee that it will include all available data

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      Assume we start with the following graph, which contains two
      equivalent resources, as defined by an ``owl:sameAs`` link.

      .. code:: programlisting


         <http://example.com/product/6>
           rdfs:label "Camera";
           owl:sameAs <http://example.org/cameras/10>.

         <http://example.org/cameras/10>
           ex:manufacturer <http://example.org/company/5>.

         <http://example.org/company/5>.
           ex:manufactured <http://example.org/cameras/10>.

      Assuming we want to collate all data around resources from
      ``example.com``, we can apply smushing to create the following
      graph:

      .. code:: programlisting


         <http://example.com/product/6>
           rdfs:label "Camera";
           owl:sameAs <http://example.org/cameras/10>;  
           ex:manufacturer <http://example.org/company/5>.
           
         <http://example.org/cameras/10>
           ex:manufacturer <http://example.org/company/5>.

         <http://example.org/company/5>.
           ex:manufactured <http://example.org/cameras/10>.
           ex:manufactured <http://example.com/product/6>.

      We can also tidy up the graph to remove statements about the
      equivalent resources, leaving:

      .. code:: programlisting


         <http://example.com/product/6>
           rdfs:label "Camera";
           owl:sameAs <http://example.org/cameras/10>;  
           ex:manufacturer <http://example.org/company/5>.
           
         <http://example.org/company/5>.
           ex:manufactured <http://example.com/product/6>.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Smushing is essentially a process of inference: by using available
      data we create new statements. Any OWL reasoner will carry out
      this kind of data merging automatically based on the available
      data and schema/ontology without the need for custom code.
      Applications that are using a triple store that applies
      inferencing by default will not need to use this approach. However
      for applications that don't need a full inferencing engine, or
      need only lightweight merging of data, then a custom smushing
      algorithm can achieve the same goal.

      There are several different variations on algorithm described
      above. For example, applications might vary in how they nominate
      the *target resource*. Typically though this will be based on a
      preferred URI. Algorithms can also be divided into those that
      preserve the original statements, e.g. so that the *equivalent
      resources* remain in the source RDF graph, or whether their
      statements are removed from the graph to leave only a normalized
      description. Applications could also use `Named
      Graphs <named-graphs.html>`__ to separately stored the "smushed"
      view of the data, preserving the original data in another graph or
      triple store.

      As noted above there are also several ways to identify equivalent
      resources. `Equivalence Links <equivalence-links.html>`__ are an
      obvious approach. Other cues can also be used including the use of
      `Inverse Functional Properties <#>`__. An inverse functional
      property is simply a property whose value uniquely identifies a
      resource, such as `Literal Keys <literal-keys.html>`__.

      An application is also free to apply it's own rules about what
      consistutes "equivalence". For example an application may decide
      to merge together resources with similar property values, even if
      those properties are not declared as Inverse Functional
      Properties. This allows for local customization of smushing rules,
      but runs the risk of generating false positives. One way to apply
      these custom rules is to use local `Schema
      Annotations <schema-annotation.html>`__ to declare specific
      properties as being equivalent. This has the benefit of working
      with both custom code and OWL reasoners.

      Smushing is often used to normalize an RDF graph resulting from a
      `Follow Your Nose <follow-your-nose.html>`__ approach to data
      discovery

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Equivalence Links <equivalence-links.html>`__
         -  `Follow Your Nose <follow-your-nose.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Smushing <#>`__
         -  `RDF Smushing <#>`__
         -  `Smushing Algorithms <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <schema-       | `Up <applicati       |  `Next <transform    |
   | annotation.html>`__  | on-patterns.html>`__ | ation-query.html>`__ |
   +----------------------+----------------------+----------------------+
   | Schema Annotation    | `Ho                  |  Transformation      |
   |                      | me <index-2.html>`__ | Query                |
   +----------------------+----------------------+----------------------+
