# Projects

## RD-Connect

COEUS can be used throughout the RD-Connect project in many scenarios, promoting the collaboration of distinct institutions within the project and extending COEUS value as a full-fledged solution to deploy new platforms with the latest semantic web standards.

### RD-Connect platform

The RD-Connect platform will be the central hub for analysis of annotated next-generation sequencing data. VCF files originally from EBI’s EGA will be processed through the platform’s standard analysis pipeline, resulting in rich annotated VCF files. Next, these will be indexed and integrated in the platform, making all data easily available for access and querying.

COEUS’ goals are two-fold in the RD-Connect platform:

1. act as a proxy for rich connection networks, via SPARQL and LinkedData;
2. provide a seamless method to provide the RD-Connect platform results as RDF or via LinkedData interfaces.

On the first scenario, COEUS will be used to deploy a simple API that can connect genes (via HGNC symbol) with associated relationships. This implies the creation of a knowledge network (similar to Diseasecard’s). Initially, the prototype will use Diseasecard’s network. Later, we will create a scientifically valid mashup of data from LUMC *Gene-Disease* mappings and output from NeurOmics and NeuRenOmics researchers’ feedback.

The second scenario involves adding a new COEUS instance that can parse summary and statistical data from the RD-Connect platform. While most data are not public, several generic datasets will be made available to the public. These should be integrated into a COEUS seed, enabling access to RDF data or via SPARQL and LinkedData interfaces.

### Linked Registries

COEUS is a unique platform to connect distributed and heterogeneous data. Within RD-Connect, there is an overarching goal of linking data (knowledge) from multiple patient registries. Patient registries are inherently closed, each adopting its own technologies, formats and models. 
COEUS will be configured to access each patient registry, extracting relevant anonymous data. Once multiple COEUS instances are deployed, each using the same data model (an official RD-Connect model), we can easily federate queries to multiple instances, thus connecting similar data.


### Linked Biobanks

Just like patient registries, RD-Connect also strives to interconnect biobanks. Similarly, biobanks are heterogeneous & distributed, making their integration far from trivial. Hence, the plan to use COEUS to connect multiple distributed biobanks is similar to the patient registries’ one. With the various biobanks providing anonymous data publicly, COEUS can be used to map and connect that data through an overarching ontology.

### NeurOmics / EuRenOmics

* COEUS as an horizontal tool for deeply specific vertical rare diseases projects
	* neurological diseases
	* renal diseases
* Pedro Sernadela’s PhD thesis
