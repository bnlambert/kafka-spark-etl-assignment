# Real-time Data Analytics Pipeline

## Tools

- Apache Kafka

- Apache Spark Streaming

- Docker & Docker Compose


## Architecture

The architecture decision was made such that the entire setup can be tested on locally and deployed remotely with minimal configuration.

The different components of this pipeline are:

### The data source (Rest API)

Our data source is a rest API that does not provide web hooks or streaming capabilities via web sockets. For this reason, our pipeline will need to periodically call the API for update(API polling).

### Data integration with Apache Kafka Connector

I chose Kafka Connect over implementing polling logic directly into the Kafka producer application because it will require a lot of effort to write the code, scale it and make it fault tolerant.

### Broker (Apache Kafka Cluster)

### Data transformation with Apache Spark Stream

![Pipeline Architecture](architecture.jpg)