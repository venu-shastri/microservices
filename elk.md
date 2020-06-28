
# ELK
ELK means:

 

-   Elasticsearch
-   Logstash
-   Kibana
## Elastic Search
Elasticsearch is a highly scalable open-source full-text search and analytics engine. It allows you to store, search, and analyze big volumes of data quickly and in near real time. It is generally used as the underlying engine/technology that powers applications that have complex search features and requirements.
### Elastic Search Basic Concepts
- **Near Real-time (NRT):** near real-time search platform means that exist a slight latency (normally one second) from the time you index a document until the time it becomes searchable.
- **Cluster:** is a collection of one or more nodes (servers) that together holds your entire data and provides federated indexing and search capabilities across all nodes.
- **Node:** is a single server that is part of your cluster, stores your data, and participates in the cluster’s indexing and search capabilities.
- **Index:** is a collection of documents that have somewhat similar characteristics.
- **Document:** is a basic unit of information that can be indexed. This document is expressed in [JSON](http://json.org/) (JavaScript Object Notation) which is a ubiquitous internet data interchange format.
## Logstash
LogStash event processing pipeline has three stages:
#### inputs
This stage help us to  to get data into Logstash
##### commonly-used inputs are:
- **file**: reads from a file on the filesystem, much like the UNIX command  `tail -0F`
-   **syslog**: listens on the well-known port 514 for syslog messages and parses according to the RFC3164 format
-   **redis**: reads from a redis server, using both redis channels and redis lists. Redis is often used as a “broker” in a centralized Logstash installation, which queues Logstash events from remote Logstash “shippers”.
-   **beats**: processes events sent by  [Beats](https://www.elastic.co/downloads/beats).

#### Filters
Filters are intermediary processing devices in the Logstash pipeline.  Combine filters with conditionals to perform an action on an event if it meets certain criteria. Some useful filters include:
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTEwNjM0ODY1ODYsOTI5MjA2NzA0XX0=
-->