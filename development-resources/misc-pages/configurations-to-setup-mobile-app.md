# Configurations to setup mobile app

### sunbird.properties

<mark style="color:blue;">**sunbird.properties**</mark> file contains all the necessary configurations to set up Sunbird mobile app. The following are the configurations inside the <mark style="color:blue;">**sunbird.properties**</mark> file.

#### Note

The properties can be environment-specific so the naming convention is \<env\_name>_\<property\__name>. For example, suppose **base\_url** is the property so its dev environment-specific property name is **dev\_base\_url,** and the staging environment-specific property name is **staging\_base\_url.**

| Property name             | Description                                                                                                                                                    |
| ------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| app\_name                 | Name of the app/instance                                                                                                                                       |
| app\_version\_code        | Version code should be incremented every time a build is uploaded to Play Store.                                                                               |
| app\_id                   | A unique application id that identifies the app.Env specific properties dev\_app\_id, staging\_app\_id                                                         |
| base\_url                 | Base URL of the instance(shouldn't contain "/" at the end). Env specific properties dev\_base\_url, staging\_base\_url                                         |
| producer\_id              | Unique id used to show the origin(app/portal/desktop) of telemetry.Env specific properties dev\_producer\_id, staging\_producer\_id                            |
| channel\_id               | Default channel id.Env specific properties dev\_channel\_id, staging\_channel\_id                                                                              |
| mobile\_app\_key          | The credentials required for API calls( will be provided by the DevOps team).Env specific properties dev\_mobile\_app\_key, staging\_mobile\_app\_key.         |
| mobile\_app\_secret       | The credentials required for API calls (will be provided by the DevOps team.).Env specific properties dev\_mobile\_app\_secret, staging\_mobile\_app\_secret   |
| deeplink\_base\_url       | Base URL used to support deep linking in the app.Env specific properties dev\_deeplink\_base\_url, staging\_deeplink\_base\_url                                |
| support\_email            | Email address of customer support where users can email their queries about the app.                                                                           |
| custom\_scheme            | Custom scheme to support browser-based google login.Env specific properties dev\_custom\_scheme, staging\_custom\_scheme                                       |
| merge\_account\_base\_url | Base URL of merge account feature(shouldn't contain "/" at the end).Env specific properties dev\_merge\_account\_base\_url, staging\_merge\_account\_base\_url |
| oauth\_redirect\_url      | Redirect URL to support browser-based google login.Env specific properties dev\_oauth\_redirect\_url, staging\_oauth\_redirect\_url                            |
| tou\_base\_url            | Terms of use baseurl.Env specific properties dev\_tou\_base\_url, staging\_tou\_base\_url                                                                      |
| survey\_base\_url         | Survey feature base URL(Manage Learn Usecase).Env specific properties dev\_survey\_base\_url, staging\_survey\_base\_url                                       |
| projects\_base\_url       | Project feature base URL(Manage Learn Usecase).Env specific properties dev\_projects\_base\_url, staging\_projects\_.base\_url                                 |

