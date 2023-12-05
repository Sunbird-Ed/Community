# Overview

<figure><img src="../../../../.gitbook/assets/Screenshot from 2023-08-11 14-03-25.png" alt=""><figcaption></figcaption></figure>

The ML-Analytical service retrieves data from either MongoDB or Kafka, carries out data transformation, and subsequently transmits the processed data to either Cloud Storage or Kafka. This data will then be accessible within Druid for subsequent analysis purposes.

## Kafka

Kafka is used to build real-time streaming data pipelines. A data pipeline reliably processes and moves data from one system to another, and a streaming application is an application that consumes streams of data.

## MongoDB

MongoDB is a [document database](https://www.mongodb.com/document-databases) used to build highly available and scalable internet applications. With its [flexible schema](https://www.mongodb.com/scale/mongodb-schema-design) approach, it’s popular with development teams using agile methodologies.

## Druid

Apache Druid is a real-time analytics database designed for large data sets. Most often, Druid powers use cases where real-time ingestion, fast query performance, and high uptime.

## Cloud Storage

Cloud storage is a cloud computing model that enables storing data and files on the internet through a cloud computing provider that you access either through the public internet or a dedicated private network connection.
