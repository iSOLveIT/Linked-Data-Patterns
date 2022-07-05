.. _bounded-description:

Bounded Description
===================

               :name: bounded-description
               :class: title

   *How can we generate a useful default description of a resource
   without having to enumerate all the properties or relations that are
   of interest?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Application using semi-structured data sources should be tolerant
      of discovering unexpected data or missing properties of resources.
      For applications to be able to achieve this, there needs to be an
      approach to generating useful default descriptions of resources
      that don't require enumerating every property of interest. This
      behaviour is particularly useful for Linked Data browsers or
      similar applications that can have little or no expectation as to
      with which datasets they may be interacting.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Extract a sub-graph, or "bounded description", from a dataset that
      contains all of relevant properties and relationships associated
      with a resource.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Bounded Descriptions take advantage of the graph structure of RDF
      in order to define simple graph operations that can be applied to
      any node in the graph. The operations yield a useful sub-set of
      the properties associated with the resource based on how they
      relate to the resource, rather than the specific RDF predicates
      that have been used.

      There are a number of different types of bounded description that
      are in common use:

      .. container:: itemizedlist

         -  *Datatype Property Description* -- retrieve all properties
            of a resource whose values are literals
         -  *Object Property Description* -- retrieve all properties of
            a resource whose values are resources, typically eliminating
            blank nodes
         -  *Concise Bounded Description* -- effectively the above two
            descriptions, but recursively include all properties of any
            blank nodes present in object properties
         -  *Symmetric Concise Bounded Description* -- as above but
            include statements where the resource being described is the
            object, rather than the subject

      Many different variations of these basic descriptions are
      possible, especially when additional filtering is done to include,
      for example, properties that are useful for labelling (in a user
      interface).

      In practice many common web application use cases can easily be
      fulfilled with one or more bounded description queries. The
      ability to use general purpose queries to build a user interface
      or otherwise drive application behaviour increases cacheability of
      the results: an application may end up using a small number of
      relatively general purpose queries that apply to a number of use
      cases.

      Bounded descriptions can be implemented using SPARQL ``CONSTRUCT``
      queries. SPARQL ``DESCRIBE`` queries are implemented using a
      Bounded Description that is built-in to the specific SPARQL
      processor being used. The most common approach is to use a Concise
      Bounded Description.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Bounded Descriptions in
            RDF <http://n2.talis.com/wiki/Bounded_Descriptions_in_RDF>`__
         -  `Concise Bounded
            Description <http://www.w3.org/Submission/CBD/>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <              | `Up <applicati       |  `Next <composite-d  |
   | blackboard.html>`__  | on-patterns.html>`__ | escriptions.html>`__ |
   +----------------------+----------------------+----------------------+
   | Blackboard           | `Ho                  |  Composite           |
   |                      | me <index-2.html>`__ | Descriptions         |
   +----------------------+----------------------+----------------------+
