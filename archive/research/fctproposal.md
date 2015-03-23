# FCT Proposal

This task will cover the creation of a semantic knowledge base to support all other internal tasks. In summary, we will research and develop additional features to improve COEUS. 
COEUS is a semantic web application framework with a steady development base and several applications (ref Diseasecard, nano pubs). 

Although this platform already provides tools for integration and interoperability, we will create new algorithms to streamline the connection to other relevant ontologies, knowledge bases and LinkedData interfaces.

BioPortal (ref) includes a comprehensive collection of life sciences-related ontologies. BioPortal enables, through its web and programmatic interface, straightforward access, browse and search features. We will implement a unique plug-n-play interface between COEUS and BioPortal that, coupled with an intuitive user interface, will ease the integration of BioPortal-stored ontologies within the project’s knowledge base.

The true value behind SW technologies lies in on how easy it is to access and exchange knowledge between independent systems.
LinkedData guidelines promote accessing data via unique URIs that, besides identifying knowledge, must resolve to real data.
SPARQL, the SW query language, complements LinkedData. 
Knowledge bases with an open SPARQL endpoint enable direct queries to their content. This empowers researchers and developers alike with an open knowledge highway. In this area, COEUS will play a fundamental role. COEUS includes, by default, algorithms to discover knowledge from SPARQL endpoints or LinkedData interface. Likewise, it features algorithms to publish collected data via SPARQL endpoint or LinkedData interfaces. 
Hence, COEUS is at the core of our research project, where extracted data will be stored and connected to a worldwide semantic intelligent network.

Alas, we need more than ontologies to fulfil the project’s requirements. The semantic annotation of data will also be crucial to success. Ontologies such as the Annotation Ontology (ref), SKOS (ref) or EDAM (ref), are vital to the scientific knowledge annotation process. 
As such, we will create and deploy new algorithms to optimize the knowledge annotation process. 
Annotation will be a core component to the project’s processing pipeline and, like with BioPortal integration, it will be setup as a plug-n-play feature in COEUS. 
In the long term, we can use any ontology to annotate knowledge in the project’s knowledge base.

Combining current COEUS’ features with these new developments results in an innovative strategy. 
This will bring true added value to the life sciences research domain as it will improve all processes associated with knowledge discovery and management, from data acquisition to LinkedData publishing, among others.