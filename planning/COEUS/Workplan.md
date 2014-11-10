# Workplan

## Short term

**Short term** developments should be ready as soon as possible (deadline on February 2015).

### Benchmarks

**What**: test performance with very (very) large datasets, find bottlenecks, plan for scalability.

**How**: implement simple scenarios with varying loads, from small Excel datasets to large (billions of rows) datasets.

**Why**: identify where we can optimize the multiple framework components, what is delaying the import process, what causes the large query response times…

**To do**

* OrphaNet import (S)
* GeneRIF import (M)
* [https://developers.google.com/freebase/data][1] (L, XL)

*Notes*: in tandem with Pedro Sernadela’s integration simulator. More details: [https://github.com/bioinformatics-ua/COEUS/issues/8][2]

### Engine

**What**: improve the framework’s core features.

**How**: write new code, fix bugs.

**Why**: performance and usability optimizations.

**To do**

* Add Excel support for file import: [https://github.com/bioinformatics-ua/COEUS/issues/5][3]
* Add multithreading support for triplification process: [https://github.com/bioinformatics-ua/COEUS/issues/2][4]
* Item objects with URIs: [https://github.com/bioinformatics-ua/COEUS/issues/4][5]
* Fix custom relationship support: [https://github.com/bioinformatics-ua/COEUS/issues/6][6]
* Improve support for URI reuse: [https://github.com/bioinformatics-ua/COEUS/issues/7][7]
* Fix Pubby accept headers: [https://github.com/bioinformatics-ua/COEUS/issues/11][8]
* Update POST on web services: [https://github.com/bioinformatics-ua/COEUS/issues/12][9]

### Mining and Annotation

**What**: continue the integration & interoperability of COEUS and Egas, bringing the results of automatic/manual annotation to a publishable Semantic Web-based interface.

**How**: develop new export plugins for Egas, develop new import plugins for COEUS, optimize Egas-COEUS workflow.

**Why**: semantic text annotation is something that is ripe for publishing.

**To do**

* Plan, code, test: rinse and repeat.
* Publish: paper for IWBBIO and journal later.

## Medium term

**Medium term** developments are on a secondary range, going to August 2015 (until next vacation).

### Interoperability

**What**: showcase interoperability with external, i.e., famous, projects.

**How**: create new comprehensive test seeds with new documentation, tutorials and videos.

**Why**: improve dissemination strategies.

**To do**

* Setup seed connecting with the EBI RDF platform
* Setup seed connecting with OpenPHACTS
* Setup seed connecting with UniProt RDF data
* Test more external tools
	* Stanbol
	* Kettle
	* Dydra
	* Talis
	* CumulusRDF
	* Sparqlr

*Notes*: Add more use cases based on RD-Connect (and EMIF) work.

### Engine

**What**: improve the framework’s core features.

**How**: write new code, fix bugs.

**Why**: performance and usability optimizations.

**To do**

* Switch codebase to support Jetty’s autodeployment instead of Apache Tomcat.
* 

### Marketing

**What**: continuous improvement of marketing materials must be realized in something new, that can foster adoption and decrease entry barrier.

**How**: promotional videos (with simple diagrams and interactions), new flyer highlighting use cases of actual relevance.

**Why**: COEUS needs more users!

**To do**

* Update documentation, tutorial, examples…: [https://github.com/bioinformatics-ua/COEUS/issues/10][10]
	* More tutorials, covering more options with greater depth
* Create promotional videos/animations: 
	* Full video with general platform overview
	* Highlight Excel to cloud to SW workflow
	* Highlight heterogeneous integration and SW abstraction
	* Highlight SW features
	* [https://github.com/bioinformatics-ua/COEUS/issues/13][11]

## Long term

**Long term** developments are required but not critical for the releases. These  just cover features that are ready for implementation, not future ideas that can be included.

### Automated import

**What**: Improve COEUS’s configuration, enabling the automatic extraction of models from relational databases, XML/JSON structures or CSV files.

**How**: There are already multiple tools to accomplish this, check the best solution to integrate in COEUS’ package.

**Why**: simplify the model creation process.

**To do**

* Assess tools for automated RDF/ontology creation.
	* D2RQ: [http://d2rq.org][12]
	* [http://www.w3.org/TR/rdb-direct-mapping/][13]
	* [http://www.w3.org/wiki/ConverterToRdf][14]
	* [https://github.com/cygri/tarql][15]

[1]:	https://developers.google.com/freebase/data "Freebase"
[2]:	https://github.com/bioinformatics-ua/COEUS/issues/8
[3]:	https://github.com/bioinformatics-ua/COEUS/issues/5
[4]:	https://github.com/bioinformatics-ua/COEUS/issues/2
[5]:	https://github.com/bioinformatics-ua/COEUS/issues/4
[6]:	https://github.com/bioinformatics-ua/COEUS/issues/6
[7]:	https://github.com/bioinformatics-ua/COEUS/issues/7
[8]:	https://github.com/bioinformatics-ua/COEUS/issues/11
[9]:	https://github.com/bioinformatics-ua/COEUS/issues/12
[10]:	https://github.com/bioinformatics-ua/COEUS/issues/10
[11]:	https://github.com/bioinformatics-ua/COEUS/issues/13
[12]:	http://d2rq.org
[13]:	http://www.w3.org/TR/rdb-direct-mapping/
[14]:	http://www.w3.org/wiki/ConverterToRdf
[15]:	https://github.com/cygri/tarql