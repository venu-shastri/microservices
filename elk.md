
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
#### Inputs
This stage help us to  to get data into Logstash
##### commonly-used inputs are:
- **file**: reads from a file on the filesystem, much like the UNIX command  `tail -0F`
-   **syslog**: listens on the well-known port 514 for syslog messages and parses according to the RFC3164 format
-   **redis**: reads from a redis server, using both redis channels and redis lists. Redis is often used as a “broker” in a centralized Logstash installation, which queues Logstash events from remote Logstash “shippers”.
-   **beats**: processes events sent by  [Beats](https://www.elastic.co/downloads/beats).

#### Filters
Filters are intermediary processing devices in the Logstash pipeline.  Combine filters with conditionals to perform an action on an event if it meets certain criteria. 
-   **grok**: parse and structure arbitrary text. Grok is currently the best way in Logstash to parse unstructured log data into something structured and queryable. With 120 patterns built-in to Logstash, it’s more than likely you’ll find one that meets your needs!
-   **mutate**: perform general transformations on event fields. You can rename, remove, replace, and modify fields in your events.
-   **drop**: drop an event completely, for example,  _debug_  events.
-   **clone**: make a copy of an event, possibly adding or removing fields.
-   **geoip**: add information about geographical location of IP addresses (also displays amazing charts in Kibana!)

#### Outputs

Outputs are the final phase of the Logstash pipeline. An event can pass through multiple outputs, but once all output processing is complete, the event has finished its execution
##### commonly used outputs
-   **elasticsearch**: send event data to Elasticsearch. If you’re planning to save your data in an efficient, convenient, and easily queryable format… Elasticsearch is the way to go. Period. Yes, we’re biased :)
-   **file**: write event data to a file on disk.
-   **graphite**: send event data to graphite, a popular open source tool for storing and graphing metrics.  [http://graphite.readthedocs.io/en/latest/](http://graphite.readthedocs.io/en/latest/)
-   **statsd**: send event data to statsd, a service that “listens for statistics, like counters and timers, sent over UDP and sends aggregates to one or more pluggable backend services”. If you’re already using statsd, this could be useful for you!
## Beats
Beats are great for gathering data and hey sit on your servers, with your containers, or deploy as functions. Beats can centralize data in Elasticsearch or to add  processing muscle, Beats can also ship to Logstash for transformation and parsing.
#### Different Types of Beats
-   [Auditbeat](https://www.elastic.co/guide/en/beats/auditbeat/6.6/auditbeat-getting-started.html): collect your Linux audit framework data and monitor the integrity of your files.
-   [Filebeat](https://www.elastic.co/guide/en/beats/filebeat/6.6/filebeat-getting-started.html): tails and ships log files.
-   [Functionbeat](https://www.elastic.co/guide/en/beats/functionbeat/6.6/functionbeat-getting-started.html): read and ships events from serverless infrastructure.
-   [Heartbeat](https://www.elastic.co/guide/en/beats/heartbeat/6.6/heartbeat-getting-started.html): ping remote services for availability.
-   [Journalbeat](https://www.elastic.co/guide/en/beats/journalbeat/6.6/journalbeat-getting-started.html): read and ships event from Journald.
-   [Metricbeat](https://www.elastic.co/guide/en/beats/metricbeat/6.6/metricbeat-getting-started.html): fetches sets of metrics from the operating system and services.
-   [Packetbeat](https://www.elastic.co/guide/en/beats/packetbeat/6.6/packetbeat-getting-started.html): monitors the network and applications by sniffing packets.
-   [Winlogbeat](https://www.elastic.co/guide/en/beats/winlogbeat/6.6/winlogbeat-getting-started.html): fetches and ships Windows Event logs.
## Kibana
Kibana is an open source analytics and visualization platform designed to work with Elasticsearch.  Kibana enables to search, view, and interact with data stored in Elasticsearch indices and can easily perform advanced data analysis and visualize  data in a variety of charts, tables, and maps.

## Kafka
Apache Kafka is a distributed streaming platform

### Kafka streaming platform has three key capabilities
<!--stackedit_data:
eyJoaXN0b3J5IjpbMTEzODk5MDQwMywtMjgxMjY5NTQxLDkyOT
IwNjcwNF19
-->