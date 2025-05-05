---
description: >-
  Release notes for the latest Sunbird ED release v7.6.0 - released on 30th Apr
  2025
---

# Sunbird v7.6.0 (Latest)

Sunbird release v7.6.0 is the latest release for the SB platform.

This release primarily incorporates bug fixes from 7.5.x and additional&#x20;

This is a certified and preferred release, and is a recommended upgrade to all the adopters

## Sunbird Ed Mobile App Release - Android v35

### ✅ What's New

* Migrated the app framework from **Cordova to Capacitor**  with backward cordova plugin compatibility
* Updated several plugins to support Capacitor, including:
  * 📁 File plugin
  * 🎥 In-app player

### 🚫 Temporarily Disabled Features

* **Groups**
* **Add/Manage Users**\
  &#xNAN;_&#x54;hese features will be added in future releases based on user needs._

### 📄 Setup Instructions

You can find the updated setup documentation here:\
👉 [SunbirdEd Mobile App GitHub Repo](broken-reference)

## Sunbird Easy Installer

### ✅ What's New

* Portal basics for Error Log Sync settings (\`fix: Added portal basics – Error Log Sync Settings\`)
* Certificate template layout (\`fix: Added cert template layout\`)
* Refactored Helm deployments to easily support other cloud providers&#x20;
  * Removed hardcoded channel values; now maintaining a single source across services
  * Removed \`environment.hcl\` (Terraform legacy cleanup)
  * Abstracted bucket names to \`private\_container\_name\`, \`public\_container\_name\` for flexibility
  * Reduced the number of bucket required from 7 to 3
* Spark deployment and model config updates for improved report handling
* Updated certificate URL and branding logo
* Removed redundant channel creation logic

Link to Release Tag:

{% embed url="https://github.com/project-sunbird/sunbird-ed-installer/releases/tag/7.6.0" %}

