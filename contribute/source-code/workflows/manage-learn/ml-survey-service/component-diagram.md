# Component Diagram



<figure><img src="../../../../../.gitbook/assets/ML Survey Service L0.png" alt=""><figcaption><p>ML Survey Service Component Diagram</p></figcaption></figure>

The [ML Survey Service](../ml-survey-service.md) is constructed using MongoDB, Kafka, and cloud storage technologies. Additionally, it seamlessly collaborates with vital services like [ML Project Service](../ml-project-service.md), [ML Core Service](../ml-core-service.md), and [Learner Services](https://lern.sunbird.org/learn/readme). This Microservice comprises ten pivotal Modules, each playing a crucial role.

#### Reports

In charge of acquiring data for reports.

#### Survey

Tasked with creating surveys using solutions and templates.

#### Survey Submission

Handles the submission of surveys and sends data to Kafka for analytical purposes.

#### Assessment

Responsible for validating assessments of criteria and questions in observations and surveys.

#### Solutions

Offers available solutions within the Manage Learn system.

#### Observations

Generates observations from solutions for users engaged in observations.

#### Observation Submissions

Manages the submission of observations and forwards data to Kafka for analytical purposes.

#### Scoring

This module will be used by observations that involve rubric-based scoring.

#### User Extensions

Storing user details and program-related information for program designers and managers.

#### Programs

Supplies a list of available programs within Manage Learn.

####

These ten modules synergize as the backbone of the [ML Survey Service](../ml-survey-service.md), empowering users to enhance and optimize Observation and Survey capabilities within the broader SunbirdEd ecosystem on the App platform.
