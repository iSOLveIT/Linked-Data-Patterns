.. container:: navheader

   +----------------------+----------------------+----------------------+
   | Overview             |                      |                      |
   +======================+======================+======================+
   | `Prev <in            | Cha                  |  `Next <identifi     |
   | troduction.html>`__  | pter 1. Introduction | er-patterns.html>`__ |
   +----------------------+----------------------+----------------------+

   --------------

.. container:: sect1

   .. container:: titlepage

      .. container::

         .. container::

            .. rubric:: Overview
               :name: overview
               :class: title

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Why A Pattern Catalogue?
                  :name: why-a-pattern-catalogue
                  :class: title

      Design patterns have a number of benefits:

      .. container:: itemizedlist

         -  Patterns have a well-defined structure that encourages focus
            on the essential knowledge being communicated. This makes
            them accessible and easy to consume.
         -  Patterns encourage discussion of related and complementary
            approaches. Design decisions are rarely clear cut. A focus
            on specifics is useful for understanding trade-offs
         -  Patterns provide a name for a particular design decision or
            solution. Collectively they build a lexicon that encourages
            clearer communication between practitioners

      The authors have successfully applied design patterns in their
      software development activities. The approach seemed well suited
      to teasing out some of the experiences and lessons they have
      learnt through working with Semantic Web technologies; the rigour
      of a pattern approach also helped the authoring.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: ...And Why a Book? Why Not a Blog or a Wiki?
                  :name: and-why-a-book-why-not-a-blog-or-a-wiki
                  :class: title

      This is something that we wrestled with for a long time. Our goal
      is that this book should ultimately reflective the collective
      experience of the Linked Data community and we want to encourage
      participation and feedback. You can use the
      `dataincubator.org <http://dataincubator.org/>`__ mailing list to
      discuss the book and debates its contents. We're also hoping to
      include your submissions, corrections and edits in the future.

      But while we want this book to grow as a participatory activity we
      (particularly Leigh) felt that an editorial layer would be a
      useful addition to this process. Helping firm up the naming,
      communication and organisation of the pattern catalogue as it
      develops.

      We also encourage the community, if they find a design pattern
      approach to be useful, to publish and share their own patterns
      using whatever mechanism feels right for them. A thousand flowers,
      etc. The
      `OntologyDesignPatterns.org <http://ontologydesignpatterns.org/>`__
      wiki provides one forum for helping to contribute to this effort.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: What's Not Covered?
                  :name: whats-not-covered
                  :class: title

      This book isn't a primer on RDF or OWL. There are already plenty
      of good sources of introductory material on the technologies
      discussed here. The book makes the assumptions that you have some
      basic understanding of RDF, RDF Schema and possibly OWL. The
      examples are given in Turtle syntax, so you should be familiar
      with that syntax too.

      If you're looking for a deeper introduction to modelling with RDF
      Schema and OWL then you should read `Semantic Web for the Working
      Ontologist <http://workingontologist.org/>`__. It's a great book
      that will give you a thorough understanding of how to apply the
      technologies. We're hoping that this work is in some sense a
      companion piece.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: How the Catalogue Is Organized
                  :name: how-the-catalogue-is-organized
                  :class: title

      The catalogue has been broken down into a number of separate
      chapters. Each chapter collects together patterns that have a
      common theme.

      .. container:: itemizedlist

         -  `Chapter 2, Identifier
            Patterns <identifier-patterns.html>`__
         -  `Chapter 3, Modelling Patterns <modelling-patterns.html>`__
         -  `Chapter 4, Publishing
            Patterns <publishing-patterns.html>`__
         -  `Chapter 6, Application
            Patterns <application-patterns.html>`__

      The catalogue also includes a few patterns that arguably aren't
      patterns at all, they're similar features of the RDF model; `Typed
      Literal <typed-literal.html>`__ for example. We decided to include
      these for the sake of helping to document best practices. There
      are plenty of examples and material on some of these basic
      features but they're often overlooked by both experienced and new
      practitioners. So we've opted to document these as patterns to
      help draw attention to them.

   .. container:: sect2

      .. container:: titlepage

         .. container::

            .. container::

               .. rubric:: Examples
                  :name: examples
                  :class: title

      The pattern catalogue includes a number of examples. Snippets of
      code, data, or queries that help to illustrate a specific pattern.
      Code examples are shown in this font.

      Where we should examples of RDF data, we have used the
      `Turtle <http://www.w3.org/TeamSubmission/turtle/>`__ syntax for
      RDF because its more concise and readable than RDF/XML. We have
      preferred to use prefixed names for standard RDF properties and
      classes but, for clarity, have not always included the
      declarations of these prefixes in the examples. This allows the
      example to focus on the particular usage being demonstrated.

      Unless otherwise stated, assume that when you're looking at some
      Turtle we've declared the following prefixes:

      .. code:: programlisting


         @prefix ex: <http://www.example.org/>
         @prefix foaf: <http://xmlns.com/foaf/0.1/> .
         @prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
         @prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
         @prefix dcterms: <http://purl.org/dc/terms/> .
         @prefix dc: <http://purl.org/dc/elements/1.1/> .
         @prefix owl: <http://www.w3.org/2002/07/owl#> .
         @prefix skos: <http://www.w3.org/2004/02/skos/core#> .
         @prefix xsd: <http://www.w3.org/2001/XMLSchema#> .

      In the `Data Management
      Patterns <data-management-patterns.html>`__ section of the book a
      number of the examples use the
      `TRiG <http://www4.wiwiss.fu-berlin.de/bizer/trig/>`__ syntax,
      which is an extension of Turtle that supports Named Graphs.

.. container:: navfooter

   --------------

   +----------------------+----------------------+----------------------+
   | `Prev <in            | `Up <i               |  `Next <identifi     |
   | troduction.html>`__  | ntroduction.html>`__ | er-patterns.html>`__ |
   +----------------------+----------------------+----------------------+
   | Chap                 | `Ho                  |  C                   |
   | ter 1. Introduction  | me <index-2.html>`__ | hapter 2. Identifier |
   |                      |                      | Patterns             |
   +----------------------+----------------------+----------------------+
