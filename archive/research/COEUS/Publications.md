# Publications

Roadmaps and ideas for future publications.

## COEUS + Egas

### Plan

* **IWBBIO 2015**
	* [http://iwbbio.ugr.es][1]
	* Abstract: Nov 30th
	* Full: Jan 14th
	* Update submission from SWAT4LS, develop, reengineer and rewrite


* **BMC Bioinformatics** / **Journal of Biomedical Semantics**
	* Full paper covering everything with real use-case
		* also new Egas version?
		* also new COEUS version?

## Linked Registries

### Plan

* New publication as outcome from Rome hackathon/BYOD event
* Showcase COEUS’ use as a unique platform for connecting/linking patient registries
	* Query federation to access distributed data
	* Unique, transparent data model layer unifying heterogeneous patient data

### A semantic web architecture for connecting rare disease registries

_or_ **Towards knowledge federation of linked registries and biobanks**

**Abstract**

Rare disease registries are now an essential tool for all clinical stakeholders.  These systems’ features aim to improve patient treatments, a vital step towards personalized medicine. Yet, the growing number of disease-specific patient registries brings new challenges for life sciences researchers, especially at two interrelated levels: data sharing and data access. These systems are closed data silos, with independent formats and data models. As they were built with security and privacy in mind, available tools lack sharing mechanisms, thus making data access a complex process. Despite these key requirements’ relevance, accessing and sharing anonymized data is essential create knowledge, enabling a better understanding of studied diseases.
As such, we introduce a semantic web-based architecture to connect distributed and heterogeneous  registries. The semantic web paradigm enhances the ways we deal with data, optimising how we can create, infer and publish knowledge. We use COEUS, a semantic web application framework, to deploy multiple registry addons, each extracting anonymized data from the associated registry. These data are translated and mapped to an ontology common to all rare diseases registries. This results in a unique semantic layer, covering the various patient registries, which we access using federated querying. Ultimately, this strategy empowers a transparent view through connected registries, enabling state-of-the-art semantic data sharing and access.

**Random**
Another major concern for data owners regards the need for changes in their software. Traditionally, third parties developed patient registries and biobanks software. For this matter, our approach requires no changes in existing software. We propose the creation of an additional semantic data layer that acts as an external plugin to the existing systems. Although ontology mappings and data translations may be required, this is done outside existing tools.

The translation process is also a key challenge. Existing data, often in legacy closed formats and without a well-defined model, must be abstracted into a new semantic web-based environment. This is where tools like D2R, COEUS, … or … play an important role. These tools facilitate the translation process by providing automated means for converting datasets in legacy formats into triples, ready for integration in a global knowledge base.

The latest BYOD for patient registries and biobanks brought to light three major roadblocks for future developments: 1) scepticism regarding these solutions’ added value, 2) difficulty in finding ontologies and 3) lack of accessible data.
These problems are interrelated and must be seen as a whole. Data custodians are not keen on sharing data from their patient registries and biobanks, even when these data are anonymous. As they fail to see the big picture, they do not recognize the added value data sharing will bring to their own research. This is further hindered by the fact that there is a clear difficulty in finding the adequate ontologies to map internal data from patient registries to an external shared common language. The outcome of this is a lack of interest in sharing data, further locking the potential behind collected data.
In summary, we believe that exploring semantic web technologies to empower a non-intrusive approach is an innovative approach to connect, enrich and deliver data from patient registries and biobanks.

## COEUS Triple Store

### A cloud-based approach for semantic data storage

**Abstract**

(Needs more SaaS…)

Semantic Web technologies have revolutionized modern strategies for discovering and managing knowledge. The new standards for describing, modeling, storing and accessing information, empower developers with new tools for building next generation software. Semantic Web openness and expressiveness enable the creation of more advanced knowledge bases, where relationships amongst data and objects can be explored to infer new knowledge or be reasoned over to expand existing knowledge. In addition, the Semantic Web premise of a truly distributed and intelligent data network is a natural enabler for integration and interoperability challenges.
Despite their evolution, Semantic Web technologies are still in their infancy. This means that there is plenty room for improving existing ones and for designing new strategies. One of the areas where this is a clear need for innovation regards the semantic storage domain. Semantic data are, in its essence, triples: subject - predicate - object axioms asserting an individual data piece. Large collections of such statements form a knowledge base, which must be persisted in some kind of triplestore. Nowadays, triplestore solutions adopt one (or a combination) of three strategies: in memory, database-backed or file-backed. In memory triplestores perform a statement loading task on server startup to load all triple statements into memory. This is the fastest approach for query answering, but the data loading performance is troublesome. Next, database-backed solutions store triple statements in a relational database. This strategy trades the reduced boot time for a poor performance when answering complex SPARQL queries. Despite multiple optimizations, where the mininum table number can be reduced to 4, database-backed solutions will always be slow when processing millions of triples in real time. At last, file-backed solutions involve processing data reads and writes from and to the hard disk. This results in weak performance measures for both boot and query answering time. This solution, whilst far from optimal, is suitable for systems where the query response time is not critical.
From this analysis it is clear that there is room for improving the semantic data storage domain. Herein we introduce a new cloud-based solution, C3S, for storing triple statements. Cloud providers, such as Amazon, Google or Microsoft, deliver high-performance data storage enabling its use in critical scenarios. C3S strategy delivers an easy-to-use plugin for quickly connecting to a cloud-based triple statement storage engine. Connection details and data exchange specificities are handled by the various C3S plugins and clients, which enables their inclusion in new or existing systems. For instance, sample plugins for Virtuoso, Jena or OWLim are available, allowing C3S integration in any of these systems.
C3S' server-side strategy relies on a balanced architecture, combining local in-memory loads with distributed cloud-based storage to deliver transparent access to a reliable high performant solution. For the clients/plugins, a single interface for data exchanges is required, simplifying C3S' use.

[1]:	http://iwbbio.ugr.es