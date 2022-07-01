.. container:: navheader

   ===================================== =============================== =
   URI Resolver                                                          
   ===================================== =============================== =
   `Prev <transformation-query.html>`__  Chapter 6. Application Patterns  
   ===================================== =============================== =

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: URI Resolver
               :name: uri-resolver
               :class: title

   *How can we customize the application behaviour associated with
   resolving (de-referencing) a URI into RDF statements?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Linked Data applications typically acquire additional relevant
      data by adopting `Follow Your Nose <follow-your-nose.html>`__
      behaviour: any URI in a graph may be assumed to be de-referencable
      to obtain additional data.

      However in practice simple de-referencing, i.e. performing a GET
      request on a URI, is not always desirable. For example:

      .. container:: itemizedlist

         -  An mobile application may need to work in an off-line mode
            where remote data is not available
         -  Continuous testing scenarios may need to rely on predictable
            data for driving test assertions and, in addition, may need
            to be executable in a self-contained environment without use
            of network services
         -  Security constraints may require network requests to be
            routed via an intermediary service
         -  A local mirror may be available which can provide a better
            quality of service
         -  A remote service may be intermittently or completely
            unavailable, requiring a local mirror to be substituted on
            either a temporary or permanent basis

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Application code should address de-referencing requests to URI
      resolver. Broadly, a URI resolver is a function that maps from a
      URI to a stream from which RDF triples can be consumed. A URI
      resolver might consist of an application component or could be
      deployed as a network addressable service (i.e. a proxy server).

      Application code should defer to the URI resolver in order to
      source RDF statements and provide configuration options to specify
      which URI resolver (e.g. implementation or service location)
      should be used. Simple de-referencing behaviour may still be used
      as fallback behaviour if no URI resolver is available.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      A Linked Data browser loads and displays resources as directed by
      user behaviour, e.g. clicking on links in the user interface. A
      user selects to view a resource. When a user requests that the
      browser displays a resource, ``http://example.org/person/1``,
      instead of performing a GET request on the resource the browser
      invokes a pre-configured URI resolver to retrieve the description
      of the resource.

      The URI resolver has been set up to direct requests matching a
      pattern of ``http://example.org/*`` to a local triple store that
      contains a mirror of the remote data. However when the user visits
      ``http://other.example.org/document/123`` the URI resolver does
      not have any prior knowledge of the resource and falls back to a
      simple GET request on the resource URI.

      In neither case does the browser (or the user) need to know how
      the description was actually retrieved.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      Adding some extra indirection around the de-referencing of URIs
      into RDF statements provides some much needed flexibility when
      dealing with network issues such as intermittently available
      connections; unreliable remote services; and security constraints.
      Applications that support the configuration of URI resolvers
      provide options for customising and optimising application
      behaviour based on local requirements.

      URI resolvers are not a new concept and have been used in many
      different systems. SGML and XML processing pipelines typically
      support URI resolver components to allow resources to be cached
      locally or even bundled with an application. More broadly, HTTP
      proxy servers fulfill the role for general web requests.

      The indirection offered by URI resolvers make them an ideal
      location in which to provide additional behaviour. For example all
      of the following can be implemented using a URI resolver
      component:

      .. container:: itemizedlist

         -  Caching of RDF descriptions as they are retrieved, e.g. in
            an in-memory, file system, or document store
         -  Substitution of a local mirror of the data in preference for
            the remote version
         -  Substitution of a local mirror of the data in preference for
            the remote version, but only where the remote service is
            unavailable
         -  Serving of a fixed response, regardless of URI (e.g. to
            support testing scenarios)
         -  Retrieval of both the remote description of a resource plus
            local `annotations <annotation.html>`__ to mix public and
            private data
         -  `parallel retrieval <parallel-retrieval.html>`__ of the
            description of a resource that is spread across any
            combination of local or remote locations
         -  Provision of reasoning over retrieved data to augment data
            against a vocabulary
         -  Provision of support for resolution of non-HTTP URI schemes
         -  On-demand conversion of non-RDF data into RDF statements

      With suitable configuration, URI resolvers can potentially be
      chained together to create a de-referencing pipeline that can
      deliver some complex application behaviours with a simple
      framework.

      There are some Linked Data applications that provide URI resolver
      services, this includes generic Linked Data browsers. At their
      simplest the browsers simply provide additional HTML presentation
      of retrieved data. But in some cases the retrieved data is both
      directly accessible (i.e. the service acts as a proxy) and may be
      supplemented with local caches, annotation, or inferencing, as
      outlined above. To support de-referencing typically use a `Rebased
      URI <rebased-uri.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `Follow Your Nose <follow-your-nose.html>`__

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Further Reading
                  :name: further-reading
                  :class: title

      .. container:: itemizedlist

         -  `Diverted URI pattern <#>`__
         -  `The Jena FileManager and LocationMapper <#>`__
         -  `Entity management in XML applications <#>`__

.. container:: navfooter

   --------------

   +---------------------------------------+------------------------------------+---+
   | `Prev <transformation-query.html>`__  | `Up <application-patterns.html>`__ |   |
   +---------------------------------------+------------------------------------+---+
   | Transformation Query                  | `Home <index-2.html>`__            |   |
   +---------------------------------------+------------------------------------+---+
