# Component Diagram



<figure><img src="../../../../../.gitbook/assets/Level 0 ML Component Diagram (2) (1).png" alt=""><figcaption></figcaption></figure>



The component depicted above offers a comprehensive view of the entire Manage Learn, showcasing its vital components and the significant roles they play in the construction and functioning of Manage Learn.



For more details visit here

{% embed url="https://app.gitbook.com/o/-Mi9QwJlsfb7xuxTBc0J/s/-MkgPDmvKwE_DgYJbvPS/~/changes/846/misc/templates-1/overview" %}

### [ML Core service](../ml-core-service/)

ML Core service plays a vital role in crafting programs and solutions within the Manage Learn environment. It acts as the bridge connecting Manage Learn with the cloud service, enabling the retrieval of preSignedUrls and downloadableUrls.



### [ML Project Service](../ml-project-service/)

ML Project Service empowers the micro-improvement capability within the Manage Learn Building block. This integral service engages with other micro services within Manage Learn and uses Learner Service and Sunbird RC to produce certificates upon a successful compilation of improvement projects.



### [ML Survey Services](../ml-survey-service/)

ML Survey Services facilitate the integration of survey and observation capabilities into Manage Learn. This service allows users to actively participate in surveys and observations.



### [ML Reports Services](../ml-report-service/)

The ML Reports Service is designed to create reports, charts, and graphs to support analytical insights.



Upon the compilation of user resources, the ML Core, ML Project, and ML Surveys services will initiate the transfer of data to Kafka. This data will subsequently be archived within Druid, serving as a repository for future utilization. Eventually, the Reports Services will harness this stored data to generate reports.



### MongoDB

MongoDB serves as the repository for storing all data.

### Kafka

Kafka functions as the communication bridge, transmitting data to various services, including analytics.

### Druid

Druid acts as the data repository specifically designated for generating reports.

### Cloud Storage

Cloud Storage is utilized for safeguarding evidence and documents.

\
\
