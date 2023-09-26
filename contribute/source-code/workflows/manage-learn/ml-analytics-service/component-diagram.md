# Component Diagram



## GitHub Repository

{% embed url="https://github.com/Sunbird-Ed/ml-analytics-service.giT" %}



<figure><img src="../../../../../.gitbook/assets/Screenshot 2023-08-16 at 2.08.08 PM (1).png" alt=""><figcaption></figcaption></figure>



The Ml-analytics service is constructed upon a framework that incorporates Kafka, MongoDB, Druid, and cloud storage. the ML-Analytics service collects data from MongoDB or Kafka, performs data transformation, and then transfers the refined data to either Cloud Storage or Kafka. This data is then made available in Druid for further analysis needs.

The Analytics Service is composed of three key modules,&#x20;

1. Observations

&#x20;The basically do the batch and real-time data ingestion.&#x20;

* Batch: Operating on a predefined schedule, it reads Observation-related data from MongoDB. The data is then transformed into a flattened structure before being loaded into Druid for further analysis.
* Real-time: The system subscribes to a designated Kafka topic that holds observations. Upon receiving new observations, the system processes them and subsequently publishes the processed data to another Kafka topic. This processed data is then consumed by Druid for real-time analysis.

[ml-survey-service.md](../ml-survey-service.md "mention")



2. Projects&#x20;

* Batch: Operating on a predefined schedule, it reads project-related data from MongoDB. The data is then transformed into a flattened structure before being loaded into Druid for further analysis.



[ml-project-service.md](../ml-project-service.md "mention")



3. Survey

The basically do the batch and real-time data ingestion.&#x20;

* Batch: Operating on a predefined schedule, it reads survey-related data from MongoDB. The data is then transformed into a flattened structure before being loaded into Druid for further analysis.
* Real-time: The system subscribes to a designated Kafka topic that holds a survey. Upon receiving the new survey, the system processes them and subsequently publishes the processed data to another Kafka topic. This processed data is then consumed by Druid for real-time analysis.



[ml-survey-service.md](../ml-survey-service.md "mention")\


4. Migrations

&#x20;Migration scripts are used to create, update or retire Charts and Reports in the respective environments.\
&#x20;

