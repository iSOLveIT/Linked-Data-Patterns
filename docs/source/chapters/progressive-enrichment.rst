.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Progressive          |                      |                      |
   | Enrichment           |                      |                      |
   +======================+======================+======================+
   | `Pre                 | C                    |  `Nex                |
   | v <primary-topic-aut | hapter 4. Publishing | t <see-also.html>`__ |
   | odiscovery.html>`__  | Patterns             |                      |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Progressive Enrichment
               :name: progressive-enrichment
               :class: title

   *How can the quality of data or a data model be improved over time?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      At the time when a dataset is first published the initial data may
      be incomplete, e.g. because data from additional systems has not
      yet been published, or the initial dataset is a place-holder that
      is to be later annotated with additional data. Data models are
      also likely to evolve over time, e.g. to refine a model following
      usage experience or to converge on standard terms.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      As the need arises, update a dataset to include additional
      `annotations <annotation.html>`__ for existing or new resources.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      A key benefit of the semi-structured nature of RDF is the ability
      to easily merge new statements into an existing dataset. The new
      statements may be about entirely new resources or include
      additional facts about existing resources. There is no need to
      fully define a schema, or even fully populate a data model, up
      front. Data can be published and then refined and improved over
      time.

      Progressive Enhancement is essentially a variant of the
      `Annotation <annotation.html>`__ pattern within a single dataset.
      Whereas the Annotation pattern describes an approach to
      distributed publishing of data about a set of resources,
      Progressive Enhancement confines this to a particular dataset
      allowing the depth of detail or quality of the modelling to
      improve over time.

      A common use of this pattern in Linked Data publishing is to
      update a dataset with additional `Equivalence
      Links <equivalence-links.html>`__.

      Progressive Enrichment is a key aspect of the
      `Blackboard <blackboard.html>`__ application pattern.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Annotation <annotation.html>`__
         -  `Equivalence Links <equivalence-links.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Pre                 | `Up <publishi        |  `Nex                |
   | v <primary-topic-aut | ng-patterns.html>`__ | t <see-also.html>`__ |
   | odiscovery.html>`__  |                      |                      |
   +----------------------+----------------------+----------------------+
   | Primary Topic        | `Ho                  |  See Also            |
   | Autodiscovery        | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
