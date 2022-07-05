.. _materialize-inferences:

Materialize Inferences
======================

               :name: materialize-inferences
               :class: title

   *How can data be published for use by clients with limited reasoning
   capabilities?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Linked Data can be consumed by a wide variety of different client
      applications and libraries. Not all of these will have ready
      access to an RDFS or OWL reasoner, e.g. Javascript libraries
      running within a browser or mobile devices with limited processing
      power. How can a publisher provide access to data which can be
      inferred from the triples they are publishing?

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Publish both the original and some inferred (materialized) triples
      within the Linked Data.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Reasoners are not as widely deployed as client libraries for
      accessing RDF. Even as deployment spreads there will typically be
      processing or performance constraints that may limit the ability
      for a consuming application to perform reasoning over some
      retrieved data. By also publishing materialized triples a
      publisher can better support clients in consuming their data.

      Most commonly materialization of the inferred triples would happen
      through application of a reasoner to the publishers data. However
      a limited amount of materialized data can easily be included in
      Linked Data views through simple static publishing of the extra
      relations. E.g. by adding extra "redundant" statements in a
      template.

      There are a range of useful relationships that could be included
      when implementing this pattern:

      .. container:: itemizedlist

         -  Typing, based on range and domains of properties and/or
            derived classes
         -  Super properties, based on property extensions
         -  Transitive relationships, e.g. ``skos:broader`` and
            ``skos:narrower`` relations
         -  Inverse properties

      Materialization may also be targetted in some way, e.g. to address
      specific application needs, rather than publish the full set of
      inferred relations. The specific materializations chosen can be
      based on expectations of common uses for the data. For example the
      publisher of a SKOS vocabulary may publish transitive relations
      between SKOS concepts, but opt not to include additional
      properties (e.g. that every ``skos:prefLabel`` is also an
      ``rdfs:label``)

      A reasonable rule of thumb approach to materializations would be
      to always include additional type or property relations whenever
      that would help ground the data in more commonly used
      vocabularies. Inverse and transitive relationships provide extra
      navigation options for Linked Data clients so are also worth
      considering.

      The downside to publishing of materialized triples is that there
      is no way for the consuming system to differentiate between the
      original and the inferred data. This limits the ability for the
      client to access only the raw data, e.g. in order to apply some
      local inferencing rules. This is an important consideration as
      publishers and consumers may have very different requirements.
      Clearly materializing triples also places additional burdens on
      the publisher.

      An alternative approach is to publish the materialized data in
      some other way, e.g. in a separate document(s) referenced by a
      `See Also <see-also.html>`__ link.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Creating Linked Data - Part V: Finishing
            Touches <http://www.jenitennison.com/blog/node/139>`__ (see
            section on Derivable Data)

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev                | `Up <publishi        |  `Ne                 |
   | <link-base.html>`__  | ng-patterns.html>`__ | xt <primary-topic-au |
   |                      |                      | todiscovery.html>`__ |
   +----------------------+----------------------+----------------------+
   | Link Base            | `Ho                  |  Primary Topic       |
   |                      | me <index-2.html>`__ | Autodiscovery        |
   +----------------------+----------------------+----------------------+
