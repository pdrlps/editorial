# Exploring Patient-level Data

## abstract

The exploration of patient-level data is the subject of many large-scale projects. Related areas cover a broad array of topics. These range from patient registries to rare diseases research, among others. The overarching goal behind existing initiatives is to uncover the full potential behind patient-level data. These data are essential for knowledge discovery, and will lead to a better understanding of diseases. In this work we performed a review of well-known large-scale initiatives, strategies and projects where the exploration of patient-level data is an underlying goal. We setup and evaluation framework assessing, for each project, its technological and scientific outcomes, partners’ features and other miscellaneous data-related topics. Our aim is to unveil on-going challenges in this domain, exploring how we can transform them into opportunities for future developments. Stakeholders continually push forward new requirements to this area, bringing new challenges that require intensive translational research. Hence, we need a better approach to understand how these challenges can be converted into open opportunities. Only with this evolution we can continue moving forward towards personalised medicine.

## Introduction

The widespread collection of patient-level data represents a critical step towards the realisation of personalised medicine. These data stem from primary care centres, hospital information systems, clinical trials’ cohorts and administrative platforms. Moreover, it withholds a huge potential that goes beyond daily clinical care.
Yet, along with the miscellaneous opportunities to explore patient-level data, this unparalleled growth of patients’ digital metadata brings several challenges. Data size, lack of open access, heterogeneity or the use of primitive technologies are some of the issues researchers face when dealing with patient-level data. In contrast, exploring the potential behind these data will lead to the discovery of new knowledge, essential to improve the current clinical narrative.
Although patient-level data from public institutions, such as hospitals or regional/national administration centres, should be easier to access, it is generally locked under primitive technological implementations. This results in closed data silos that hinder scientific and technological evolution. Several large-scale projects already try to commoditise access to these data, whether through policies or technical standards for data exchanges.
Pharmaceutical companies are also responsible for a big chunk of patient-level data. Clinical trials’ cohorts generate comprehensive patient datasets whose value for personalised medicine research is immeasurable. Despite this, most of pharmaceutical data are private. 
It is important to distinguish between private companies’ data, which is the basis for internal research and development for new drugs and treatments, from public research datasets, fundamental to advance general scientific research. Although pharmaceutical companies are entitled to keep their results private, policies should be put in place to foster the sharing of clinically relevant results into the public domain.
Dealing with this heterogeneous mixture of private and public patient-level data, tools, standards and projects is in itself a complex research and development challenge. Ultimately, the entropy in this ecosystem is delaying what should be a swift evolution. Hence, we need to evaluate past and on-going initiatives to better assess and plan the personalised medicine research and development roadmap for the upcoming years. 
For this matter we performed a review of the outcomes of existing initiatives, identifying current challenges and uncovering new opportunities. We present this comprehensive review targeting three key objectives: (1) identify the best initiatives dealing with patient-level data, (2) inspect and study their different features and (3) evaluate tackled challenges and open opportunities.

## Methods

### Design
This review covers mostly past and on-going large-scale projects. Selected projects’ evaluation is based on an assessment framework with four key components: control, sustainability, technology and science. This design allows us to better understand the projects’ outcomes distribution as well as defining an initial categorization for each project. We chose topics for matching criteria in each area based on mappings with existing ontologies, e.g., SKOS (Simple Knowledge Organization System) [1]() or EDAM (EMBRACE Data and Methods) ((ref EDAM)).
At the control level we assess several topics, detailed next.
• Data ownership: Who owns the project data and who decides whether to make data available or not. Available options are project, partner or community.
• Data access: Is there open access to the project’s data or is it closed to project partners. Available options are open, closed or partners only.
• Data storage: Are data stored in partners’ private repositories or publicly shared with the involved community. Available options are private, public or partners only.
• Patient involvement: Are patients in defining the data ownership, i.e., can patients control who can see their personal data in the project’s systems. Available options are yes or no.
• Security, privacy and auditing: How are security, privacy and auditing issues dealt with within the project? Available options are external, project, none.
In this review we also assess the selected projects’ sustainability, covering several areas. These are detailed next. 
• Business model: What is the business model behind the data owners. This has implications on what happens beyond each project’s scope. Available options are business, academia or undefined.
• Data maintenance: Associated with the project’s partners business model, we have to assess what will happen with the collected data when the project finishes. Available options are composed of erased, stored, open sourced, offline or undefined.
At the technology level we evaluated several relevant areas for translational research. 
• Technological outcomes: Are there (or will there be) any relevant technical outcomes from the project? Available options are yes, only scientific, too soon to know or unknown.
• Technology: What are the main technological outcomes of each project. This includes web services, database, framework, library, virtual machine, infrastructure, standards or undefined.
At last, we inspected the key scientific outcomes for each project, evaluating their areas of impact.
• Field of research: The fields of research to where the outcomes from the patient level data exploration will be applied. These include genomics, transcriptomics, proteomics, epigenomics, phenomics, metabolomics, pharmacogenomics and other.
• Area of Interest: Similarly to the field of research, we identified the technological areas of scientific interest that were studied in the project. Available options are analytics, annotation, data visualization, data integration, text mining, ontology, semantic analysis and other.

#### Inclusion and Exclusion Criteria

We searched for large-scale international projects in general financing listings and EU- or NIH-funded projects. The inclusion criteria for this review were as follows:
• ongoing or finished after January 1st, 2010;
• sponsored mainly by the NIH or the European Comission;
• includes partners from both academia and the business sector;
• must focus on rare diseases, pharma or direct patient involvment;
• must have published public results.
For all identified projects, we reviewed titles, funding information, references and available publications to better assess if the projects appeared to meet all inclusion criteria. If insufficient information was available to make a confident decision, we contacted key project partners to disclose further details.

### Projects
After processing our initial set with over 100 projects ((ref Full Listings)), we analysed deeply the 17 projects that met our inclusion criteria.

Table x - Project overview table


On a first evaluation we can quickly assess that…
(tbc)
.



## Results

There are miscellaneous projects working on improvements to the exploration of patient-level data. These stem from several areas of interest and cover miscellaneous research domains. However, policy and technology advances originate challenges and leverage opportunities. Challenges relate to data discovery, access, acquisition and ownership. This brings several opportunities to deploy future solutions that fully explore the enormous amounts of patient-level data.

### Challenges

There’s a clear dichotomy regarding data. Patient-level data is a very specific use case for exploration. While there are too much data scattered throughout multiple stakeholders, they are wildly difficult to obtain. The outcome of this is that, in the end, there is not enough data to generate statically meaningful conclusions. Hence, we cannot discover or infer new knowledge because there is no access to a minimal amount of patient data.
Along with distribution, data heterogeneity arises as a key challenge for exploring patient-level data. There are several projects dealing with creating new and improving existing data standards for data sharing. However, these are far from being widely adopted throughout international stakeholders. Bioinformatics and pharmacogenomics projects also face these challenges. Nevertheless, for these there are already adequate standards for data storage and exchange. 
In the same vein, data translation also arises as a complex challenge for researchers. In addition to the obvious sense, translating data between multiple languages, there is the data translation from low-level free text data to structured information. Clinicians’ reports traditionally include their notes in free text. These notes must be mapped to a shared domain, elevated from simple text to meaningful structured knowledge.
Data discovery, access and acquisition are typical problems that can be solved by improving existing technologies and by focusing on their widespread adoption. Unlike these, data ownership is a much more complex issue. Dealing with data ownership involves tackling issues related with government’s policies, stakeholders’ interests and projects’ internal guidelines. In an ideal scenario, all patient-level data should be available for research purposes. This should be particularly enforced in publicly funded projects. Yet, this does not happen as most projects are not authorised to share data and, where data are shared, access restrictions are in place.

### Opportunities

Great challenges leverage great opportunities. From our review, we believe there is room for improving how we explore patient-level data and how we can use it to further improve research & development towards personalised medicine. 
There is huge potential behind the combination of data available worldwide. Yet, we need to develop and disseminate new technologies that improve how relevant entities collect, store and share patient-level data.
To obtain real advances in this domain, we must see worldwide patient-level data as a whole, and not as single detached data silos. Although we already have the technology to accomplish this, stakeholders must unite efforts to make this holistic view a reality.
At the technical level, opportunities arise that demand the creation of new software and new standards. Likewise, at a policy level, we must improve existing guidelines and policies to better cover data sharing and ownership, and ethics issues.
New data management standards should promote better (and easier) ways to access and share data. This will empower knowledge discovery, and enable the integration and interoperability among patient-level data silos throughout the world. Going from patient-level data to summary-level data, and vice-versa, should be a simple straightforward process.
Ideally, new software tools will streamline collaboration and sharing among patients and clinicians. These should promote ease of access to patient information and enhance the communication process among clinicians. Furthermore, new tools are required to improve data ownership controls, facilitating how patients, clinicians or researchers express who has access to relevant personal data.
Despite the great opportunity for creating new standards and software, these assets alone are not enough to change the current scenario. New politics and guidelines, stemming directly from key worldwide stakeholders, must be disseminated to all interested parties. Moreover, with adequate support from governmental agencies (regional, national and international), projects and their internal partners will proactively work towards implementing these new guidelines.

## Discussion

As this review reveals, there is room for change in the exploration of patient-level data. However, we must take in account that these results are biased and strict. This is an ever-expanding field with lots of partners, projects and companies working in this subject. We believe the growing relevance of genomics data as well as several other technological advances will be essential to continually improving the exploration of patient-level data.


### The Growing Relevance of Genomics Data

The core focus of this review revolves around projects dealing with patient-level data stemming from electronic patient records. However, the quantity and quality of patient databases focused on genomics data is growing. Furthermore, next generation sequencing technologies streamline the generation of huge patient datasets.
In a sense, patient sequencing data are patient-level data. Projects such as the 1000 genomes project ((refs 1000g), dutch genomics ((refs)), uk genomics ((refs)), are trying to sequence large numbers of individuals to better understand existing genotype-phenotype relationships and uncover new ones.
In the long-term, these data will be included in clinical patient registries. They may even be part of the electronic patient record, where clinicians will require new tools to explore these data. In summary, this is a whole new field of exploration for personalised medicine and patient-level data research that cannot be ignored.

### Implications for Future Research

As detailed in previous sections, the various opportunities highlight the room for improvement in this domain. Assessing the projects’ timing evolution we identify that the focus on sharing, dissemination and patient control is of growing relevance in the field.
The creation of new technical standards and data sharing policies will be fundamental for future research. Moreover, these topics are emerging in current project calls. Thus, they are becoming a stepping-stone for future research and infrastructure initiatives.
Despite the scale of on-going projects, they will not cover every possible topic. Technological developments in data visualisation, integration and interoperability, originating from distinct areas, must be brought to patient-level exploration. The foundation of translational research, where multiple technical research areas collide, will be even more meaningful in the future.

## Conclusions

This comprehensive review delivers a general overview of different initiatives that promote the exploration of patient-level data. We limited our study to research and development projects in the recent past and established base criteria to evaluate on-going initiatives. As preliminary results, we already identified several opportunities for future developments. Namely, (1) bringing distributed data together, (2) putting more advanced sharing and integration software at clinicians’ fingertips and (3) pressuring stakeholders for stricter data access and exchange guidelines. The lack of well-established and widely adopted solutions covering these areas represents a major roadblock for the adequate exploration of patient-level data. However, if future projects consistently adopt these overarching goals, personalised medicine will be one step closer. 

