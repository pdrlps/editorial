# Results
i2x’s brings great value to scientific data integration landscape. However, while we are keen to emphasise i2x’s extensibility as its main feature, we must highlight three other relevant results.
- Near real-time data integration is achieved through the deployment of intelligent agents, which can operate remotely, to monitor data sources.
- Improved data delivery to heterogeneous destinations using a modern template-based approach, allowing transmitting and transforming data.
- Advanced integration and interoperability, as we can use i2x to empower multiple service-oriented architectures, from publish/subscribe to cloud-based integration-as-a-service.
Although these results are intertwined, we discuss each in detail next.

## Real-time content monitoring
i2x ensures real-time reliable data transmission and up-to-dateness. Local (server-side) or remote (client-side) agents perform resource monitoring tasks. While server-side monitoring is enclosed within i2x's server, remote monitoring brings three key benefits: distribution, improved load control and better security.
The ability to download, configure and execute monitoring tasks locally adds a unique distribution layer to i2x. At the architecture level, we can deploy and configure any number of remote agents, pushing data to the main i2x server. 
Local agent execution moves the monitoring schedule responsibility to the agent owners. As a result, agent's scheduling is more flexible. Agents run as a standalone ruby script with an associated configuration file. Scheduled tasks or manual ad-hoc execution (whenever data owners want to integrate/publish new data) automate i2x's script execution.
At last, using client-side agents results in a more secure ecosystem. All communications with the i2x platform are already secured through HTTPS. Yet, with client-side agents, sensitive content,  such as authentication credentials or private API tokens, are not stored in i2x's server platform. All configurations are saved locally, in a private JSON file (Figure x). Moreover, user-based access tokens control access to the APIs required for remote monitoring. Users can add one or more tokens and revoke existing ones in i2x's web interface. This token-based strategy also ensures that client-side agents only access the user's integrations and templates.

> more real-time monitoring

## Template-based delivery
The use of template-based engines in software is common and the data integration domain is not an exception. Template-based integrations strategies [refs refs refs] traditionally refer to the data extraction activity of the ETL warehousing workflow. As i2x uses intelligent agents for this task, templates' use fulfils transform and load requirements.
As detailed in the implementation, i2x includes a comprehensive template mechanism, based on variables and functions, to generate integration data for delivery to many destinations.  This comprehensive approach is simple, yet flexible.

Currently, building tools to call REST services or manage files bring distinct requirements and imply custom ad-hoc implementations. However, i2x’s template flexibility provides an abstraction on top of these methods. Whether we want to append lines to a CSV file, send an email or POST data to a REST service, users control the entire process in i2x interface.


## Advanced integration & interoperability

### Event-driven architecture
Event-driven architectures adopt a message-based approach to decouple  service providers from consumers [refs 32, 33 alain mouttham event driven]. In these service-oriented architectures, event detection is essential to get a reliable stream of changed data. 
i2x enables this kind of reactive integration. Intelligent agents are configured to detect events, with i2x server acting as a message broker and router.


### Publish/Subscribe
The i2x framework is also an enabler of publish-subscribe software. The basic principle behind this strategy revolves around a dynamic endpoint, the publisher, that transmits data to a dynamic set of subscribers [refs 31, 34 alain mouttham event drive]. Translating this basic principle to i2x's model, we can see the agents as a controlled set of publishers (local or remote), that can be configured, using integrations, to interact with specific templates, the subscribers.
In a real world use case, data owners now have the tools to deliver custom notifications when new data are generated. This further advances the state of the art, becoming vital when we consider the amount of legacy systems used to store data and the availability (or lack thereof) of interoperability tools to connect these systems.

Another major outcome underlying this i2x architecture is the ability to perform asynchronous push-based communication, broadcasting event data to any number of assorted destinations.



### Integration-as-a-Service
Cloud-based integration-as-a-service is the pinnacle of integration and interoperability developments. The i2x framework empowers these architectures, moving one step closer towards interoperable science data [ref Toward interoperable bioscience data]. 
Besides being a service consumer, for both data extraction and loading tasks, i2x is also a service provider, with its rich API. This further improves i2x adaptability to tackle miscellaneous real-world challenges for integration and interoperability.