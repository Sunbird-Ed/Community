# Sunbird Mobile



### Introduction <a href="#introduction" id="introduction"></a>

The Sunbird Mobile app provides mobility to its feature-rich learning platform. It provides learners with the flexibility to learn anywhere, anytime.

### Prerequisites <a href="#prerequisites" id="prerequisites"></a>

\
1.To set up Sunbird mobile app, ensure you have installed the following:\
 a) NPM Version - 6.+\
 b) Node JS Version - 8.+\
 c) Cordova Version - 8.+\
 d) Ionic Version - 4.11.2\
2\. Generate the key and secret for the mobile app user using the JWT token of the mobile admin user. Run the **OnboardConsumers** Jenkins Job and take the jwt token(**JWT token for mobile\_admin**) from Jenkins Output.

**Generating Secret:** Execute the listed API to generate the key and secret for the mobile app:

curl -X POST \ \<your-sunbird-base-url>/api/api-manager/v1/consumer/mobile\_app/credential/register \ -H ‘authorization: Bearer \<mobile\_admin\_jwt\_token\_from\_jenkins\_job\_output>’ \ -H ‘content-type: application/json’ \ -d ‘{ “request”: { “key”: “\<implementation-name>-mobile-app- \<version-number>” } }’

**Response body:**

{“result”:{“key”:”\<implementation-name>-mobile-app-\<version-number>”,”secret”:”\<secret>”\}}

Use the key and secret from the response given for MOBILE\_APP\_KEY and MOBILE\_APP\_SECRET configuration in respective environments in gradle.properties file. Example:

**dev\_mobile\_app\_key = “\<implementation-name>-mobile-app-\<version-number>” dev\_mobile\_app\_secret = “\<secret>“**

**Producer Key**

Replace the producer id `PRODUCER_ID` for respective environments in sunbird.properties.

**Fabric credentials:**

Replace `release_fabric_api_key` in `sunbird.properties` with your fabric API Key. Create an account in [fabric.io](https://get.fabric.io/) and register in the app to get the API key.

### Set up mobile app workspace from Git Repository <a href="#set-up-mobile-app-workspace-from-git-repository" id="set-up-mobile-app-workspace-from-git-repository"></a>

Sunbird mobile app can be built from the main source code which is available at [SunbirdEd-mobile-app](https://github.com/Sunbird-Ed/SunbirdEd-mobile-app).

* Clone the [SunbirdEd-mobile-app](https://github.com/Sunbird-Ed/SunbirdEd-mobile-app) repo
* [Customising App Configuration](http://docs.sunbird.org/latest/#customising-app-configuration) - sample.sunbird.properties file is located inside SunbirdEd-mobile-app > buildConfig folder. This has to be renamed to sunbird.properties and appropriate values should be provided.
* [Package the framework and form data](http://docs.sunbird.org/latest/#package-the-framework-and-form-data).
* go to project folder and run **./build.sh**

#### Customising App Configuration <a href="#customising-app-configuration" id="customising-app-configuration"></a>

Instance admin of Sunbird adopters can configure various aspects of the Sunbird mobile app based on the requirement of the the organization. The admin are able to configure various aspects such as:

* App name
* App logo
* Login/Guest page to new users
* Sign in footer card on the app
* Onboarding cards
* Categories in the profile page

| S NO. | VARIABLE NAME                                                          | DESCRIPTION                                                                                                                                                        | PURPOSE                                                                                                                                                                                                    | DEFAULT VALUE                                                                                                                |
| ----- | ---------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| 1     | dev\_app\_id/staging\_app\_id/production\_app\_id                      | The app ID in the **SunbirdEd-mobile-app/buildConfig/sunbird.properties** file with the implementation-specific application ID                                     | To change the app ID                                                                                                                                                                                       | appId: “org.sunbird.app”                                                                                                     |
| 2     | app name                                                               | Navigate to the **SunbirdEd-mobile-app/config.xml** file and enter the required app name                                                                           | To change the app name                                                                                                                                                                                     |                                                                                                                              |
| 3     | app logo                                                               | Navigate to **SunbirdEd-mobile-app/resources/android/icon**                                                                                                        | Replace the **ic\_launcher.png** image with your desired logo in all the mipmap and drawable folders. The logo name should be **drawable-ldpi-icon.png**                                                   | To change the app logo                                                                                                       |
| 4     | splash image                                                           | Navigate to **SunbirdEd-mobile-app/resources/android/splash**                                                                                                      | Replace the **drawable-ldpi-icon.png, drawable-hdpi-icon.png, drawable-xhdpi-icon.png** image with your desired image.                                                                                     | To change the splash image                                                                                                   |
| 5     | app                                                                    | Set the configuration variable in the **SunbirdEd-mobile-app repo** file in the **buildConfig** folder                                                             |                                                                                                                                                                                                            |                                                                                                                              |
| 6     | app version code                                                       | Version code for the app release                                                                                                                                   | To customize the end points in the app                                                                                                                                                                     | Replace redirect base url REDIRECT\_BASE\_URL and all other base urls with your respective domain name in sunbird.properties |
| 7     | deep link schema                                                       | This plugin handles deeplinks on iOS and Android for both custom URL scheme links and Universal App Links. Deep link schema can be changed from sunbird.properties | Change the “dev\_deeplink\_base\_url = dev.open-sunbird.org” to the required name                                                                                                                          |                                                                                                                              |
| 8     | display\_onboarding\_page                                              | set the configuration variable inside the **SunbirdEd-mobile-app repo** inside **buildConfig** folder                                                              | to display the onboarding page                                                                                                                                                                             | false                                                                                                                        |
| 9     | display\_signin\_footer\_card\_in\_course\_tab\_for\_teacher           | set the **display\_signin\_footer\_card\_in\_course\_tab\_for\_teacher**variable as **true** in sunbird.properties file                                            | to show the sign-in footer in the course tab for teachers                                                                                                                                                  | false                                                                                                                        |
| 10    | display\_signin\_footer\_card\_in\_library\_tab\_for\_teacher          | Set the **display\_signin\_footer\_card\_in\_library\_tab\_for\_teacher** variable **true** in sunbird.properties file                                             | to show the sign-in footer in the library tab for teachers                                                                                                                                                 | false                                                                                                                        |
| 11    | display\_signin\_footer\_card\_in\_profile\_tab\_for\_teacher          | Set the **display\_signin\_footer\_card\_in\_profile\_tab\_for\_teacher**as **true** in sunbird.properties file                                                    | to show the sign-in footer in the profile tab for teachers                                                                                                                                                 | false                                                                                                                        |
| 12    | display\_signin\_footer\_card\_in\_profile\_tab\_for\_student          | Set the **display\_signin\_footer\_card\_in\_profile\_tab\_for\_student**as **true** in sunbird.properties file                                                    | to show the sign-in footer in the profile tab for students                                                                                                                                                 | false                                                                                                                        |
| 13    | display\_signin\_footer\_card\_in\_library\_tab\_for\_student          | Set the **display\_signin\_footer\_card\_in\_library\_tab\_for\_student**as **true** in sunbird.properties file                                                    | to show the sign-in footer in the profile tab for students                                                                                                                                                 | false                                                                                                                        |
| 14    | display\_onboarding\_card                                              | set the display\_\_onboarding\_cards as true in sunbird.properties file                                                                                            | to display the guest/login page                                                                                                                                                                            | false                                                                                                                        |
| 15    | display\_framework\_categories\_in\_profile                            | set the display\_framework\_categories\_in\_profile variable as true in sunbird.properties file                                                                    | to display categories in the guest/login page                                                                                                                                                              | false                                                                                                                        |
| 16    | track\_user\_telemetry                                                 | Variable used to track user telemetry.                                                                                                                             | Used to track telemetry that is missing at the device level so as to generate greater usage context within the instance. Set the variable as _true_ in the **sunbird.properties** file to enable tracking. | false                                                                                                                        |
| 17    | content\_streaming\_enabled                                            | Variable used to enable content streaming                                                                                                                          | Used to enable content streaming. Set the variable as _true_ in the **sunbird.properties** file to enable content streaming                                                                                | false                                                                                                                        |
| 18    | open\_rapdiscovery\_enabled                                            | Variable used to enable OPENRAP discovery                                                                                                                          | Used to enable OPENRAP discovery. Set the variable as _true_ in the **sunbird.properties** file to enable OPENRAP discovery                                                                                | false                                                                                                                        |
| 19    | display\_onboarding\_category\_page                                    | Variable used to enable onboarding category selection page                                                                                                         | Used to onboarding category selection page in the onboarding process. Set the variable as _true_ in the **sunbird.properties** file to enable onboarding category selection page.                          | false                                                                                                                        |
| 20    | display\_onboarding\_scan\_page                                        | Variable used to enable onboarding scan page.                                                                                                                      | Used to enable onboarding scan page in the onboarding process. Set the variable as _true_ in the **sunbird.properties** file to onboarding scan page                                                       | false                                                                                                                        |
| 21    | support\_email                                                         | Variable used to set                                                                                                                                               | Used to set the support email id. Set the variable as _\<valid\_email\_id>_ in the **sunbird.properties** file to set support email id                                                                     | \<valid\_email\_id>                                                                                                          |
| 22    | dev\_custom\_scheme/staging\_custom\_scheme/production\_custom\_scheme | Scheme used to redrirect chrome custom tab back to mobile app                                                                                                      |                                                                                                                                                                                                            | “org.sunbird.app”                                                                                                            |

#### Packaging Framework and Form Data <a href="#packaging-framework-and-form-data" id="packaging-framework-and-form-data"></a>

Sunbird mobile app supports configuration of the app framework to enable offline usage of the app. To configure the app framework, adopter needs to package the channel for the respective framework. Details of the file naming convention and folder location are given below:

| S NO. | FOLDER                              | FILE NAME                               | PURPOSE                                                                                                                     |
| ----- | ----------------------------------- | --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| 1     | buildConfig/data/framework          | framework-\<FRAMEWORK\_IDENTIFIER<.json | To package the channel for the respective framework. Same framework must be listed in the channel’s suggestedFramework list |
| 2     | buildConfig/data/channel            | channel-\<CHANNEL\_IDENTIFIER>.json     | To package the channel. To support offline usage custodianOrgId channel must be included in the bundle                      |
| 3     | buildConfig/data/form               | pageassemble\_course\_filter.json       | Page assemble filter for course                                                                                             |
| 4     | buildConfig/data/form               | pageassemble\_library\_filter.json      | Page assemble filter for library                                                                                            |
| 5     | buildConfig/data/system             | \<system-setting-custodianOrgId>.json   | custodianOrgId channelid for the mobile app                                                                                 |
| 6     | buildConfig/data/system             | system-setting-courseFrameworkId.json   | courseFrameworkId for the TPD workflow                                                                                      |
| 7     | buildConfig/data/notificationconfig | local\_notofocation\_config.json        | Configuration for local Notification setup in mobile                                                                        |

#### Installing the Mobile Application <a href="#installing-the-mobile-application" id="installing-the-mobile-application"></a>

1.Create a workspace (Folder Hierarchy) and clone the Git repositories into this folder

2.Execute the instructions mentioned for each cloned repository

3.Open terminal and change the directory to “SunbirdEd-mobile-app”

4.Add one device to the system

5.Run the command- **$ ionic cordova run android**

#### Generate Multiple Sunbird Apps <a href="#generate-multiple-sunbird-apps" id="generate-multiple-sunbird-apps"></a>

As a Sunbird instance owner, owner should be able to generate multiple apps for multiple environments(dev/qa/production) so that user can use all the apps simultaneously. For each app, user should be able to have different content stores (on the local device), fire telemetry from separate app identifiers and upload to playstore (if need be).

**Configuration**

Instance admin of Sunbird adopters can configure the appId in the following way to acheive the functionality

* dev\_app\_id = org.sample.app.dev
* staging\_app\_id = org.sample.app.staging
* production\_app\_id = org.sample.app
