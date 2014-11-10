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

### A semantic web architecture for connecting patient registries

**Abstract**

WRITE ME!

## COEUS Triple Store

### A cloud-based approach for semantic data storage

**Abstract**

(Needs more SaaS…)

Semantic Web technologies have revolutionized modern strategies for discovering and managing knowledge. The new standards for describing, modeling, storing and accessing information, empower developers with new tools for building next generation software. Semantic Web openness and expressiveness enable the creation of more advanced knowledge bases, where relationships amongst data and objects can be explored to infer new knowledge or be reasoned over to expand existing knowledge. In addition, the Semantic Web premise of a truly distributed and intelligent data network is a natural enabler for integration and interoperability challenges.
Despite their evolution, Semantic Web technologies are still in their infancy. This means that there is plenty room for improving existing ones and for designing new strategies. One of the areas where this is a clear need for innovation regards the semantic storage domain. Semantic data are, in its essence, triples: subject - predicate - object axioms asserting an individual data piece. Large collections of such statements form a knowledge base, which must be persisted in some kind of triplestore. Nowadays, triplestore solutions adopt one (or a combination) of three strategies: in memory, database-backed or file-backed. In memory triplestores perform a statement loading task on server startup to load all triple statements into memory. This is the fastest approach for query answering, but the data loading performance is troublesome. Next, database-backed solutions store triple statements in a relational database. This strategy trades the reduced boot time for a poor performance when answering complex SPARQL queries. Despite multiple optimizations, where the mininum table number can be reduced to 4, database-backed solutions will always be slow when processing millions of triples in real time. At last, file-backed solutions involve processing data reads and writes from and to the hard disk. This results in weak performance measures for both boot and query answering time. This solution, whilst far from optimal, is suitable for systems where the query response time is not critical.
From this analysis it is clear that there is room for improving the semantic data storage domain. Herein we introduce a new cloud-based solution, C3S, for storing triple statements. Cloud providers, such as Amazon, Google or Microsoft, deliver high-performance data storage enabling its use in critical scenarios. C3S strategy delivers an easy-to-use plugin for quickly connecting to a cloud-based triple statement storage engine. Connection details and data exchange specificities are handled by the various C3S plugins and clients, which enables their inclusion in new or existing systems. For instance, sample plugins for Virtuoso, Jena or OWLim are available, allowing C3S integration in any of these systems.
C3S' server-side strategy relies on a balanced architecture, combining local in-memory loads with distributed cloud-based storage to deliver transparent access to a reliable high performant solution. For the clients/plugins, a single interface for data exchanges is required, simplifying C3S' use.

[1]:	http://iwbbio.ugr.es