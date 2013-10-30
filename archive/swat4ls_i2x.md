# Semantic rule processing for real-time data integration

## Abstract

Integration-as-a-service platforms arise as a modern strategy to integrate data from distributed environments, making them perfectly tailored for life sciences environments. Nowadays, modern service interoperability strategies, such as workflows and static service-oriented architecture, are giving place to more dynamic environments, where the path from the original resource to the integrative destination is triggered autonomously and in real-time.
A key component in this data integration workflow regards the actual data validation and transformation. In this manuscript we introduce a component to enhance these activities by enabling the execution of complex pre- and post-integration semantic algorithms.

## Introduction

Real-time data integration continues to be a challenge in the life sciences domain. Whereas in other scenarios, such as mechanical engineering or embedded software, several solutions are in place, the automated integration of biomedical data has plenty room for innovation. 
With the evolution of cloud-based technologies, integration-as-a-service ideals are now being used to describe new platforms that enable real-time automated integration of data and services. However, this concept is sill not widely adopted in the bioinformatics technologies domain. 
Moreover, the Semantic Web's underlying flexibility and dynamics can be combined with integration-as-a-service strategies to reach a whole that is more than the sum of its parts. 
The complex Extract-Transform-Load (ETL) data warehousing workflow can be improved through the surgical inclusion of semantic-based components.
This work introduces such element, enhancing the integration workflow with new methods to pre- and post-process data in the integration pipeline. Data can be validated or transformed, according to a predefined set of customisable rules. Simpler validation examples include matching regular expressions evaluate text content or boolean arithmetic expressions to evaluate numeric values. At a more complex level, inference and reasoning can be used to transform content before integration.

## Methods

The semantic rule processing component will interact directly with the ETL engine in the integration pipeline - Figure 1. The basic integration workflow is comprised by three tasks, moving the data from the original source to the desired destination: (1) data extraction, (2) data transformation; (3) data loading. Our rule processing algorithms will divide the second step, data transformation, in two complementary activities: validation and transformation.


## Results

Leveraging on Semantic Web's capabilities, this modular engine can perform complex validation and transformation processing algorithms. These are divided in two categories: validation and transformation.
As the name implies, validation rules evaluate data against defined conditions. Validation algorithms output a boolean value: if true (content is valid) the integration proceeds, if false (content is not valid) the integration workflow stops. 
There are two types of validation rules, based on conditional statements and regular expressions. Conditional validation rules assess if the content obeys to a predefined condition. These mimic simple arithmetic comparisons: less than (<), less or equal than (<=), more than (>), more or equal than(>=), equal (=). While these are suitable for numerical values, string-based content requires more complex validation. For instance, emails, URLs or UniProt identifiers require specific matches for validation. Hence, the inclusion of regular expressions in the validation process is imperative.
Transformation rules are used to generate new content from existing data. Like in the validation rules, there are two types of possible transformations, basic operations and semantic. Basic operations cover number and string manipulation tasks, including mathematical equations for numbers and string concatenation or replacement for text.
Semantic transformations rely on inference and reasoning to generate new knowledge for integration, using complex ontology rules.

## Discussion

Despite the ever growing number of frameworks in this domain, there are several untapped challenges regarding the integration of information from distributed resources. Within these, improving the execution of semantic processing and validation rules arises as a key opportunity to greatly improve data integration platforms.
In this manuscript we propose a modular engine that adds a layer of semantics to traditional data integration workflows. With this strategy, the engine enables executing multiple pre- and post-integration processing algorithms, including data validation and transformation.

