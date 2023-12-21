# Release notes

<table data-full-width="true"><thead><tr><th>Release Version</th><th>Date</th></tr></thead><tbody><tr><td>7.0.0</td><td>TBD</td></tr></tbody></table>

### Overview

This release focusses on the removal of hard-coded values in the mobile and web apps. Adopters can now create their own frameworks and customise the features as per their requirements. Also, Google Play has mandated to have account deletion feature in the app for Android users.

Discussion thread:&#x20;

### New Features

#### **1.** **Delete user functionality (**[**LR-683**](https://project-sunbird.atlassian.net/browse/LR-683)**)**

<details>

<summary>Details</summary>

Sunbird Mobile and Web app will comply to the [Google Play app's account deletion requirements](https://support.google.com/googleplay/android-developer/answer/13327111?hl=en#zippy=%2Cwhat-users-will-see-if-your-app-supports-account-deletion). It has mandated that if the app allows user to create their account then it must also allow users to request for account deletion. This will establish transparency and give control to users over their data.

</details>

#### **2.** Generalisation of Sunbird ED by r**emoval of hard-coded values in Mobile and Portal (**[**ED-1957**](https://project-sunbird.atlassian.net/browse/ED-1957)**,** [**ED-3042**](https://project-sunbird.atlassian.net/browse/ED-3042)**)**

<details>

<summary>Details</summary>

Previously, Sunbird ED supported only a single domain, i.e., Education. Now, adopters can create their own framework and customise the features as per their requirements. The features has been made dynamic by removing the hard-coded values in both Mobile app and Portal.

For more details, refer [link](https://project-sunbird.atlassian.net/wiki/spaces/SUN/pages/3398729734/ED-Portal+Config+Changes+as+per+the+BMGS+Hardcoded+Removal)

</details>

### Enhancements / Technical Tasks

#### **1.**[ ](https://github.com/Sunbird-Ed/Community/blob/7e03a2a3a6d002b0f80afa6c5a80994949125228/use/releases/release-notes/6.0.0-draft.md#enhancements-technical-tasks-details)Capacitor Migration ([ED-2963](https://project-sunbird.atlassian.net/browse/ED-2963))

<details>

<summary>Details</summary>

Migration from Cordova to Capacitor version 5

Note: Capacitor beta version is done

</details>

### Bug Fixes

This release had a few bug fixes. For a complete list, refer to this link



### Open/Known Bugs

There are a few known bugs in this release. For a complete list, refer to this link

### Build Tags

The build tags used by the below building blocks for this release to upgrade your Sunbird ED are:

_Sunbird ED_

_Sunbird Lern_

_Sunbird Obsrv_

_Sunbird-Knowlg_

_Sunbird-InQuiry_

### Installation or Upgrade

_For fresh installation 7.0.0_

_Upgrade Sunbird from 6.0.0 to 7.0.0_

### Configuration/Environment variable

This section provides a list of environment variables with their default values and descriptions required to run either the Sunbird portal or mobile service. To change the default behavior, modify the variable value based on your requirements.

_Adding new variables_

### Deprecations and Removals

This section provides the list of APIs that are deprecated or removed from this release.

_Note: There are no APIs deprecated or removed in this release._

### Breaking Changes



### Release Notes: Dependent building blocks

Sunbird-Knowlg:&#x20;

Sunbird-Obsrv:&#x20;

Sunbird-Lern:&#x20;

Sunbird-inQuiry:&#x20;

Sunbird-CoKreat:&#x20;
