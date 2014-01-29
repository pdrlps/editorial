# Results


## Active monitoring

The resource monitoring tasks are performed by local (server-side) or remote (client-side) agents. 
For an improved performance, monitoring jobs are enqueued in a simple homogeneous queue, where all jobs have the same priority. With various overlapping monitoring schedules, using limited job parallelization prevents system overloads, an acceptable trade off considering the added monitoring delay.
On the client-side, monitoring job execution is more flexible as it can be manually triggered or automated.

### Client-side monitoring
As mentioned, agents can be configured to run locally. This brings three key benefits to the **i2x** platform: distributed monitoring, improved load control and better security.
The ability to download, configure and execute monitoring tasks locally adds a unique distribution layer to i2x. At the architecture level, any number of agents can be remotely deployed and configured to push data to the main i2x server. 
Local agent execution moves the monitoring schedule responsibility to the agent owners. As a result, agent's scheduling is more flexible. Agents run as a standalone ruby script with an associated configuration file. Script execution can be automated, using a cron job task for instance, or can be run ad-ho, when the data owners want to integrate/publish new data.
At last, using client-side agents results in a more secure ecosystem. All communications with the i2x platform are already secured through HTTPS. However, with client-side agents, sensitive content,  such as authentication credentials or private API tokens, do not need to be registered in i2x's server platform. All configurations are stored locally, in a private JSON file (Figure x). Moreover, access to the APIs required for remote monitoring is controlled with set of user-based access tokens. Users can easily add one or more tokens and revoke them in i2x's web interface. The toKen-based strategy also ensures that  the client-side agents can only access integrations and templates associated with the token user.
