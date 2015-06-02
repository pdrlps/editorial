# Summaries

## Ideia

Cada vez mais as páginas web incluem um número elevado de elementos que visam complementar o conteúdo principal da página mas que, de certa forma, apenas complicam a visibilidade do mesmo. Apesar da importância de coleções de ligações para páginas internas ou externas, logotipos ou imagens de publicidade, ou cabeçalhos e rodapés informativos, estes componentes adicionam distrações e dificultam a legibilidade da página. 
Desta forma, neste trabalho pretendemos desenvolver métodos para automatizar a extração do conteúdo mais importante de cada página, oferecendo esta funcionalidade através de um serviço web onde qualquer página poderá ser otimizada. Numa primeira fase, o foco serão páginas onde o conteúdo é maioritariamente composto por texto e imagens. Num segundo nível, o objetivo é dotar os algoritmos de extração de conteúdo de alguma flexibilidade através de modelos (templates) para configurar o que extrair de cada página. No futuro, podemos incluir técnicas de mineração de texto e inteligência artificial para automatizar a deteção de qual o conteúdo mais importante em cada página.
Esta ferramenta será incluída no Diseasecard, facilitando a legibilidade das várias páginas apresentadas no browser em LiveView.

## Objetivos

* Desenvolver pacote/web service para simplificar legibilidade do conteúdo de páginas web
	* Input: URL de uma página
	* Output: conteúdo principal da página (processado pela ferramenta)
* Desenvolver modelo de conteúdos numa página web
	* Texto principal
	* Imagem principal
	* Links externos
	* Links internos
* Valor acrescentado
	* Legibilidade
	* Acesso ótimo ao conteúdo sem distrações
	* Acesso rápido ao conteúdo mais importante da página
	* Vista normalizada de LiveView

## Notas

* O que é importante?
	* Blocos “grandes” de texto
	* Links externos e internos 
	* Imagens
* “Configuração”
	* URLs podem/devem vir a ser configurados com um template
	* O template contém expressões XPath ou identificadores para extrair conteúdo
		* html/body/div[@id=content]
		* \#content
	* Template diz como extrair o conteúdo mais importante
	* Essencial para aprendizagem futura
* Exemplos
	* [http://omim.org/entry/104300][1]
		* Texto Clinical Synopsis…
		* Lista de external links
		* Lista de internal links
	* [https://www.clinicaltrials.gov/ct2/show/NCT01626326][2]
		* Texto Full-text view
	* [http://www.uniprot.org/uniprot/P05067][3]
		* Texto function
		* DNA sequence
		* Lista de external links
	* [http://v4.genecards.org/cgi-bin/carddisp.pl?gene=APP][4]
		* Texto summaries
		* Lista de external links
		* Imagem “genomic view”
	* [http://www.ncbi.nlm.nih.gov/pubmed?term=Alzheimer%20disease%201,%20familial][5]
		* Lista de publicações
	* [http://www.rcsb.org/pdb/explore/explore.do?structureId=3KTM][6]
		* Estrutura proteína em 3D
	* [http://string-db.org/newstring\_cgi/show\_network\_section.pl?identifier=P05067][7]
		* Mapa de ligações da proteína


## Ligações

* * Readability
	* [https://www.readability.com][8]
	* [https://github.com/buriy/python-readability][9]
	* [https://github.com/cantino/ruby-readability][10]
* Instapaper
	* [https://www.instapaper.com][11]
* Pocket
	* [https://getpocket.com][12]
* How do they work?
	* [http://www.quora.com/How-do-Pocket-app-Instapaper-Flipboard-etc-extract-articles-from-a-page][13]



[1]:	http://omim.org/entry/104300
[2]:	https://www.clinicaltrials.gov/ct2/show/NCT01626326
[3]:	http://www.uniprot.org/uniprot/P05067
[4]:	http://v4.genecards.org/cgi-bin/carddisp.pl?gene=APP
[5]:	http://www.ncbi.nlm.nih.gov/pubmed?term=Alzheimer%20disease%201,%20familial
[6]:	http://www.rcsb.org/pdb/explore/explore.do?structureId=3KTM
[7]:	http://string-db.org/newstring_cgi/show_network_section.pl?identifier=P05067
[8]:	https://www.readability.com
[9]:	https://github.com/buriy/python-readability
[10]:	https://github.com/cantino/ruby-readability
[11]:	https://www.instapaper.com
[12]:	https://getpocket.com
[13]:	http://www.quora.com/How-do-Pocket-app-Instapaper-Flipboard-etc-extract-articles-from-a-page