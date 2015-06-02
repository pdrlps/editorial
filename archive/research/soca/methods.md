
# methods

The main challenge behind our approach is how to handle changes in data over time. As we need to provide always-updated datasets, we have to ensure a virtual stream of changed data being constantly fed into i2x. As mentioned, i2x enables two distinct event types as its input: pushed events and agent-tracked events. Hence, we deploy two distinct strategies to keep up with synchronised origin and destination resources: 1) active integration based real-time content monitoring, where i2x’s intelligent agents constantly poll resources looking for events; and 2) passive integration based on events pushed into i2x. These strategies, and an overview of how data are delivered to their destination, are discussed next.


## Active integration
i2x’s active integration approach is based on the constant monitoring of the original resources. With this strategy, we configure agents to access and process a dataset with a predefined scheduling interval. In the processing step, we analyse the dataset looking for new content. When the agents identify new data elements, an event is created and the configured integration triggered. To complement our cloud-based system, we also developed a local agent that we use to track private datasets in securely closed environments. The entire process is shown in Figure x’s activity diagram.
The agents feature intelligent content change detection algorithms to perform basic detection and filtering actions (ref. Gustafsson F. Adaptive filtering and change detection. Wiley New York; 2000). These are specialised for each integrated data format, enabling the rapid identification of new events. Agents are configured to extract defined data elements from the original sources, and each of these is independently stored, without dependencies to other resources, datasets or agents. When data are extracted, i2x starts a verification process, which occurs in four steps.
1.  A new detector loads agent metadata according to the resource data format. For instance, the CSV detector implementation is different from the SQL database detector one, although both share the same interface.
2.  The detector polls the resource for data, which returns the requested dataset. Again, this process is detector-based, requiring format-specific algorithms.
3.  The detector validates the retrieved data in an internal cache. The cache acts as the atomic data storage component, storing each data element uniquely.
4.  If the retrieved data are not in the cache, i.e., data are fresh, a new event is created, triggering the data push to the main application controller for delivery and storing the new data in the cache. If the data are not new, the integration process stops. 

i2x uses a Redis cache for optimal detection performance. 
The cache verification process can use two distinct data elements. On the one hand, users can configure the cache property for each agent specifying what variable the change detection algorithm will monitor. This should be set to track unique data properties, namely identifiers. On the other hand, if there are no data elements that can identify integrated data unequivocally, the framework creates and stores an MD5 hash of the data elements’ content. As changing content results in a new hash, we can detect new events without compromising the system performance

### Cloud vs local agents
While cloud-based monitoring is optimal for content available online, private local monitoring brings three key benefits: distribution, improved load control and better security. 
The ability to download, configure and execute monitoring tasks locally adds a unique distribution layer. At the architecture level, we can deploy and configure any number of remote agents, pushing data to the framework’s main server. 
Local agent execution moves the monitoring schedule responsibility to the agent owners. As a result, agents’ scheduling is more flexible. Agents run as a standalone script with an associated configuration file. Scheduled tasks or manual ad-hoc execution (whenever data owners want to integrate/publish new data) automate the script execution. 
At last, using client-side agents results in a more secure ecosystem. All communications with the platform are already secured through HTTPS. Yet, with client-side agents, sensitive content, such as authentication credentials or private API tokens, are not stored in the server. All configurations are saved locally, in a private JSON file. Moreover, user-based access tokens, unique 32 character strings, control the API data exchanges required for remote monitoring. Users can add one or more tokens and revoke existing ones in the server’s web interface. This token-based strategy also ensures that client-side agents only access the user's integrations and templates.


## Passive integration

Passive integration is the exact opposite of active integration: instead of constantly tracking resources, i2x idly waits for data sent by external resources. The major drawback of this approach is that it requires changes in the original data sources. Despite this, the integration process is quite simpler and uses fewer computational resources.
Passive integration is based on push-based events and in the Webhooks/RESThooks pattern (ref). This pattern defines a publish/subscribe architecture where connected services are notified of certain actions.
Hence, we expect data owners to “hook” a connection to i2x’s integrations, notifying the platform every time new content is produced. Figure 2 shows an activity diagram with the passive integration process.
The change detection algorithms are very similar to the active integration ones. Despite being on the receiver end of the new data notifications, we still verify i2x’s cache to double check if the data are indeed fresh.


## Data delivery

