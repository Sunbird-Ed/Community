# 4.10.0 to 5.0.0

### Overview <a href="#overview" id="overview"></a>

This page details out the jobs required to be run as part of the upgrade from Sunbird and Vidaydaan release 4.10.0 to release 5.0.0. Use the following table to understand the jobs that need to be executed in order to successfully complete the upgrade. Any jenkins job configuration or pre-requisites mentioned under manual configuration section needs to be done first before running any of the mentioned jobs. The order of the jobs should also be run as shown below. They can be run in parallel to speed up the execution.

#### Build and Deploy for Sunbird <a href="#build-and-deploy-for-sunbird" id="build-and-deploy-for-sunbird"></a>

| Service to be Build                     | Build Tag                           | Service to Deploy                        | Deploy Tag        | Comments         |
|-----------------------------------------|-------------------------------------|------------------------------------------|-------------------|------------------|
| Build/Core/OfflineInstaller             | release-5.0.0_RC18                  | Deploy/Core/OfflineInstaller             | release-5.0.0_RC2 |                  |
| Build/Core/Assessment                   | release-5.0.0_RC1                   | Deploy/Kubernetes/Assessment             | release-5.0.0_RC2 |                  |
| Build/Core/Cert                         | release-5.0.0_RC2                   | Deploy/Kubernetes/Cert                   | release-5.0.0_RC2 |                  |
| Build/Core/CertRegistry                 | release-5.0.0_RC1                   | Deploy/Kubernetes/CertRegistry           | release-5.0.0_RC2 |                  |
| Build/Core/Content                      | release-5.0.0_RC1                   | Deploy/Kubernetes/Content                | release-5.0.0_RC2 |                  |
| Build/Core/Dial                         | release-5.0.0_RC1                   | Deploy/Kubernetes/Dial                   | release-5.0.0_RC2 |                  |
| Build/Core/DiscussionsMW                | release-5.0.0_RC2                   | Deploy/Kubernetes/DiscussionsMW          | release-5.0.0_RC2 |                  |
| Build/Core/Groups                       | release-5.0.0_RC2                   | Deploy/Kubernetes/Groups                 | release-5.0.0_RC2 |                  |
| Build/Core/Learner                      | release-5.0.0_RC2                   | Deploy/Kubernetes/Learner                | release-5.0.0_RC2 |                  |
| Build/Core/Lms                          | release-5.0.0_RC2                   | Deploy/Kubernetes/Lms                    | release-5.0.0_RC2 |                  |
| Build/Core/Nodebb                       | release-5.0.0_RC1 , nodebb: v1.18.6 | Deploy/Kubernetes/Nodebb                 | release-5.0.0_RC2 |                  |
| Build/Core/Notification                 | release-5.0.0_RC2                   | Deploy/Kubernetes/Notification           | release-5.0.0_RC2 |                  |
| Build/Core/Player                       | release-5.0.0_RC18                  | Deploy/Kubernetes/Player                 | release-5.0.0_RC2 |                  |
| Build/Core/Search                       | release-5.0.0_RC1                   | Deploy/Kubernetes/Search                 | release-5.0.0_RC2 |                  |
| Build/Core/Taxonomy                     | release-5.0.0_RC1                   | Deploy/Kubernetes/Taxonomy               | release-5.0.0_RC2 |                  |
| Build/DataPipeline/AnalyticsCore        | release-5.0.0_RC1                   | Deploy/DataPipeline/AnalyticsCore        | release-5.0.0_RC1 |                  |
| Build/DataPipeline/CoreDataProducts     | release-5.0.0_RC1                   | Deploy/DataPipeline/CoreDataProducts     | release-5.0.0_RC1 |                  |
| Build/DataPipeline/EdDataProducts       | release-5.0.0_RC2                   | Deploy/DataPipeline/EdDataProducts       | release-5.0.0_RC1 |                  |
| Build/Lern/LernDataProducts             | release-5.0.0_RC3                   | Deploy/Lern/LernDataProducts             | release-5.0.0_RC3 | New Lern BB jobs |
| Build/Lern/LernFlinkJobs                | release-5.0.0_RC4                   | Deploy/Lern/LernFlinkJobs                | release-5.0.0_RC4 | New Lern BB jobs |
| Build/KnowledgePlatform/FlinkJobs       | release-5.0.0_RC3                   | Deploy/KnowledgePlatform/FlinkJobs       | release-5.0.0_RC2 |                  |
| Build/KnowledgePlatform/Learning        | release-5.0.0_RC1                   | Deploy/KnowledgePlatform/Learning        | release-5.0.0_RC2 |                  |
| Build/KnowledgePlatform/Yarn            | release-5.0.0_RC1                   | Deploy/KnowledgePlatform/Yarn            | release-5.0.0_RC2 |                  |
| Build/managed-learn/ml-core-service     | release-5.0.0_RC6                   | Deploy/managed-learn/ml-core-service     | release-5.0.0_RC2 |                  |
| Build/managed-learn/ml-projects-service | release-5.0.0_RC5                   | Deploy/managed-learn/ml-projects-service | release-5.0.0_RC2 |                  |
| Build/managed-learn/ml-survey-service   | release-5.0.0_RC6                   | Deploy/managed-learn/ml-survey-service   | release-5.0.0_RC2 |                  |
| Build/managed-learn/ml-reports-service  | release-5.0.0_RC2                   | Deploy/managed-learn/ml-reports-service  | release-5.0.0_RC2 |                  |
|  |              | Deploy/managed-learn/ml-analytics-service   | release-5.0.0_RC7 ||
| Build/Plugins/ContentEditor             | release-5.0.0_RC1                   | Deploy/Plugins/ContentEditor             | release-5.0.0_RC2 |                  |
| Build/Plugins/ContentPlugins            | release-5.0.0_RC1                   | Deploy/Plugins/ContentPlugins            | release-5.0.0_RC2 |                  |
| Build/Plugins/GenericEditor             | release-5.0.0_RC1                   | Deploy/Plugins/GenericEditor             | release-5.0.0_RC2 |                  |
| Build/UCI/UCI                           | release-5.0.0                       | Deploy/UCI/UCI                           | release-5.0.0_RC2 |                  |
|                                         |                                     |                                          |                   |                  |
|                                         |                                     | Deploy/KnowledgePlatform/KafkaSetup      | release-5.0.0_RC2 |                  |
|                                         |                                     | Deploy/Kubernetes/Keycloak               | release-5.0.0_RC2 |                  |
|                                         |                                     | Deploy/Kubernetes/DialUploadSchema       | release-5.0.0_RC2 |                  |
|                                         |                                     | Deploy/Kubernetes/PublicDIALSchema       | release-5.0.0_RC2 |                  |
|                                         |                                     | Deploy/Sunbird-RC/Upload_RC_Schema       | release-5.0.0_RC2 |                  |

#### Manual Configurations for Sunbird <a href="#manual-configurations-for-sunbird" id="manual-configurations-for-sunbird"></a>
| Manual Step                                                                                                                                                                                                        | Instruction                                                                                                  |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------|
| Form config                                                                                                                                                                                                        | https://project-sunbird.atlassian.net/wiki/spaces/MC/pages/3222962177/Form+config+-+Program+dashboard+4.10.3 |
| Add dialcode-context-updater drop down for KnowledgePlatform/FlinkJobs                                                                                                                                             | https://github.com/project-sunbird/sunbird-devops/pull/3470                                                  |
| Create  new Jenkins jobs for Lern BB                                                                                                                                                                               | https://github.com/project-sunbird/sunbird-devops/pull/3529                                                  |
| ML-Analytics Service Manual Task                                                                                                                                                                                                       | https://docs.google.com/document/d/11iQTao4YmqWMf3LbLY7WrLqT3KjNyJhR1cdH_I4buHs/edit || 
| ML Core service: </br> 1) Take mongDB backup - "ml-survey" </br> 2) Login to ml-core service. goto migrations -> entity-generalisation-5.0 directory. | Execute scripts as mentioned in the README file inside this directory.                                                                                                        |                                                                                                            |                                  |                                                                                                                                 &                                                                                                       


