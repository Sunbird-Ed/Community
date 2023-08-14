# Component Diagram



<figure><img src="../../../../../.gitbook/assets/ML Core Service L0 (1).png" alt=""><figcaption></figcaption></figure>

The ML Core Service is constructed using a MongoDB, Kafka, and cloud storage technologies. Additionally, it seamlessly collaborates with vital services like ML Project Service, ML Survey Service, and Learner Services. This Microservice is composed of ten pivotal Modules, each playing a crucial role.

#### User Role&#x20;

This module stores essential user role information.

#### Cloud Service

It facilitates communication between ML Core and the Cloud Service for data storage and retrieval.

#### Admin

Providing administrative services within the Manage Learn Building block.

#### Users

Serving user-centric functions, including targeted programs and resources.

#### Solution

Responsible for solution creation and management.

#### Certificate Base Templates

Creating foundational certificate templates used by certificate templates and providing certificate URLs.

#### Certificate Template

Mapping certificates with solutions and associated criteria.

#### Program Users

Managing user enrollment and consent statuses.

#### Program:

Creating and managing programs.

#### User Extension

Storing user details and program-related information for program designers and managers.

These ten modules synergize as the backbone of the ML Core Service, empowering users to enhance and optimize program capabilities within the broader SunbirdEd ecosystem on the App platform.
