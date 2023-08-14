# Service Setup Guide

### Pre-requisites

* All resources under Introduction to Manage Learn Category
* NodeJS
* Druid

### Clone the service repository onto your system

* Create a new folder where you want to clone the repository.
* Navigate to that directory using the terminal.
* Execute the git commands to clone the repository using the provided link from the code tab.

Git link

{% embed url="https://github.com/shikshalokam/ml-reports-service.git" %}

```
https://github.com/shikshalokam/ml-reports-service.git
```

command to clone



```
git clone https://github.com/shikshalokam/ml-reports-service.git
```

### Create .env file

Create a file named `.env` and copy the environment-specific data corresponding to that service into the `.env` file.

```
# Environment configurations file
APPLICATION_PORT = "3000"                                                 // Application port number
APPLICATION_ENV = "development"                                           // Application running enviornment

INTERNAL_ACCESS_TOKEN = "Fg*************yr"                               // Internal access token for accessing internal service APIs

#Druid configuration
DRUID_URL = "http://localhost:9042"                                       // Druid connection url
OBSERVATION_DATASOURCE_NAME = "OBSERVATION_DATASOURCE_NAME"               // Observation data source name
OBSERVATION_EVIDENCE_DATASOURCE_NAME = "EVIDENCE_DATASOURCE_NAME"         // Observation evidences data source name
SURVEY_DATASOURCE_NAME = "SURVEY_DATASOURCE_NAME"                         // Survey data source name
SURVEY_EVIDENCE_DATASOURCE_NAME = "SURVEY_EVIDENCE_DATASOURCE_NAME"       // Survey evidence data source name
PROJECT_RESOURCE_DATASOURCE_NAME = "PROJECT_RESOURCE_DATASOURCE_NAME"            // Project resource data source name
OBSERVATION_RESOURCE_DATASOURCE_NAME = "OBSERVATION_RESOURCE_DATASOURCE_NAME"    // Observation resource data source name
SURVEY_RESOURCE_DATASOURCE_NAME = "SURVEY_RESOURCE_DATASOURCE_NAME"              // Survey resource data source name
PROGRAM_RESOURCE_DATASOURCE_NAME = "PROGRAM_RESOURCE_DATASOURCE_NAME"     // Program resource data source name
CONTENT_REPORT_THRESHOLD = 5                                              // Restrict number of records to be shown for container reports
ENTITY_SCORE_REPORT_THRESHOLD = 5                                         // Restrict number of submission for entity score report
OBSERVATION_SCORE_REPORT_THRESHOLD = 2                                    // Restrict number of submission per entity in observation report
EVIDENCE_THRESHOLD = 3                                                    // Restrict number of evidence per questions

#Gotenberg configuration
GOTENBERG_URL = "http://localhost:3000"                                   // Gotenberg service URL

# ML Survey Service
ML_SURVEY_SERVICE_URL = "http://ml-survey-service:3000"                   // ML survey service URL

# ML Core  Service
ML_CORE_SERVICE_URL = "http://ml-core-service:3000"                       // ML Core Service URL

# OFFLINE TOKEN VALIDATION
KEYCLOAK_PUBLIC_KEY_PATH = "keycloak-public-keys"                         // Keycloak public keys path
```

### Install Dependencies

To install dependencies from a `package.json` file in Visual Studio Code, you can use the integrated terminal. Here are the steps:

* Open the integrated terminal by going to View > Terminal or using the shortcut Ctrl+\` (backtick).
* In the terminal, navigate to the directory where the package.json file is located.
* Run the command `npm install` or `yarn install`, depending on your preferred package manager.
* The package manager will read the package.json file and install all the dependencies specified in it.
* Wait for the installation process to complete. You should see progress indicators or a success message for each installed dependency.
* Once the installation is finished, the dependencies listed in the package.json file will be installed in a node\_modules directory in your project.

### Setting the keycloak

* Create a folder on service directory named: `keycloak-public-keys`
* Inside that folder create a file `GRxxx....................xxxxx60fA`

**for keycloak file please contact Backend Team**

### Setup Database

The Reports service will communicate with the ML Core and ML Survey services to retrieve data from MongoDB for generating reports and analytics. Additionally, it will interact with Druid for the reporting and analytics functionalities.

####
