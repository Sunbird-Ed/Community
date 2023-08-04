---
description: >-
  The Sunbird portal is the browser-based interface for the Sunbird application
  stack. It provides a web app through which all functionality of Sunbird can be
  accessed.
---

# Portal - Component Diagrams

## GitHub Repository:&#x20;

{% embed url="https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/release-6.0.0" %}

## Architecture

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption></figcaption></figure>

## Sunbird ED Portal&#x20;

&#x20;The Sunbird ED portal is divided into two folders called app that contains server-side code and client for client-side code.

![](<../../../.gitbook/assets/image (22).png>)![](<../../../.gitbook/assets/image (23).png>)



## **Sunbird Portal UI**

<figure><img src="../../../.gitbook/assets/image (24).png" alt=""><figcaption></figcaption></figure>

[**Client Folder**](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/6.0.0/src/app/client)

Includes the client source code for the Angular application. This folder includes various components, modules, services, styles, and other assets necessary to build the front end of the application.&#x20;



### [Public ](https://sunbird-ed.github.io/docs/portal/modules/PublicModule.html)

The main objective of this folder to&#x20;

The folder contains all the components page routes which can be accessible by anonymous or guest users.&#x20;

### [Core](https://sunbird-ed.github.io/docs/portal/modules/CoreModule.html)

The folder contains all the reusable features such as the header, footer, search, main menu, and language dropdown.



### [Shared](https://sunbird-ed.github.io/docs/portal/modules/SharedModule.html)

The Folder contains all the reusable components across the portal such as the loader, popup, card,sb-data table, alert popup, slick etc...

### Manage Learn

TBU

### Additional Info:

#### Forms

In the portal, lots of UI capabilities are generalised in terms of [formConfig](https://documenter.getpostman.com/view/25186239/2s946pXoZ2). to reduce the code dependency by decoupling form logic from the portal code.

## Front-End Libraries

<figure><img src="../../../.gitbook/assets/image (26).png" alt=""><figcaption></figcaption></figure>

All the library that Front-end is depending  to get the capabilities&#x20;

| ED Library Name    | GitHub Repo                                                                                                                                        | Description                                                                                                                                                                                                       |
| ------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Common Consumption | [https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents#readme](https://github.com/Sunbird-Ed/SunbirdEd-consumption-ngcomponents#readme) | These components are designed to be used in Sunbird consumption platforms _( web portal, offline desktop app)_ to drive reusability, maintainability hence reduce the redundant development effort significantly. |
| Player             | [https://github.com/Sunbird-Ed/sb-styles/tree/master](https://github.com/Sunbird-Ed/sb-styles/tree/master)                                         | Sunbird styles is Sass-based tool to generate utility classes.                                                                                                                                                    |
| Editors            | [https://github.com/Sunbird-Ed/sb-themes](https://github.com/Sunbird-Ed/sb-themes)                                                                 | Sunbird themes are color & layout templates used in subird Portal & Mobile apps.                                                                                                                                  |
| SB-Forms           | [https://github.com/Sunbird-Ed/SunbirdEd-forms](https://github.com/Sunbird-Ed/SunbirdEd-forms)                                                     |                                                                                                                                                                                                                   |
| SB-Dashlet         |                                                                                                                                                    |                                                                                                                                                                                                                   |
| Client Service     |                                                                                                                                                    |                                                                                                                                                                                                                   |

## Sunbird Portal API Servcies&#x20;

[**App Folder**](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/6.0.0/src/app)

<figure><img src="../../../.gitbook/assets/image (25).png" alt=""><figcaption></figcaption></figure>

Includes backend API interface which is used  Node.js framework.&#x20;

It leverages a keyCloakHelper file to handle login and logout functionalities while adopting token-based session storage to manage user sessions effectively.&#x20;

Additionally, the interface integrates multiple API middleware functions to accomplish tasks such as token verification, API whitelisting, and customizing request headers as needed.



### Code Structure

### [User Session Management - **Server.js** ](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/6.0.0/src/app/server.js)

It is used in web development for the server-side entry point of a Node.js application.

It acts as the main starting point of the server, responsible for initializing the server, defining routes, and handling incoming requests from clients.

it is used to store the session based on [Anonymous](https://project-sunbird.atlassian.net/wiki/spaces/SP/pages/3324477457/Portal+-+Login+Work+flow+post+success+with+keycloak+-+Anonymous) &[ Logged in User](https://project-sunbird.atlassian.net/wiki/spaces/SP/pages/3324182538/Portal+-+Login+Work+flow+post+success+with+keycloak+-+Logged+In+User)

### [**Routes**](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/6.0.0/src/app/routes)

It handles all the API routes. which are triggering from the client side. such as content/\*, content/copy/questionset etc.

### [API Whitelisting: **Helpers Folder** ](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/6.0.0/src/app/helpers)

Contains all the js files which are used for user [authentication](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/app/helpers/kongTokenHelper.js) and [authorization](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/app/helpers/keyCloakHelper.js).

Contains the [API Whitelist](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/app/helpers/apiWhiteList.js) js file which Handles whitelisting and role checks of Portal API(s).

### [Role check: **Proxy Folder**](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/6.0.0/src/app/proxy)

it contains the set-up method such as decoraterequestHeader, verifyToken, and isApiwhitelisted which validates whether the API request is valid or not with proper role check and auths token.

[**ResourceBundles**](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/6.0.0/src/app/resourcebundles)**:** it contains the resource bundles for internationalization and localization purposes in the application. it is used for translations and provides a seamless way to display the application's user interface in different languages based on user preferences.

### [EnvVariablesHelper](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/app/helpers/environmentVariablesHelper.js)

It contains the [envHelperFile](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/app/helpers/environmentVariablesHelper.js) which is responsible for storing the env variable that is required in the portal from DevOps.

## **Dependent Sunbird BB\`s**

<figure><img src="../../../.gitbook/assets/image (4).png" alt=""><figcaption></figcaption></figure>

Lots of front-end Libraries and services we are leveraging from the other building blocks

### **Sunbird Building Blocks which are being used in ED Portal**

* [Lern](https://lern.sunbird.org/)
* [Obsrv](https://obsrv.sunbird.org/)
* [InQuiry](https://inquiry.sunbird.org/learn/readme)
* [Knowlg](https://knowlg.sunbird.org/learn/readme)
* [ED](https://ed.sunbird.org/learn/readme)
