
# methods


## Real-time content monitoring

This framework ensures real-time reliable data transmission and up-to-dateness. Local (server-side) or remote (client-side) agents perform resource-monitoring tasks. While server-side monitoring is enclosed within the server, remote monitoring brings three key benefits: distribution, improved load control and better security. 
The ability to download, configure and execute monitoring tasks locally adds a unique distribution layer. At the architecture level, we can deploy and configure any number of remote agents, pushing data to the framework’s main server. 
Local agent execution moves the monitoring schedule responsibility to the agent owners. As a result, agents’ scheduling is more flexible. Agents run as a standalone script with an associated configuration file. Scheduled tasks or manual ad-hoc execution (whenever data owners want to integrate/publish new data) automate the script execution. 
At last, using client-side agents results in a more secure ecosystem. All communications with the platform are already secured through HTTPS. Yet, with client-side agents, sensitive content, such as authentication credentials or private API tokens, are not stored in the server. All configurations are saved locally, in a private JSON file. Moreover, user-based access tokens, unique 32 character strings, control the API data exchanges required for remote monitoring. Users can add one or more tokens and revoke existing ones in the server’s web interface. This token-based strategy also ensures that client-side agents only access the user's integrations and templates.
To ensure a reliable stream of changed data, this framework relies on a set of content change detection services. These services perform basic detection and filtering actions (ref. Gustafsson F. Adaptive filtering and change detection. Wiley New York; 2000), specialised for each integrated data format, enabling the rapid identification of new events. The architecture adopts an atomic data storage approach for content change detection. That is, agents are configured to extract defined data elements from the original sources, and each of these is independently stored, without dependencies to other resources, datasets or agents. This verification process occurs in four steps.
1.	A new detector loads agent metadata according to the resource data format. For instance, the CSV detector implementation is different from the SQL database detector one, although both share the same interface.
2.	The detector polls the resource for data, which returns the requested dataset. Again, this process is detector-based, requiring format-specific algorithms.
3.	The detector validates the retrieved data in an internal cache. The cache acts as the atomic data storage component, storing each data element uniquely.
4.	If the retrieved data are not in the cache, i.e., data are fresh, a new event is created, triggering the data push to the main application controller for delivery and storing the new data in the cache. If the data are not new, the integration process stops. 
In the current version of the framework we use a Redis cache for optimal detection performance. Nevertheless, when this component is not available, the platform resorts to a solution based on the internal data store’s relational database. 
The cache verification process can use two distinct data elements. On the one hand, users can configure the cache property for each agent specifying what variable the change detection algorithm will monitor. This should be set to track unique data properties, namely identifiers. On the other hand, if there are no data elements that can identify integrated data unequivocally, the framework creates and stores an MD5 hash of the data elements’ content. As changing content results in a new hash, we can detect new events without compromising the system performance

## Push based events

## Data delivery

- discuss the actual implementation
- how to handle change over time, two options
	- real time monitoring
		- deployed algorithms for resource tracking
		- extract data elements
		- identify new events
		- trigger integration
		- no changes to original resource
	- push based mechanics
		- wait for data, sent via push
		- involves updates to original resource
- data delivery
	- template-based engine to connect with any kind of service
		- check previous content

