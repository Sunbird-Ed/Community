# SunbirdED Portal

The Sunbird portal is the browser-based interface for the Sunbird application stack. It provides a web-app through which all functionality of Sunbird can be accessed.

### Getting started

To get started with the Sunbird portal, please try out our cloud-based demo site at: [https://staging.sunbirded.org](https://staging.sunbirded.org/)

### Table of contents

* [Prerequisites](https://github.com/Sunbird-Ed/SunbirdEd-portal#prerequisites)
* [Project Setup](https://github.com/Sunbird-Ed/SunbirdEd-portal#project-setup)
* [Running Application](https://github.com/Sunbird-Ed/SunbirdEd-portal#running-application)
* [Project Structure](https://github.com/Sunbird-Ed/SunbirdEd-portal#project-structure)
* [Testing](https://github.com/Sunbird-Ed/SunbirdEd-portal#testing)

#### Prerequisites

| **System Requirements** |                                                                                                                                                                                      |
| ----------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Operating System**    | <p>MAC OS X 10.0 and above/Linux<br><br><mark style="color:red;">Windows (not verified).</mark> Take it with your own expertise(no community support but open for contribution).</p> |
| **RAM**                 | > 6 Gb                                                                                                                                                                               |
| **CPU**                 | 2 cores, >2 GHz                                                                                                                                                                      |

| Software dependencies                                            |                                                      |
| ---------------------------------------------------------------- | ---------------------------------------------------- |
| [**Node**](https://nodejs.org/en/download/)                      | > 14.x.x (Install the latest release of LTS version) |
| [**Angular CLI**](https://angular.io/cli#installing-angular-cli) | > 11.x.x (Install the latest Angular CLI version)    |
| [**yarn**](https://classic.yarnpkg.com/en/)                      | Latest version of yarn: `npm install --global yarn`  |
| [**nodemon**](https://www.npmjs.com/package/nodemon)             | Latest version of nodemon: `npm install -g nodemon`  |

#### Project Setup

1.  Clone project

    ```
    git clone https://github.com/Sunbird-Ed/SunbirdEd-portal.git
    ```

    > _**Note**_: Stable versions of the sunbird portal are available via tags for each release, and the master branch contains latest stable release. For latest stable release [refer](https://github.com/Sunbird-Ed/SunbirdEd-portal/branches)
2. Install required dependencies
   1. Sunbird portal or web application
      1. $ cd {PROJECT-FOLDER}/src/app/client
      2. $ yarn install
   2. Sunbird services stack or the backend API interface
      1. $ cd {PROJECT-FOLDER}/src/app
      2. $ yarn install
3.  Configuring the Environment and Services Stack

    > Configure the following system environment variables in the terminal which you have opened

    ```
       | Environment Variable      |  Value  | Data Type |
       | :------------------------ | ------- | --------- |
       |  sunbird_environment      | local   |   string  |
       |  sunbird_instance         | sunbird |   string  |
       |  sunbird_default_channel  | sunbird |   string  |
       |  sunbird_default_tenant   | sunbird |   string  |
    ```

    > The initialization of these environmental variables can take place in a common place like in your **.bashrc** or **.bash\_profile**
4.  Edit the Application Configuration

    > Open `<PROJECT-FOLDER>/src/app/helpers/environmentVariablesHelper.js` in any available text editor and update the contents of the file so that it contains exactly the following values

    ```
        module.exports = {
            // 1. LEARNER_URL   
            LEARNER_URL: env.sunbird_learner_player_url || <'https://<host for adopter's instance>',
            
            // 2. CONTENT_URL
            CONTENT_URL: env.sunbird_content_player_url || <'https://<host for adopter's instance>',
            
            // 3. CONTENT_PROXY  
            CONTENT_PROXY_URL: env.sunbird_content_proxy_url || <'https://<host for adopter's instance>',
            PORTAL_REALM: env.sunbird_portal_realm || 'sunbird',
            
            // 4. PORTAL_AUTH_SERVER_URL
            PORTAL_AUTH_SERVER_URL: env.sunbird_portal_auth_server_url || <'https://<host for adopter's instance>',
            PORTAL_AUTH_SERVER_CLIENT: env.sunbird_portal_auth_server_client || "portal",
            ...
            PORTAL_PORT: env.sunbird_port || 3000,
              
            // 5. PORTAL_API_AUTH_TOKEN
            PORTAL_API_AUTH_TOKEN: env.sunbird_api_auth_token || User generated API auth token
            ...
            
            // 6. PORTAL_ECHO_API_URL
            PORTAL_ECHO_API_URL: env.sunbird_echo_api_url || '',
            ...
        }
    ```

    > These are the mandatory keys required to run the application in Local environment. Please update them with appropriate values in `<PROJECT-FOLDER>/src/app/helpers/environmentVariablesHelper.js`

    ```markup
        |           Environment Variable        |  Data Type |             Description                |
        | :-------------------------------------| ---------- | -------------------------------------  |
        |        sunbird_azure_account_name     |   string   |          Azure account Name            |
        |        sunbird_azure_account_key      |   string   |          Azure Account Key             |
        |          sunbird_aws_region           |   string   |        Region for AWS account          |
        |  KONG_DEVICE_REGISTER_ANONYMOUS_TOKEN |   boolean  |   Flag value to allow anonymous user   |
        |  sunbird_anonymous_device_register_api|   string   |The API for registering anonymous device|
        |  sunbird_anonymous_register_token     |   string   |    Token to register anonymous device  |
        |               SB_DOMAIN               |   string   |    The host for Sunbird Environment    |
        |         PORTAL_API_AUTH_TOKEN         |   string   |     User generated API auth token      |
    ```

    > Once the file is updated with appropriate values, then you can proceed with running the application

#### Running Application

1. Sunbird portal or web application
   1. Run the following command in the **{PROJECT-FOLDER}/src/app/client** folder
   2. $ ng build --watch=true
   3. Wait for the build process to complete before proceeding to the next step
2. Sunbird services stack or the backend API interface
   1. Run the following command in the **{PROJECT-FOLDER}/src/app** folder
   2. $ npm run server
3. The local HTTP server is launched at `http://localhost:3000`

#### Project Structure

```
.
├── Sunbirded-portal                                            
|   ├── /.circleci                           # 
│   |   └── config.yml                       # Circleci Configuration file
|   ├── /experiments                         # -|-
|   ├── /src/app                             # Sunbird portal or web application
│   |   ├── /client                          # -|-
│   |   |    └── src                         # -|-
│   |   ├── /helpers                         # Helpers and Service file
│   |   ├── /libs                            # Sunbird utilities
│   |   ├── /proxy                           # Redirection to respective services
│   |   ├── /resourcebundles                 # Language resources
│   |   ├── /routes                          # Sunbird Backend Routes
│   |   ├── /sunbird-plugins                 # Sunbird plugins for editors
│   |   ├── /tests                           # Test case scripts for helpers and routes
│   |   ├── framework.config.js              # Default framework configuration
│   |   ├── gulp-tenant.js                   # -|-
│   |   ├── gulpfile.js                      # Gulp build configuration
│   |   ├── package.json                     # Contains Node packages as specified as dependencies in package.json
│   |   └── server.js                        # Main application program file / entry file for Sunbird services stack or the backend API interface
└───└── .gitignore                           # git configuration to ignore some files and folder
```

#### Testing

1.  Sunbird portal or web application

    ```
     1. $ cd {PROJECT-FOLDER}/src/app/client
     2. $ npm run test
     3. With Coverage $ npm run test-coverage
    ```
2.  Sunbird services stack or the backend API interface

    ```
     1. $ cd {PROJECT-FOLDER}/src/app
     2. $ npm run backend-test
     3. With Coverage $ npm run backend-test-with-coverage
    ```
