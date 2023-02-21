---
description: Minimal build properties
---

# Misc Pages

To ensure the sunbird is easily adopted by different adapters, it is important to understand the minimal build properties required. In this article, we will delve into these requirements and explore the key factors that play a role in ensuring a seamless integration of sunbird.

\


The minimal build properties include the following,

```properties
//App specific Properties
staging_app_id = org.sunbird.app.staging
app_name = Sunbird
app_version_code = 1

// Staging environment properties.
staging_base_url = https://staging.sunbirded.org
staging_device_register_base_url= https://apistaging.ntp.net.in
staging_mobile_app_key = <app-key>
staging_mobile_app_secret = <app-secret>
staging_deeplink_base_url = staging.sunbirded.org

support_email = dummy@example.com

```

The sunbird.properties file contains various properties that are used to configure the app for different environments (dev, staging, and production). For the minimal properties, we are considering only a staging environment as of now.

The properties include details such as the app's ID, version code, and name. It also contains properties specific to each environment, such as the base URL, mobile app key and secret, channel ID, producer ID, deep link URLs, OAuth redirect URL, etc.



It also contains properties for Fabric keys, which are used for crash reporting and analytics in the mobile app.\


Additionally, it contains some properties for displaying specific information in the app, such as displaying framework categories in the profile, and sign-in footer cards in different tabs for teachers and students.

These properties are set to default values and these values will be replaced with actual values by the developer or dev-ops team before the app is deployed to each environment.

\
