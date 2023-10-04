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

<table><thead><tr><th width="150">S NO.</th><th>VARIABLE NAME</th><th>DESCRIPTION</th><th>PURPOSE</th><th>DEFAULT VALUE</th></tr></thead><tbody><tr><td>1</td><td>dev_app_id/staging_app_id/production_app_id</td><td>The app ID in the <strong>SunbirdEd-mobile-app/buildConfig/sunbird.properties</strong> file with the implementation-specific application ID</td><td>To change the app ID</td><td>appId: “org.sunbird.app”</td></tr><tr><td>2</td><td>app name</td><td>Navigate to the <strong>SunbirdEd-mobile-app/config.xml</strong> file and enter the required app name</td><td>To change the app name</td><td></td></tr><tr><td>3</td><td>app logo</td><td>Navigate to <strong>SunbirdEd-mobile-app/resources/android/icon</strong></td><td>Replace the <strong>ic_launcher.png</strong> image with your desired logo in all the mipmap and drawable folders. The logo name should be <strong>drawable-ldpi-icon.png</strong></td><td>To change the app logo</td></tr><tr><td>4</td><td>splash image</td><td>Navigate to <strong>SunbirdEd-mobile-app/resources/android/splash</strong></td><td>Replace the <strong>drawable-ldpi-icon.png, drawable-hdpi-icon.png, drawable-xhdpi-icon.png</strong> image with your desired image.</td><td>To change the splash image</td></tr><tr><td>5</td><td>app</td><td>Set the configuration variable in the <strong>SunbirdEd-mobile-app repo</strong> file in the <strong>buildConfig</strong> folder</td><td></td><td></td></tr><tr><td>6</td><td>app version code</td><td>Version code for the app release</td><td>To customize the end points in the app</td><td>Replace redirect base url REDIRECT_BASE_URL and all other base urls with your respective domain name in sunbird.properties</td></tr><tr><td>7</td><td>deep link schema</td><td>This plugin handles deeplinks on iOS and Android for both custom URL scheme links and Universal App Links. Deep link schema can be changed from sunbird.properties</td><td>Change the “dev_deeplink_base_url = dev.open-sunbird.org” to the required name</td><td></td></tr><tr><td>8</td><td>display_onboarding_page</td><td>set the configuration variable inside the <strong>SunbirdEd-mobile-app repo</strong> inside <strong>buildConfig</strong> folder</td><td>to display the onboarding page</td><td>false</td></tr><tr><td>9</td><td>display_signin_footer_card_in_course_tab_for_teacher</td><td>set the <strong>display_signin_footer_card_in_course_tab_for_teacher</strong>variable as <strong>true</strong> in sunbird.properties file</td><td>to show the sign-in footer in the course tab for teachers</td><td>false</td></tr><tr><td>10</td><td>display_signin_footer_card_in_library_tab_for_teacher</td><td>Set the <strong>display_signin_footer_card_in_library_tab_for_teacher</strong> variable <strong>true</strong> in sunbird.properties file</td><td>to show the sign-in footer in the library tab for teachers</td><td>false</td></tr><tr><td>11</td><td>display_signin_footer_card_in_profile_tab_for_teacher</td><td>Set the <strong>display_signin_footer_card_in_profile_tab_for_teacher</strong>as <strong>true</strong> in sunbird.properties file</td><td>to show the sign-in footer in the profile tab for teachers</td><td>false</td></tr><tr><td>12</td><td>display_signin_footer_card_in_profile_tab_for_student</td><td>Set the <strong>display_signin_footer_card_in_profile_tab_for_student</strong>as <strong>true</strong> in sunbird.properties file</td><td>to show the sign-in footer in the profile tab for students</td><td>false</td></tr><tr><td>13</td><td>display_signin_footer_card_in_library_tab_for_student</td><td>Set the <strong>display_signin_footer_card_in_library_tab_for_student</strong>as <strong>true</strong> in sunbird.properties file</td><td>to show the sign-in footer in the profile tab for students</td><td>false</td></tr><tr><td>14</td><td>display_onboarding_card</td><td>set the display__onboarding_cards as true in sunbird.properties file</td><td>to display the guest/login page</td><td>false</td></tr><tr><td>15</td><td>display_framework_categories_in_profile</td><td>set the display_framework_categories_in_profile variable as true in sunbird.properties file</td><td>to display categories in the guest/login page</td><td>false</td></tr><tr><td>16</td><td>track_user_telemetry</td><td>Variable used to track user telemetry.</td><td>Used to track telemetry that is missing at the device level so as to generate greater usage context within the instance. Set the variable as <em>true</em> in the <strong>sunbird.properties</strong> file to enable tracking.</td><td>false</td></tr><tr><td>17</td><td>content_streaming_enabled</td><td>Variable used to enable content streaming</td><td>Used to enable content streaming. Set the variable as <em>true</em> in the <strong>sunbird.properties</strong> file to enable content streaming</td><td>false</td></tr><tr><td>18</td><td>open_rapdiscovery_enabled</td><td>Variable used to enable OPENRAP discovery</td><td>Used to enable OPENRAP discovery. Set the variable as <em>true</em> in the <strong>sunbird.properties</strong> file to enable OPENRAP discovery</td><td>false</td></tr><tr><td>19</td><td>display_onboarding_category_page</td><td>Variable used to enable onboarding category selection page</td><td>Used to onboarding category selection page in the onboarding process. Set the variable as <em>true</em> in the <strong>sunbird.properties</strong> file to enable onboarding category selection page.</td><td>false</td></tr><tr><td>20</td><td>display_onboarding_scan_page</td><td>Variable used to enable onboarding scan page.</td><td>Used to enable onboarding scan page in the onboarding process. Set the variable as <em>true</em> in the <strong>sunbird.properties</strong> file to onboarding scan page</td><td>false</td></tr><tr><td>21</td><td>support_email</td><td>Variable used to set</td><td>Used to set the support email id. Set the variable as <em>&#x3C;valid_email_id></em> in the <strong>sunbird.properties</strong> file to set support email id</td><td>&#x3C;valid_email_id></td></tr><tr><td>22</td><td>dev_custom_scheme/staging_custom_scheme/production_custom_scheme</td><td>Scheme used to redrirect chrome custom tab back to mobile app</td><td></td><td>“org.sunbird.app”</td></tr></tbody></table>

#### Packaging Framework and Form Data <a href="#packaging-framework-and-form-data" id="packaging-framework-and-form-data"></a>

Sunbird mobile app supports configuration of the app framework to enable offline usage of the app. To configure the app framework, adopter needs to package the channel for the respective framework. Details of the file naming convention and folder location are given below:

<table><thead><tr><th width="150">S NO.</th><th>FOLDER</th><th>FILE NAME</th><th>PURPOSE</th></tr></thead><tbody><tr><td>1</td><td>buildConfig/data/framework</td><td>framework-&#x3C;FRAMEWORK_IDENTIFIER&#x3C;.json</td><td>To package the channel for the respective framework. Same framework must be listed in the channel’s suggestedFramework list</td></tr><tr><td>2</td><td>buildConfig/data/channel</td><td>channel-&#x3C;CHANNEL_IDENTIFIER>.json</td><td>To package the channel. To support offline usage custodianOrgId channel must be included in the bundle</td></tr><tr><td>3</td><td>buildConfig/data/form</td><td>pageassemble_course_filter.json</td><td>Page assemble filter for course</td></tr><tr><td>4</td><td>buildConfig/data/form</td><td>pageassemble_library_filter.json</td><td>Page assemble filter for library</td></tr><tr><td>5</td><td>buildConfig/data/system</td><td>&#x3C;system-setting-custodianOrgId>.json</td><td>custodianOrgId channelid for the mobile app</td></tr><tr><td>6</td><td>buildConfig/data/system</td><td>system-setting-courseFrameworkId.json</td><td>courseFrameworkId for the TPD workflow</td></tr><tr><td>7</td><td>buildConfig/data/notificationconfig</td><td>local_notofocation_config.json</td><td>Configuration for local Notification setup in mobile</td></tr></tbody></table>

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
