# Implementation
i2x’s implementation, programmed in Ruby, is organised in three components: i2x server, i2x client and i2x gem. The source code is available at GitHub [endnote] distributed under the MIT free software license. We used the Rails web framework to  streamline i2x’s server development process.

i2x server is the platform, deploying the framework’s core features. An installation is available online at https://bioinformatics.ua.pt/i2x/. i2x gem provides the methods to configure and deploy local i2x agents,  executed using i2x client scripts.


## Internal model and architecture
### Model
Four core elements compose i2x’s internal model: Integrations, Agents, Events and Templates.
**Agents**
Agents are intelligent algorithms configured to monitor resources. Internally, they analyse data detecting changes in comparison to the last analysis. Agents can be executed locally using i2x’s client and gem. This results in improved security and reduces the data exchanges. Agent’s monitoring scheduling is also flexible, ranging from every 5 minutes to weekly-basis. Available schedules are not hard-coded, the schedule list is defined in the application settings and can differ on distinct i2x server instances.
More importantly, whereas the basic modus operandi is active integration, relying on regular content polling, content changes can also be pushed directly to agents, enabling a passive integration scenario.
In i2x’s initial version, agents can detect changes in four distinct formats: CSV/TSV files, SQL databases (MySQL or PostgreSQL), XML or JSON data. Although these seem rather basic,  these formats cover the output of the majority of data sources and web services available. Moreover, i2x’s open architecture makes it easy to build on these methods to expand the detection to extra data formats.
**Events**
The outcome of agents’ monitoring process are Events. Each content “change” detected by the intelligent agents creates new events. These trigger the execution of delivery templates, enabling the flow of data within i2x.
**Templates**
Delivery templates define the actions that i2x will execute for  new events. i2x’s contains templates for executing SQL queries, sending emails, calling web services (using URL routes) or managing files (in a private user workspace or in an associated Dropbox account). 
In similar fashion, the templates set can be extended with additional plugins to connect custom services or delivery types.
**Integrations**
Integration tasks establish the connection between agents and templates. That is, integrations define the data origin and destination. Integrations match multiple agents with multiple templates, enabling a many-to-many data distribution.

Figure x shows a subset of i2x’s relational model. This highlights the relationships amongst the various core elements and the model’s underlying extensibility.

### Architecture 
Figure x details i2x's architecture. This revolves around 4 interdependent layers with ten basic components, described next.

**Resource**
Origin resources refer to the data sources being monitored by the configured agents. At the moment, these endpoints can provided data in SQL, CSV, XML or JSON format.

**Agent**
Agents are intelligent distributed engines tracking resources and extracting content for verification in format-specific detectors.
Agents are executed in the main i2x server or in remote locations through i2x’s client scripts.

**Detector**
Agents use detectors to track resources looking for changes in the output content. The detector connects to the data store to analyse and retrieve event metadata obtained by the agents.

**FluxCapacitor**
The Flux Capacitor is the main application controller, registering and proxying everything. With all components deployed independently, the Flux Capacitor acts as the glue to keep all pieces together, and as a flow manager, ensuring that all operations are performed smoothly, from event detection to the final delivery. 
Moreover, FluxCapacitor is also i2x’s API, empowering the various platform’s web services.

**Data store**
i2x’s internal data store is a relational database used for persisting application data. Currently, i2x uses MySQL for development and PostgreSQL in production environments. Yet, extra Ruby on Rails configurations can change these properties .
In addition to the relational database, i2x can use a Redis cache for faster change detection and event generation.

**Postman**
The Postman, as implied by its naming, performs the delivery of each template. That is, it finalises the integration tasks, receiving (via POST) event data and applying them to the delivery template for execution.

**Destination**
Destinations are the templates’ objects to which the Postman will connect for the final delivery. At the moment, these can be files (via user-based workspace or Dropbox), SQL databases (MySQL or PostgreSQL), emails or HTTP-based web service calls.

**Log**
The **Log** stores summary information for all actions and flows. Each log entry contains the minimal set of information required to reenact specific transactions or errors. This includes timestamps, origin/destination and the messages sent. For improved tracking and analysis, the backend uses the Sentry platform.


## System workflows
Figure x shows i2x’s basic Extract-Transform-Load pipeline, from data source polling to resource delivery.

1. Poll Content *Agent-Origin resource*: connect to external data source and load content.
2. Return Content *Origin resource-Agent*: The data source returns the requested content.
3. Check Content *Agent-Detector*: The agent sends acquired data to  Detector for content change detection.
4. Check Changes *Detector-Data store*: the Detector imports the data into the internal Data Store and checks if there have been any changes since the last update (new events).
5. Return Events *Data store-Detector*: The Data store analyses the submitted content and returns the set of events with the unique new content.
6. Push/hook events *Detector-FluxCapacitor*: The Flux Capacitor receives new data, pushed from the Detector or hooked from external systems.
7. Forward data *Flux Capacitor-Postman*: the FluxCapacitor sends received event data to the Postman for delivery.
8. Retrieve template *Postman-Data store*: the Postman loads the matched template from the Data store.
9. Return template *Data store-Postman*: the Data store returns matching templates.
10. Process template *Postman*: the Postman transforms the delivery template with the event data.
11. Delivery *Postman-Destination resource*: the Postman performs the final delivery, concluding the ETL workflow.

There two more pipelines enabled that imply surgical changes to i2x’s base pipeline. When dealing with remote agents and when event data are pushed from external resources.
For the former, there are a couple additional steps on the content detection and on the template delivery. FluxCapacitor mediates the content change detection, acting as a middleware layer between the remote agent and the detection engine. Likewise, template delivery is also mediated by i2x’s FluxCapacitor.
When external resources push events, the content detection sub-sequence is ignored. The internal pipeline starts on step 7 as data are pushed directly from the external resources to the FluxCapacitor API.

### Dynamic content change detection
To ensure a reliable stream of changed data, i2x relies on a set of content change detection services. These are specialised for each integrated data format, which enables the rapid identification of new events.
i2x’s adopts an atomic data storage approach for content change detection. That is, agents are configured to extract defined data elements from the original sources, and each of these independently stored, without dependencies with other datasets. This verification process occurs in four steps.
- First, a new detector loads agent metadata
the agent metadata according to the resource data format. For instance, the CSV detector implementation is different from the SQL database detector implementation, although both share the same interface.
- Second, the detector polls the resource for data, which returns the requested dataset. Again, this process is detector-based, requiring format-specific algorithms.
- Third, the detector service validates the retrieved data in an internal cache. The cache acts as the atomic data storage component, storing each data element uniquely.
- Fourth, if the retrieved data are not in the cache, i.e. data is fresh, a new event is created, triggering the data push to the main application controller for delivery and storing the new data in the cache. When the data has already been seen, the integration task finishes at this stage.
i2x implementation is prepared to use a Redis cache for optimal detection performance. Nevertheless, when this component is not available the platform resorts to an internal solution based on the system’s relational database.
The cache verification process can use two distinct data elements. On the one hand, users can configure the cache property for each agent specifying what variable change detection will use. This should be set to track unique data properties, namely identifiers.  E.g. a CSV column number or the output of an XPath query. On the other hand, if there are no data elements that can identify integrated data unequivocally, i2x creates and stores an MD5 hash of the data elements’ content. As changing content results in a new hash value, i2x can detect new events without compromising the system performance.

### Transferring data
At a basic level, i2x is as an intelligent ETL proxy. The framework simplifies the process of extracting, transforming and loading data from distributed sources to heterogeneous destinations.
The data extraction for each resource is configured in the agent, through selectors. Selectors are key-value pairs, mapping a unique variable name, the key, with an expression to extract data elements, the value. Where keys can be general strings, values are specific to each data format. For example, with CSV data, values are column numbers, but with XML data, values are XPath query strings.
Delivery templates perform the transform and load process. Their configuration can have various variables, named within the _%{ }_ expression. These are identified at runtime and should match the selector keys configured in the agent.
For instance, an integration task that extracts data from a CSV file to a SQL database insert has an agent with a set of selectors matching CSV column numbers with variable names. During the transform and load process, i2x replaces SQL template variables (for instance, the INSERT INTO statement values) with values obtained for each variable at each CSV row.
Besides transferring static values for variables, i2x templates can call internal functions or execute custom transformations. i2x functions are named within _${i2x.  }_ and provide quick access to programmatic operations. The simplest example, _${i2x.datetime}_ outputs the time of delivery in the template. More complex examples are written in Ruby code. The _${i2x.code(  )}_ function enables writing simple scripts, evaluated during the delivery. This endows i2x’s templates with a generic, simple and flexible strategy of transforming data. Furthermore, enables conditional  transformations, solving equations or manipulating strings, among many others. 


### Agent distribution
i2x’s distributed architecture relies on the ability to deploy intelligent remote agents. Agents can be executed in the server-side, i.e. in the same machine as i2x’s main server, or at the client-side, i.e. with direct access to resources.
This feature is relevant when we consider the amount of data available in legacy systems, such as relational databases or CSV files, which is not available through public URLs or services. In these scenarios, client agents are configured with the main i2x server details, and deployed on the resource location.
A Ruby script controls local agent execution, which loads all required code through i2x gem. The ETL workflow for distributed agents is similar to what happens in the main server. The major change regards the content change detection engine. Whereas with server-side agents the cache verification occurs within the server codebase, with client-side agents a web service call to i2x's API performs the verification. Likewise, with new events, the client agent initiates the delivery through another web service call.
Users can create one or more application keys, unique 32 character strings, securely identifying web service calls to i2x’s API. Agent’s configuration use these, the *access_token* property, to confirm all API requests. Since the applications keys are unique to each user, i2x’s client agent can only access agents, integrations and templates for the user to whom the application key belongs, thus securing the data flow between distributed agents and the main server.


### Job processing
A queue-based approach to execute monitoring jobs addresses scalability challenges. Since these are the more processing-intensive algorithms and control the application workflow, each monitoring task is enqueued in a homogeneous queue, without priority ordering.
During the predetermined scheduling intervals (every 5 minutes, every 10 minutes, every week…), i2x loads the respective agents. Each agent monitoring task is then enqueued for execution in i2x’s internal queue (managed through the application's relational database).
In parallel with i2x’s application server, a queue tracking service is continuously running, dequeuing jobs according to the system’s resources load. For instance, if the system can only execute two tasks simultaneously, and there are four agent monitoring tasks in the queue, the tasks will be processed two at the time, in order of arrival. Task processing starts with the agent monitoring and proceeds to the final delivery.
In spite of being a rather simplistic scaling method, this  strategy prevents system overloads without compromising the near real-time solution, i.e. introduced delays are not significant to the application workflow.
