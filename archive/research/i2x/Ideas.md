# Ideas

## Features

### Agents

* Ability to test agents configurations
* Ability to include custom HTTTP headers
* New Excel detector
* Add support for Microsoft SQL server

### Templates

* More features on URL routes
* Rewrite internal template functions and ruby code execution engine

### Integrations

* New workflow (wizard-based) to create integrations
	* Setup agents and templates in the integrations wizard
* Rewrite associated Javascript code (specially for all forms)
* Notification on push events


### Usability & Misc

* New dashboard providing an overview of everything happening in the system in real-time
* New Stream view (all events)
* Add real meta tags for SEO
* New “model” library with models for agents and templates
	* Twitter API
	* Google Drive API
	* Dropbox API
	* …

### Marketing

* Make promo flyers
* Make promo videos
* Write white paper
* Re-test UI with real users
* Add more use cases and samples


## Adaptive Polling for Real-time Content Integration

Data integration continues to be a fundamental challenge for advancing science. Although several high-quality tools have recently arisen to improve how we aggregate, harmonise and transfer heterogeneous data, the requirements associated with integration have also evolved. Where traditional integration approaches rely on manual triggers to create time-based snapshots of integrated datasets, current integration scenarios demand an always-updated view of these same datasets. In sum, there should be a constant content flow synchronising origin data sources and destination resources.
As such, we need to develop new dynamic integration strategies that are autonomous and operate in real-time. These should act intelligently to changes detected in tracked datasets, generating a live stream of changed and/or updated data.
There are two distinct methods to accomplish real-time integration, based on opposite approaches. On the one hand, push-based strategies involve sending new data to a set of preconfigured destination resources. Despite its better performance, this strategies implies changing the original data sources, which is not desirable. On the other hand, poll-based strategies rely on the constant monitoring of datasets to identify new or updated content. This approach’s poor performance and heavy use of computational resources are overcome by its adaptability to any kind of system, including legacy data sources.
With a strategy based on the automated polling of data sources, the actual integration of new data can be a residual process in comparison with the wasted computational resources of loading the same dataset over and over again. For instance, assuming a dataset that produces new data on a daily basis, polling it for updates every 5 minutes is not necessary. Likewise, datasets producing new data every hour should not be polled weekly. To overcome this, we need to develop a more intelligent integration algorithm that identifies the best time interval to poll each dataset. This adaptive polling will reduce the waste of computational resources, while still ensuring that data are synchronised across resources. This new algorithm must combine several metrics with data-mining approaches to understand and identify the best scheduling for polling each data source. Furthermore, and taking into account the growing number of available integration tools, the created algorithms should be as generic as possible, facilitating their inclusion in existing frameworks.
