---
description: >-
  This document explains how users can configure the branding name and logo for
  their Sunbird application using the sunbird_tenant_cdn_url .
---

# Branding Name and Logo Configuration Guide

The configuration allows customization of various branding assets such as logos, app logos, favicons, and posters.

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXcy6RDfJ4MuU2k3VNPAWa1gdZ-y-Ij9dCef5mivTxff_jIjvXdvVYcdAdnItYysYRenixORi9rhA2Hnb6SJ-BaHxLrv3cMr1wSp-yaTrDAXxO5bN60eoO6i97ymUEk9nDkOHRL3tQ?key=6ZxLi1rtEkXdLe4tCZWjbGAg" alt=""><figcaption><p>i. Brand Logo</p></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdv0bg4SfYkzp2p1OzbYbhnINnuHxELd7nrXjHKEu-SDx4m7bp2Hyik6nwqCgrFIZa69djeVf2HRTW_Btl6-AeK2-PXuvo21SAELsFSZ8S9WCGfb3wQaEX_5wq9oAz8a__XNIq3MA?key=6ZxLi1rtEkXdLe4tCZWjbGAg" alt=""><figcaption><p>ii) Brand favicon</p></figcaption></figure>

<figure><img src="https://lh7-rt.googleusercontent.com/docsz/AD_4nXdGL1m8wuy0qCfvmUUNTexAx9KYOK6sLz-TNkr4HE9yLmE_rlhJ6RKSnT4V5owFd1jL_sNeR-ahtRKcKN0aPsoUmzNDPWOgQgLmEVct4GXWfTX5B6rILDwneQ6XF0-yErHKUxqn?key=6ZxLi1rtEkXdLe4tCZWjbGAg" alt=""><figcaption><p>iii) Poster</p></figcaption></figure>

***

### Configuration overview

The branding assets are served through a Content Delivery Network (CDN) and follow a specific URL structure. The assets must be stored under a tenant directory with predefined image names. If no custom branding is provided, default branding assets for Sunbird will be used.

The CDN URL must follow the structure: `sunbird_tenant_cdn_url/tenant_id/image_name`

Example:[`http://sunbirded/NCF/logo.png`](http://sunbirded/NCF/logo.png)

Here:

* _sunbird\_tenant\_cdn\_url_: The base URL of the CDN (e.g., \`http://sunbirded\`).
* _tenant\_id_: The tenant identifier (e.g., \`NCF\`). Configured as sunbird\_default\_channel
* _image\_name_: The predefined name of the branding asset (e.g., \`logo.png\`).

***

### Predefined Image Names

To properly configure branding, the following image names must be used:

| **Asset** | **Image Name** | **Description**                                            |
| --------- | -------------- | ---------------------------------------------------------- |
| Logo      | logo.png       | The primary logo displayed on the application.             |
| App Logo  | appLogo.png    | The logo specifically used for the mobile app              |
| Favicon   | favicon.ico    | The small icon displayed in the browser tab or address bar |
| Poster    | poster.png     | A poster image for informational displays \[Optional]      |

### Default Branding

If no custom branding is provided, the application will fall back to the default Sunbird branding. The default branding assets include:

* Logo: A generic Sunbird logo.
* App Logo: Same as the default Sunbird logo for mobile application.
* Favicon: A Sunbird-themed favicon.
* Poster: A default poster image for Sunbird.

***

### Steps to Configure Branding

1. **Prepare the Branding Assets:**
   1. Ensure that the images are in the correct formats:
      1. logo.png and appLogo.png: PNG format.
      2. favicon.ico: ICO format.
      3. poster.png: PNG format.
   2. Use the exact file names as specified above.
2. **Upload Assets to the CDN:**
   1. Place the assets in the appropriate tenant directory under the CDN.
   2. For example:
      1. [http://sunbirded/NCF/logo.png](http://sunbirded/NCF/logo.png)
      2. [http://sunbirded/NCF/appLogo.png](http://sunbirded/NCF/logo.png)
      3. [http://sunbirded/NCF/favicon.ico](http://sunbirded/NCF/logo.png)
      4. [http://sunbirded/NCF/poster.png](http://sunbirded/NCF/logo.png)
3. **Update the Configuration:**
   1. Set the `sunbird_tenant_cdn_url` to the base URL of the CDN in the environment configuration.
   2. Example:
      1. `sunbird_tenant_cdn_url=http://sunbirded`
      2. `sunbird_default_channel=NCF`
4. **Verify the Branding:**
   1. Access the application and ensure that the branding assets are correctly displayed.
   2. If any asset is missing or not configured, the default branding will be used.

***

### Troubleshooting

1. **Missing or Incorrect Branding:**
   1. Verify the URL structure and ensure the assets are correctly named and placed in the tenant directory.
   2. Check the `sunbird_tenant_cdn_url` and `sunbird_default_channel` configurations.
2. **Fallback to Default Branding:**
   1. If the custom asset is not found, the application will use the default Sunbird branding.
   2. Ensure that the asset exists in the CDN with the correct file name.

&#x20;

<br>
