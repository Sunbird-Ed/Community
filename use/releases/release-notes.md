# Release notes

<table data-full-width="true"><thead><tr><th>Release Version</th><th>Date</th></tr></thead><tbody><tr><td>6.0.0</td><td>27-Sep-2023</td></tr></tbody></table>

### Overview

This release majorly highlights the CSP changes and angular upgrades. Sunbird ED is now cloud agnostic; it will run seamlessly on any cloud service. Both the web app and mobile app have completed the angular upgrades.

Discussion thread: [https://github.com/orgs/Sunbird-Ed/discussions/508](https://github.com/orgs/Sunbird-Ed/discussions/508)

### New Features

#### **1.** **Access Program dashboard and reports without resource filter** **(**[**ED-63**](https://project-sunbird.atlassian.net/browse/ED-63)**)**

<details>

<summary>Details</summary>

Program managers can access program-level data, including user detail reports, and graphs without selecting resource-level filters. Program designers need to select resource filters to view data. Big number data will also be shown in the graphs tab.

</details>

#### **2.** **Introduction of Multi-select Block filter** **(**[**ED-63**](https://project-sunbird.atlassian.net/browse/ED-63)**,** [**ED-520**](https://project-sunbird.atlassian.net/browse/ED-520)**)**

<details>

<summary>Details</summary>

A multi-select block filter will be available to drill down the data in the program and admin dashboard. Block filter will be enabled only when users select a district. A new ‘Block-wise status’ tab is also added to the program dashboard.

</details>

#### **3.** **Copy the whole Question Set with the click of a button** **(**[**ED-1945**](https://project-sunbird.atlassian.net/browse/ED-1945)**)**

<details>

<summary>Details</summary>

Users are now enabled to copy the whole question set, similar to copying the content.

</details>

#### **4.** **Updates on PII Consent and Data for Managed Learn (**[**ED-609**](https://project-sunbird.atlassian.net/browse/ED-609)**)**

<details>

<summary>Details</summary>

The program managers and designers can view the data of the number of users who joined a program. Users can choose to join a program with or without providing PII consent. Consenting to share PII data will lead to information, such as Name, State, User ID, District, Block, School ID, and School Name, being shared with the administrators.

Program managers and designers will have the ability to download and access the User detail report, which contains the users' updated PII information.

</details>

#### **5.** **Start date of the Program** **(**[**ED-63**](https://project-sunbird.atlassian.net/browse/ED-63)**,** [**ED-609**](https://project-sunbird.atlassian.net/browse/ED-609)**)**

<details>

<summary>Details</summary>

The program becomes discoverable for targeted users according to the start date of the program given by the program designer while creating the program. The users will be notified whether a program has been joined or not on the program details page.

</details>

### Enhancements / Technical Tasks

#### **1.**[ ](https://github.com/Sunbird-Ed/Community/blob/7e03a2a3a6d002b0f80afa6c5a80994949125228/use/releases/release-notes/6.0.0-draft.md#enhancements-technical-tasks-details)Sunbird ED is now cloud-agnostic ([ED-2631](https://project-sunbird.atlassian.net/browse/ED-2631))

<details>

<summary>Details</summary>

From this release, SunbirdEd proudly supports cloud agnosticity, allowing you to deploy and run the platform seamlessly across various cloud providers. This means you have the freedom to choose the cloud environment that best suits your organization's needs, whether it's AWS, Azure, Google Cloud, or others. To achieve this, Sunbird has built the SDK to help all the services use the same code base as much as it can.

For more details on the node services, backend services, and file upload plugins, refer [CSP changes](https://ed.sunbird.org/\~/changes/c4YpJpIRZcszTUHGkkDJ/use/developer-guide/csp-changes)

</details>

#### **2.** Angular Upgrades

Angular migration is completed for

* **Portal**: from v11 to v14
* **Mobile** **App**: from v9 to v13

<details>

<summary>Details</summary>

* **Angular upgrade** is completed for both the Web app and the Mobile app.([ED-1312](https://project-sunbird.atlassian.net/browse/ED-1312), [ED-1311](https://project-sunbird.atlassian.net/browse/ED-1311))
  * Web app version updated from 11 to 14
  * Mobile App version updated from 9 to 13

<!---->

* **Cordova migration**: The software upgrade for Cordova-android is carried out to version 11. ([ED-1323](https://project-sunbird.atlassian.net/browse/ED-1323))

_**Note:** The splash screen will display a single-colored background with no customization. For more information, refer to_ [_splash screens_](https://developer.android.com/develop/ui/views/launch/splash-screen) _and_ [_migrate existing splash screens_](https://developer.android.com/develop/ui/views/launch/splash-screen/migrate)

* **Ionic Migration**: The software upgrade for ionic migration is carried out from version 5 to 6. ([ED-1682](https://project-sunbird.atlassian.net/browse/ED-1682), [ED-1322](https://project-sunbird.atlassian.net/browse/ED-1322))
* **SB-dashlets** library migrated to version 14 ([ED-2066](https://project-sunbird.atlassian.net/browse/ED-2066))

</details>

#### **3.** **Enhanced Observation and Project features** **(**[**ED-63**](https://project-sunbird.atlassian.net/browse/ED-63)**)**

<details>

<summary>Details</summary>

* Users can add links as evidence at the task and project level
* Users can view the observation questionnaire before starting the observation.
* Users can delete any wrongly attached files to the tasks created in any project.
* Evidence attached at a project level will automatically be saved to the ‘Files’ section

</details>

#### **4.** **Enhancements in the Program feature** **(**[**ED-63**](https://project-sunbird.atlassian.net/browse/ED-63)**)**

<details>

<summary>Details</summary>

* New interface for program listing page
* Addition of a program feature for teachers

</details>

### Bug Fixes

This release had a few bug fixes. For a complete list, refer to this [link](https://project-sunbird.atlassian.net/issues/?filter=12819)

1. While accessing the course from the Programs tile, users were navigated to the profile page by clicking the back button ([ED-1619](https://project-sunbird.atlassian.net/browse/ED-1619))
2. The telemetry events were not generated when the user tapped the OK button on the confirmation pop-up while exiting from playing content. ([ED-1290](https://project-sunbird.atlassian.net/browse/ED-1290))
3. The Export CSV button was not working in the admin dashboard tables ([ED-2160](https://project-sunbird.atlassian.net/browse/ED-2160))
4. Errors from SB-Dashlet components affecting graphs and tables ([ED-2019](https://project-sunbird.atlassian.net/browse/ED-2019))
5. Bugs resolved in Rapid Survey Questionnaire\_CWSN ([ED-83](https://project-sunbird.atlassian.net/browse/ED-83))
6. Video course progress was not getting updated ([KN-710](https://project-sunbird.atlassian.net/browse/KN-710))
7. The course progress did not update as completed after consuming 20% of video content ([KN-733](https://project-sunbird.atlassian.net/browse/KN-733))
8. Global filters not coming up in the admin dashboard graphs ([ED-2027](https://project-sunbird.atlassian.net/browse/ED-2027))
9. Longer text MCQ questions UI was breaking, and in the options that contained longer text, the radio button was not visible ([IQ-64](https://project-sunbird.atlassian.net/browse/IQ-64))
10. Users were unable to create more than 20 questions in the Question set ([IQ-181](https://project-sunbird.atlassian.net/browse/IQ-181))
11. Users were able to see the delete icon for the added file in the Observation tile and Survey tile ([ED-1274](https://project-sunbird.atlassian.net/browse/ED-1274))
12. Users could select an end date for the Program and resources that were lesser than the start date ([ED-1642](https://project-sunbird.atlassian.net/browse/ED-1642))

### Open/Known Bugs

There are a few known bugs in this release. For a complete list, refer to this [link](https://project-sunbird.atlassian.net/issues/?filter=12841)

1. Accessibility issues:
   * Users will not be able to consume the downloaded question set in offline mode. ([ED-2317](https://project-sunbird.atlassian.net/browse/ED-2317))
   * Register here and forgot password links are not working on the login page ([ED-2305](https://project-sunbird.atlassian.net/browse/ED-2305))
2. In the desktop application, the minimize button will freeze when the course assessment is in full-screen mode ([ED-2813](https://project-sunbird.atlassian.net/browse/ED-2813))

### Build Tags

The build tags used by the below building blocks for this release to upgrade your Sunbird ED are:

[Sunbird ED](https://ed.sunbird.org/use/updating-sunbird-releases/5.2.0-to-6.0.0-draft#sunbirded)

[Sunbird Lern](https://ed.sunbird.org/use/updating-sunbird-releases/5.2.0-to-6.0.0-draft#sunbird-lern)

[Sunbird Obsrv](https://ed.sunbird.org/use/updating-sunbird-releases/5.2.0-to-6.0.0-draft#sunbird-obsrv)

[Sunbird-Knowlg](https://ed.sunbird.org/use/updating-sunbird-releases/5.2.0-to-6.0.0-draft#sunbird-knowlg)

[Sunbird-InQuiry](https://ed.sunbird.org/use/updating-sunbird-releases/5.2.0-to-6.0.0-draft#sunbird-inquiry)

### Installation or Upgrade

[For fresh installation 6.0.0](https://ed.sunbird.org/use/installing-ed-platform/release-5.2.0-1)

[Upgrade Sunbird from 5.2.0 to 6.0.0](https://ed.sunbird.org/use/updating-sunbird-releases/5.2.0-to-6.0.0-draft)

### Configuration/Environment variable

This section provides a list of environment variables with their default values and descriptions required to run either the Sunbird portal or mobile service. To change the default behavior, modify the variable value based on your requirements.

[Adding new variables](../updating-sunbird-releases/5.2.0-to-6.0.0.md#adding-the-new-variables)

### Deprecations and Removals

This section provides the list of APIs that are deprecated or removed from this release.

_Note: There are no APIs deprecated or removed in this release._

### Breaking Changes

_Note: There are no notable breaking changes in Web App - Portal in this release._

Mobile App: [Cordova migration](https://github.com/Sunbird-Ed/Community/blob/7e03a2a3a6d002b0f80afa6c5a80994949125228/use/releases/release-notes/6.0.0-draft.md#cordova-migration-the-software-upgrade-for-cordova-android-is-carried-out-to-version-11.)

### Release Notes: Dependent building blocks

Sunbird-Knowlg: [v 5.5.0](https://knowlg.sunbird.org/use/release-notes/release-5.5.0-latest)

Sunbird-Obsrv: [v 5.1.0](https://obsrv.sunbird.org/use/release-notes/release-v-5.1.0)

Sunbird-Lern: [v 5.3.0](https://lern.sunbird.org/use/release-notes/release-v-5.3.0)

_**Note**: Only PII changes are taken in this release. RC migration is planned for future releases._

Sunbird-inQuiry: [v 5.7.0](https://inquiry.sunbird.org/use/release-notes/inquiry-release-v5.7.0-latest)

_**Note**_: _Question set editor is not integrated, planned for future releases._

Sunbird-CoKreat: [v 5.2.0](https://cokreat.sunbird.org/use/release-notes/cokreat-release-v5.2.0-upcoming-release)
