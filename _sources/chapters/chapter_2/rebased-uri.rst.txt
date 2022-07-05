.. _rebased-uri:

Rebased URI
===========

               :name: rebased-uri
               :class: title

   *How can we construct one URI based on another?*

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Context
                  :name: context
                  :class: title

      Sometimes when generating a `Patterned
      URI <patterned-uris.html>`__ the key that we have for as `URL
      Slug <url-slug.html>`__ is not a simple literal value, but instead
      another URI. For example this can occur when generating a new
      Named Graph URI for a resource, or when defining a service URL for
      a `URI Resolver <uri-resolver.html>`__.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Solution
                  :name: solution
                  :class: title

      Rewrite the original URI to use a new, predictable base URI using
      on of the options described below.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Example(s)
                  :name: examples
                  :class: title

      An application needs to generate a new Named Graph URI for a
      resource URI of ``http://example.org/document/1``. The application
      uses a regular expression to rewrite the original URI to a new
      base, e.g. ``http://graphs.example.org/document/1``.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Discussion
                  :name: discussion
                  :class: title

      URL rewriting is a common feature of all web servers and most web
      frameworks. Rewriting is normally carried out using regular
      expressions to match and replace portions of the original URI with
      some standard replacement text.

      URL rewriting is used in several Linked Data services in order to
      create new URLs. This is typically to support `URI
      resolution <uri-resolver.html>`__ for remote (RDF) resources.

      Several different approaches seem to be in use. The following
      examples all show a rewrite for this URI:
      ``http://example.org/document/1``. Each example notes an example
      service that uses the approach:

      .. container:: itemizedlist

         -  *Simple Prefixing* (URIBurnder):
            ``http://service.example.com/resolve/http://example.org/document/1``.
            The original URI is simply appended to a new base URL. Has
            the advantage of working with any protocol.
         -  *Prefixing, No Protocol* (Triplr):
            ``http://service.example.com/resolve/example.org/document/1``.
            The original URI is simply appended to a new base URL after
            first removing the protocol (e.g. "http://"). Server will
            need to assume the ``http`` protocol if de-referencing the
            URI or reversing the rewrite.
         -  *Prefixing, With Delimiter* (Callimachus):
            ``http://service.example.com/resolve;http://example.org/document/1``.
            The original URI is simply appended to a new base URL which
            ends with a semi-colon.
         -  *Prefixing, As Parameter* (SPARQL Graph Protocol):
            ``http://service.example.com/resolve?uri=http://example.org/document/1``.
            The original URI is simply appended to a new base URL as a
            query string parameter.
         -  *Rewritten Authority*:
            ``http://data.example.org/document/1``. The authority
            component of the URI is rewritten to create a new base URI.
            This approach might lead to URI clashes unless the input
            URIs have a predictable structure.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Related
                  :name: related
                  :class: title

      .. container:: itemizedlist

         -  `URI resolver <uri-resolver.html>`__

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <              | `Up <identifi        |  `Next <             |
   | proxy-uris.html>`__  | er-patterns.html>`__ | shared-keys.html>`__ |
   +----------------------+----------------------+----------------------+
   | Proxy URIs           | `Ho                  |  Shared Keys         |
   |                      | me <index-2.html>`__ |                      |
   +----------------------+----------------------+----------------------+
