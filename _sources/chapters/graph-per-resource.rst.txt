.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Graph Per Resource   |                      |                      |
   +======================+======================+======================+
   | `Prev <graph-        | Chapter 5. Data      |  `Next <graph        |
   | per-aspect.html>`__  | Management Patterns  | -per-source.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Graph Per Resource
               :name: graph-per-resource
               :class: title

   *How can we organise a triple store in order to make it easy to
   manage the statements about an individual resource?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Web applications typically offer forms for editing the description
      of an individual resource, e.g. the title, description and tags
      that apply to a specific photo. RESTful APIs typically support
      replacing the description of a resource using a PUT operation. In
      both cases it would be useful to be able to serialize all of the
      statements relating to a given resource, including any edits, and
      directly replace the relevant triples in a triple store backing
      the application or API.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Store the description of each resource in a separate `Named
      Graph <named-graphs.html>`__ using a graph URI derived from the
      resource URI as the graph URI. When the resource is updated,
      simply replace the contents of that graph with the latest state of
      the resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      A user is editing the description of
      ``http://example.org/picture/1``. The application delivers a web
      form to the authorised user which presents the current description
      of the resource in an interactive editing form. When the client
      submits the changes back to the server, it does so by serializing
      the state of the form as RDF which is then processed by the
      server.

      On receiving the update from the client, the server-side code
      computes the graph URI for the resource being edited. For this
      application graph URIs are derived from resource URIs by a simple
      rewrite. For example the data for ``http://example.org/picture/1``
      is stored in ``http://data.example.org/graphs/picture/1``.

      To apply the update the server-side code simply determines the
      appropriate graph URI and then stores the data in a `SPARQL 1.1.
      Graph Store Protocol <#>`__ enabled store using a simple PUT
      operation.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Partioning the triple store by resource rather than by
      `source <graph-per-source.html>`__ provides an easy way to quickly
      access the description of an individual resource without having to
      use a SPARQL query. This is particularly true if the graph URI for
      a resource can be derived using a simple algorithm, e.g. rewriting
      to a different base URI, pre-pending a known prefix, etc.

      The `SPARQL 1.1. Graph Store Protocol <#>`__ provides a way for
      code to find and update the description of a resource without
      needing further knowledge of the data stored about any specific
      resource. This allows server-side code to remain relatively
      generic: it doesn't need to know details about what kinds of data
      is captured about individual resources, it just needs to know
      where to persist the data its given.

      When applying this pattern it is common to store a `bounded
      description <bounded-description.html>`__ of the resource in each
      graph ensuring that each graph has a clear scope.

      While this pattern makes it easy to manage a bounded description
      for a resource, including its relationships to other resource, it
      doesn't help with managing references to the resource elsewhere in
      the store. E.g. if a resource is deleted (by removing its graph),
      there may still be statements relating to that resource elsewhere
      in the graph. Additional SPARQL Update operations, for example,
      would be needed to remove these statements. Depending on the
      complexity of the graph structure and the needs of the application
      these overheads might make this pattern unsuitable.

      In circumstances where additional context is required, e.g.
      in-bound relations, for an application view, a fall-back to SPARQL
      queries over a `Union Graph <union-graph.html>`__ of the store can
      provide additional flexibility. However for the simplest cases of
      serving Linked Data pages, this pattern makes for very simple and
      light-weight application code.

      For very simple use cases the graph URI of the graph holding the
      description of the resource could in fact be the resource URI.
      However in practice this can limit system evolution. As explained
      in the `Graph Annotation <graph-annotation.html>`__ pattern, the
      ability to store additional graph metadata can be useful. And in
      that case a separate graph URI is essential to avoid potential
      confusion around the scope of individual statements.

      In some applications several different processes might contribute
      to the creation of a description of a resource. Using a single
      graph per resource might therefore involve contention around
      several processes. The `Graph Per
      Aspect <graph-per-aspect.html>`__ pattern allows this contention
      to be removed by using multiple graphs per resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Named Graph <named-graphs.html>`__
         -  `Graph Annotation <graph-annotation.html>`__
         -  `Graph Per Source <graph-per-source.html>`__
         -  `Graph Per Aspect <graph-per-aspect.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Named Graph (Wikipedia) <#>`__
         -  `Managing RDF using Named Graphs <#>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <graph-        | `Up <data-manageme   |  `Next <graph        |
   | per-aspect.html>`__  | nt-patterns.html>`__ | -per-source.html>`__ |
   +----------------------+----------------------+----------------------+
   | Graph Per Aspect     | `Ho                  |  Graph Per Source    |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
