# Component Diagram



<figure><img src="../../../../../.gitbook/assets/ML Reports Service L0 (1).png" alt=""><figcaption></figcaption></figure>

The ML Reports Service is constructed using a Druid as a data source. Additionally, it seamlessly collaborates with vital services like [ML Survey Service](../ml-survey-service/), [ML Core Service](../ml-core-service/), and Gotenberg. This Microservice is composed of six pivotal Modules, each playing a crucial role.

#### Assessment

This module helps to get data related to the assessment

#### Resource

It gets data from Druid for any resource and program in which location it started.

#### Reports

Responsible for generating reports.

#### Projects

Responsible for generating reports on Project Document

#### Observation

Responsible for generating reports on Observation Document

#### Survey

Responsible for generating reports on Survey Document



### [Gotenberg](https://gotenberg.dev/)

Gotenberg provides a developer-friendly API to interact with powerful tools like Chromium and LibreOffice for converting numerous document formats (HTML, Markdown, Word, Excel, etc.) into PDF files, and more!

These six modules synergize as the backbone of the ML Reports Service, empowering users to enhance and optimize Reports within the broader SunbirdEd ecosystem on the App platform.
