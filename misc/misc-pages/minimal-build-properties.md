# Minimal build properties

To ensure different adapters easily adopt the sunbird, it is important to understand the minimal build properties required. In this article, we will delve into these requirements and explore the key factors that play a role in ensuring a seamless integration of sunbird.&#x20;

The mandatory build properties include the following,&#x20;

```
//App-specific Properties
staging_app_id = org.sunbird.app.staging
app_name = Sunbird
app_version_code = 1

// Staging environment properties.
staging_base_url = https://staging.sunbirded.org
staging_device_register_base_url= https://apistaging.ntp.net.in
staging_mobile_app_key = sunbird-0.1
staging_mobile_app_secret = c0MsZyjLdKYMz255KKRvP0TxVbkeNFlx
staging_deeplink_base_url = staging.sunbirded.org

// Fabric Keys
release_fabric_api_key = 4a735dc3520070ad4ea3339e4d8d2bb00efe8eaa
release_fabric_api_secret = a98a1c7293881445c6e471588c3adaaef3814c89bdf26b4c1393196162ba9e1c

support_email = dummy@example.com
```

Optional build properties include the following,

```

// Staging environment properties.
staging_channel_id = 505c7c48ac6dc1edc9b08f21db5a571d
staging_producer_id = staging.diksha.app
staging_merge_account_base_url= https://merge.staging.ntp.net.in
staging_deeplink_ncert_url = epathshala.nic.in
staging_deeplink_igot_url = igot.gov.in
staging_tou_base_url = https://static.preprod.ntp.net.in
staging_survey_base_url= https://google.com/
staging_projects_base_url = https://google.com
```

The sunbird.properties file contains various properties that are used to configure the app for different environments (dev, staging, and production). For the minimal properties, we are considering only a staging environment as of now.

The properties include the app's ID, version code, and name. It also contains properties specific to the staging environment, such as the base URL, mobile app key and secret, channel ID, producer ID, deep link URLs, OAuth redirect URL, etc.

It also contains properties for Fabric keys, which are used for crash reporting and analytics in the mobile app.

These properties are set to default values and will be replaced with actual values by the developer or dev-ops team before the app is deployed to each environment.
