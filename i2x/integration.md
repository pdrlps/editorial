# Integration

### Publish-Subscribe Architecture
The i2x framework is also an enabler of publish-subscribe software. The basic principle this strategy revolves around a dynamic endpoint, the publisher, that transmits data to a variable set of subscribers (check refs). Applying this basic principle to i2x's model, we can see the agents as a controlled set of publishers (local or remote), that can be configured, using integrations, to interact with specific templates, the subscribers.
In a real world use case, an agent can monitor for specific events in a database and, when new events are detected, publish the new data to a predetermined URL, via POST. This publishing task involves pushing the data to a given endpoint, which must be capable of understanding exchanged content.

