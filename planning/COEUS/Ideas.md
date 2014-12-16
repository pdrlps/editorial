# Ideas

## BioPortal Integration & Interoperability

BioPortal contains the majority of ontologies associated with the life sciences and clinical fields. COEUS should include streamlined features to enhance how these ontologies are imported into each seed. BioPortal includes a REST API that can be queried to retrieve ontology metadata (required for import).
This should be available in the configuration wizard, as a new option in the prefixes loading step.

## Data Visualization

Add default data visualization features to access data stored in each seed.

* Simple SPARQL/RDF navigation package;
* Auditing
	* Assess relationship depth;
	* Validate structure;
	* Check configuration *bugs*;
* Custom Concept-based *bridges*
	* Links (URLs) from Item identifiers (e.g.:, uniprot:P51587 \> http://uniprot.org/uniprot/P51587)

## coeuSMART

Develop integration & interoperability features with tranSMART.

* Plugin-based approach: extract data from tranSMART instances;
* Simple RDF abstraction tool;
* SPARQL endpoint to tranSMART data;
* Continue Rui Mendes’ work.

## COEUS VM

Providing COEUS as a downloadable virtual machine is another step towards becoming a more ubiquitous tool. Making COEUS’ installation easier can be accomplished by providing all the required tools (MySQL, Tomcat, Java…) already available in a single VM package.
Furthermore, we can also design Docker or Vagrant scripts to streamline COEUS’ install process.

## C3S - Cloud (COEUS) Triple Store

Use COEUS as a Software-as-a-Service provider, fully explore cloud capabilities to provide a unique solution for hosting triple data for everyone, online.

* Dydra http://dydra.com/
* Talis http://www.talis.com/
* CumulusRDF https://code.google.com/p/cumulusrdf/
* Sparqlr http://www.sparqlr.com/

* [ http://www.usna.edu/Users/cs/adina/research/Rya\_CloudI2012.pdf ][1]
* http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=4736747
* http://dl.acm.org/citation.cfm?id=1940751
* [http://www.researchgate.net/publication/228950189\_Rdf\_on\_cloud\_number\_nine/file/32bfe50d0a5464c1ae.pdf][2]
* http://ieeexplore.ieee.org/xpl/login.jsp?tp=&arnumber=4629730
* http://dl.acm.org/citation.cfm?id=2188058
* http://iswc2011.semanticweb.org/fileadmin/iswc/Papers/Workshops/SSWS/Ladwig-et-all-SSWS2011.pdf
* http://oro.open.ac.uk/29124/

## Neuropathologies

Deploy very specific COEUS instances along with dedicated client applications that cover the neuropathologies domain. Having this very specific use case will improve Pedro Sernadela’s thesis and allow publishing new articles

[1]:	http://www.usna.edu/Users/cs/adina/research/Rya_CloudI2012.pdf "http://www.usna.edu/Users/cs/adina/research/Rya_CloudI2012.pdf"
[2]:	http://www.researchgate.net/publication/228950189_Rdf_on_cloud_number_nine/file/32bfe50d0a5464c1ae.pdf