# Methods

## Architecture

Two distinct ends of the spectrum finally connected. On one side, we have the text-mining tools, which have Egas as their main advanced user interface, enabling the creation of new knowledge through the curation of any textual document. On the other side, we have COEUS, semantic web application framework, enabling the quick creation of new knowledge bases through a simple configuration UI. As we put these two tools together, we aim to create a seamless integration layer, unifying access to the rich curated knowledge for both text-mining developers and biomedical researchers.

**Figure 1**

## Pipeline


1. Automated document annotation
2. Manual document annotation
3. Annotation extraction (via Egas API)
4. COEUS integration into knowledge base
5. Ontology matching (map annotated terms with existing or new identifiers)
6. Publishing (LinkedData, Nanopubs!, SPARQL, API to other apps…)

**Figure 2**

## Implementation

A prototype implementation of this architecture involved adding features to both Egas and COEUS. At the annotator level, API methods were developed to automate exporting curation results and loading data from COEUS. In COEUS, plugins were created to read BioC and AB.1 data. These connectors interact with the mentioned ontology selection and matching tools, generating rich triplesets for integration.
With a COEUS instance deployed for our case study, Egas regularly pushes new curation data, triggering the integration process. Once this finishes, generated knowledge is immediately available for publishing. At this stage, any tool can use the semantically enhanced curation outcomes. I