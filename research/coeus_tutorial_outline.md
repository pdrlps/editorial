# COEUS: Semantic Web Application Framework
(http://bioinformatics.ua.pt/coeus)

## Content

As the “omics” revolution unfolds, the growth in data quantity and diversity is bringing about the need for pioneering bioinformatics software, capable of significantly improving the research workflow. To cope with these computer science demands, biomedical software engineers are adopting emerging semantic web technologies that better suit the life sciences domain. The latter’s complex relationships are easily mapped into semantic web graphs, enabling a superior understanding of collected knowledge. Despite increased awareness of semantic web technologies in bioinformatics, their use is still limited.
COEUS is a new semantic web framework, aiming at a streamlined application development cycle and following a “semantic web in a box” approach. The framework provides a single package including advanced data integration and triplification tools, base ontologies, a web-oriented engine and a flexible exploration API. Resources can be integrated from heterogeneous sources, including CSV and XML files or SQL and SPARQL query results, and mapped directly to one or more ontologies. Advanced interoperability features include REST services, a SPARQL endpoint and LinkedData publication. These enable the creation of multiple applications for web, desktop or mobile environments, and empower a new knowledge federation layer. 
The platform, targeted at biomedical application developers, provides a complete skeleton ready for rapid application deployment, enhancing the creation of new semantic information systems. COEUS is available as open source at http://bioinformatics.ua.pt/coeus/.

## Methods

COEUS primary focus is the streamlined integration of data from heterogeneous sources into a unified semantic knowledge base. Hence, the latest COEUS developments include a new web-based graphical user interface to facilitate the configuration of the data integration connectors.
With this tutorial/hands-on session, we want to introduce the new setup process, highlighting COEUS’ integration & interoperability features. The session is planned as follows:
- Download and install COEUS
- Setup a new COEUS instance, integrating data from well-know -omics resources
    - Explore the various integration connectors, loading data from multiple heterogeneous resources (HGNC CSV, UniProt XML…)
- Use COEUS’ API to access aggregated data
    - Explore the various data access methods to build a small web information system
- Exploit COEUS SPARQL and LinkedData interfaces for Federated Querying


## For Participants

COEUS (http://bioinformatics.ua.pt/coeus/) is a semantic web application framework targeting the quick creation of new biomedical applications. The framework combines the latest Semantic Web technologies with Rapid Application Development ideals to provide, in a single package, the required tools to build a new semantic web information system from scratch. Diseasecard (http://bioinformatics.ua.pt/diseasecard/), a portal for rare genetic diseases research, was built using this framework. In this tutorial/hands-on session, we will guide you through the process of creating your own custom COEUS knowledge base, similar to what was created for Diseasecard. You will learn how to:
* Create a new COEUS instance
    * From GitHub download to web deployment
* Integrate data from heterogeneous *omics sources into your COEUS knowledge base
    * Create your mashup merging multiple datasets
* Explore COEUS API to access aggregated data
    * Build new rich web information systems using the API
    *  Access knowledge federation through the SPARQL and LinkedData interfaces
We believe that COEUS’ comprehensive set of data connectors to easily import, translate and access data to and from semantic web environments can improve both the research and application development workflows.

## Structure

### Introduction

- Classic COEUS presentation
- introduce the problem, bioinformatics heterogeneity, diversity, big data... (? everyone already knows this!)
- the Semantic Web paradigm as a solution
    - from external heterogeneous sources into a unified knowledge base (connectors, selectorx...)
- the COEUS internal data model: entities, concepts, items, resources...
- data access, Apis, rest, SPARQL, linked data...
- full architecture description
 - Tutorial outline overview
	- Describe what will happen in the following workshop
	- review what everything is
	- recheck VMs, installed components

### Proteomics data overview

- integrate data for proteins, genes and additional metadata
- what will we do: start from specific list, expand with additional concepts and connections
- sources
     - HGNC, UniProt, what else
- think about a shared model to organize these data
    - there are lots and lots of distinct solutions, we are proposing only one
- remember to start with small subset

### Modeling
- define COEUS model for proteomics example
- Entities, Concepts, Resources
- model everything in real time (?)
    - use omnigraffle or something similar to organize the structure
- outcome
    - finished internal data model
    - list of connectors and resource selectors
    - everything ready to configure a new seed

### Check up time
- check if everyone has COEUS working
- create "config" tester tool
- attention to custom computers
    - Tomcat passwords
    - MySQL stuff
- outcome
    - everyone must be on the "same page" (application-wise)

### Web Application
- COEUS application organization
    - web application structure
    - work environments
    - seeds
- COEUS actions
    - configure/setup
    - build
    - rebuild
    - clean

### Wizard
- setup new environment
    - db
    - predicates
    - API keys
    - local configs
    - pubby
    - joseki
- setup new seed
- 
- configure
    - entities
    - concepts
    - resources
    - selectors
- build
- knowledge base overview

### API

(only for documentation)

- method overview
- LinkedData
    - browse specific items
    - show connections
- SPARQL
    - perform custom queries
    - federation (?)
- REST services

### Client Applications
- Sample demo accessing constructed knowledge base
- Web app
    - API keys
    - read/write access
    - write, then SPARQL
- Mobile app
    - highlight framework
    - jQuery mobile?

### Conclusion
- Q&A
- point to documentation











