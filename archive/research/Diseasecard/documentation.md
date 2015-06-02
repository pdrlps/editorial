# Documentation and Development Guidelines


### Configuration files

* **config.js**: default COEUS configuration file. Special attention to *environment*, *built* and *debug* properties. More details available on COEUS documentation.
* **dc4.js**: Diseasecard-specific configuration file. Includes connection details to internal index (*index*), Solr host (*solr*) and Redis cache (*redis*).
* **dc4\_joseki\_sdb.ttl**: COEUS configuration file for Joseki (SPARQL endpoint server). Special attention to the database connection details (*sdb:jdbcURL*, *sdb:sdbUser*, *sdb:sdbPassword*). More details available on COEUS documentation.
* **dc4\_predicates.csv**: COEUS predicate configuration file. Contains all used properties for faster indexing and optimal prefix resolution: [http://bioinformatics.ua.pt/coeus/hasConcept][1]\<-\>coeus:hasConcept. More details available on COEUS documentation.
* **dc4\_pubby.ttl**: COEUS configuration file for Pubby (LinkedData server). Special attention to * conf:sparqlEndpoint*, *conf:datasetBase* and * conf:webBase*. More details available on COEUS documentation.
*  **dc4\_sdb\_\<environment\>.ttl**: COEUS configuration file for Jena (triplestore server). Defines database connection properties to where triples are stored. Special attention to *sdb:jdbcURL*, *sdb:sdbUser* and *sdb:sdbPassword*. More details available on COEUS documentation.
* **dc4\_setup.rdf**: COEUS (v1) configuration file for knowledge base creation setup. Contains Entity, Concept, Resource properties. Best edited in Protégé. More details available on COEUS (v1) documentation.

## Code structure

### Packages

* **de.fuberlin.wiwiss.pubby**: Pubby LinkedData interface. More details available on COEUS documentation.
* **pt.ua.bioinformatics.coeus.\***: code from COEUS framework.
* **pt.ua.bioinformatics.coeus.actions.diseasecard**: Diseasecard-specific servlet actions.
* **pt.ua.bioinformatics.diseasecard.services**: code for several internal services and helper utilities.
* **de.fuberlin.wiwiss.pubby**: Pubby LinkedData interface. More details available on COEUS documentation.
* **redis.client.jedis**: Jedis code (Redis client).


## Update/Rebuild

### Tasks

1. Check main knowledge base configuration file (dc4\_setup.rdf) for data source updates.
2. Load OMIM data at Level 0 for * pt.ua.bioinformatics.coeus.common.Run*, which loads *pt.ua.bioinformatics.coeus.api.plugins.OMIMPlugin*
3. Process main data source nodes by levels (1, 2, 3, 4…) watching out for dependencies. This builds the knowledge base.
4. Load disease list into browsing cache * pt.ua.bioinformatics.diseasecard.services.Browsier*
4. Load knowledge network into cache for each disease (OMIM based) and each gene (HGNC based) * pt.ua.bioinformatics.diseasecard.services.Cashier*
5. Index full-text content for Solr-based search * pt.ua.bioinformatics.diseasecard.services.Indexer*

[1]:	http://bioinformatics.ua.pt/coeus/hasConcept "http://bioinformatics.ua.pt/coeus/hasConcept"