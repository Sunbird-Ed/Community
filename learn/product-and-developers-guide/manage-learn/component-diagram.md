# Component Diagram

<figure><img src="../../../.gitbook/assets/Level 0 ML Component Diagram (2) (5).png" alt=""><figcaption></figcaption></figure>

The component depicted above offers a comprehensive view of the entire Manage Learn, showcasing its vital components and the significant roles they play in the construction and functioning of Manage Learn.

### [ML Core service](../../../contribute/source-code/workflows/manage-learn/ml-core-service.md)

ML Core service plays a vital role in crafting programs and solutions within the Manage Learn environment. It acts as the bridge connecting Manage Learn with the cloud service, enabling the retrieval of preSignedUrls and downloadableUrls.

### [ML Project Service](../../../contribute/source-code/workflows/manage-learn/ml-project-service.md)

ML Project Service empowers the micro-improvement capability within the Manage Learn Building block. This integral service engages with other micro services within Manage Learn and uses [Learner Service](https://lern.sunbird.org/learn/readme) and [Sunbird RC ](https://docs.sunbirdrc.dev/learn/readme)to produce certificates upon a successful compilation of improvement projects.

### [ML Survey Services](../../../contribute/source-code/workflows/manage-learn/ml-survey-service.md)

ML Survey Services facilitate the integration of survey and observation capabilities into Manage Learn. This service allows users to actively participate in surveys and observations.

### [ML Reports Services](../../../contribute/source-code/workflows/manage-learn/ml-report-service.md)

The ML Reports Service is designed to create reports, charts, and graphs to support analytical insights.

### [ML Analytics Service](../../../contribute/source-code/workflows/manage-learn/ml-anaylatics-service.md)

The ML Analytics Service is constructed upon a framework that incorporates Kafka, MongoDB, Druid, and cloud storage. the ML-Analytics service collects data from MongoDB or Kafka, performs data transformation, and then transfers the refined data to either Cloud Storage or Kafka. This data is then made available in Druid for further analysis needs.

### Observ Data Product

On Demand Druid Exhaust Job is a generic data-product used to generate CSV reports. By passing the druid query config, we can use its capability to generate reports dynamically for any columns included in the druid datasource.

### [Learn Data Pipeline (Flink Jobs)](https://lern.sunbird.org/learn/product-and-developer-guide/data-pipeline-flink-jobs)

Program User Info Job

`program-user-info` is used to record the user's information when the user submits the program. Whenever a program is submitted, this job receives an event with the user's information as JSON data and then it parses and stores it as respective key-value pairs in Cassandra.

### [Learn Data Products](https://lern.sunbird.org/learn/product-and-developer-guide/data-products)

Program Exhaust\
Program user personal info exhaust is data-product that generates CSV file containing user details. Each record represents user details who has joined the [program](../../functional-capabilities/manage-learn/what-is-a-program.md). This service uses flattened data from Cassandra which is created by a Flink job called Program User Info. This data-product is configurable for L2, L3 and L4 [data security levels](https://docs.google.com/document/d/1pLvKSiPYzFm-XNl9zA5KAIU1MM5CC0tC/edit#heading=h.gjdgxs).\\

Upon the compilation of user resources, the ML Core, ML Project, and ML Surveys services will initiate the transfer of data to Kafka. This data will subsequently be archived within Druid, serving as a repository for future utilization. Eventually, the Reports Services will harness this stored data to generate reports.

### MongoDB

MongoDB is a [document database](https://www.mongodb.com/document-databases) used to build highly available and scalable internet applications. With its [flexible schema](https://www.mongodb.com/scale/mongodb-schema-design) approach, it’s popular with development teams using agile methodologies.

### Kafka

Kafka is used to build real-time streaming data pipelines. A data pipeline reliably processes and moves data from one system to another, and a streaming application is an application that consumes streams of data.

### Druid

Apache Druid is a real-time analytics database designed for large data sets. Most often, Druid powers use cases where real-time ingestion, fast query performance, and high uptime.

### Cloud Storage

Cloud Storage is utilized for safeguarding evidence and documents.

\
\\
