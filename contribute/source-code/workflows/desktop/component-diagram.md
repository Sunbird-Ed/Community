---
description: >-
  The Sunbird Desktop is the offline-based interface that provides to access &
  distribution of digital content in areas where Internet connectivity is
  challenging.
---

# Component Diagram

## GitHub Repository

{% embed url="https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop" %}
github repo
{% endembed %}

## Architecture

<figure><img src="../../../../.gitbook/assets/Screenshot 2023-08-11 at 6.59.48 PM.png" alt=""><figcaption><p>Desktop Architecture</p></figcaption></figure>

Sunbird desktop run on a platform called [electron](https://www.electronjs.org/)

## Sunbird Desktop

![](<../../../../.gitbook/assets/Screenshot 2023-08-10 at 8.14.31 PM (1).png>)

### Sunbird Desktop UI

![](<../../../../.gitbook/assets/image (28).png>)

The Portal folder is responsible to render the UI on the desktop.

### Sunbird Desktop API Server

![](<../../../../.gitbook/assets/Screenshot 2023-08-11 at 8.28.51 PM.png>)

The Modules folder contains the API server proxy to communicate with the upstream server

### Code Structure

Important folder

These are the important folder that is used in Sunbird Desktop

* [helpers](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/helper)
* [glupfile.js](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/master/src/desktop/gulpfile.js)
* [main.ts](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/master/src/desktop/main.ts)
* [modules](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/modules)
* [OpenRAP](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/OpenRAP)
* [Public](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/public)
* [env.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/desktop/env.json)
* [openrap-sunbirded-plugin](component-diagram.md#openrap-sunbirded-plugin)

### [helpers](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/helper)

The folder is used to provide the Authentication/Authorization session of the logged-in user.

### [glupfile.js](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/master/src/desktop/gulpfile.js)

In the portal desktop Gulp is a task runner that uses Node.js as a platform. Gulp purely uses JavaScript code and helps to run front-end tasks and large-scale web applications. It builds system automated tasks like CSS and HTML minification, concatenating library files, and compiling the SASS files.

### [main.ts](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/master/src/desktop/main.ts)

main.ts file is the entry point of a portal desktop. where all the scripts execution initiate

### [modules](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/modules)

This folder contains API server proxy to communicate with the upstream server such as routes, sdk db schema, logger, proxy-util, telemetry helper

### [OpenRAP](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/OpenRAP)

OpenRAP is more like a repo, where we have a content database which is meant for desktop it's a standalone app that runs mainly offline first. in offline first certain items such as content items, and telemetry user data have to store & when the user log-in it's not online but it will give the data from the [pouchdb](component-diagram.md#pouchdb).

OpenRAP is an open-source initiative to enable communities/stakeholders to easily build and deploy WiFI-enabled resource access points within their community.

### [pouchdb](https://pouchdb.com/)

It enables applications to store data locally while offline, then synchronize it with CouchDB and compatible servers when the application is back online, keeping the user's data in sync no matter where they next log in.

### [Public](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/public)

The folder includes the code to initiate the player and the portal UI in the desktop app

### [env.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/desktop/env.json)

It contains the [env.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/desktop/env.json) file which is responsible for storing the env variable such as token,baseurl, and id that is required in the Desktop from DevOps.

### openrap-sunbirded-plugin

It contains the below folder

content: sample content to be used for offline desktop

Data: It contains some sample channels used as a default, sample form JSON, faq, framework & location.

ecars: it stands for ekstep content archive it stores and loads the ecras if required on desktop

### Resources:

* [Portal Desktop Application - Local Setup](https://project-sunbird.atlassian.net/wiki/spaces/SP/pages/3339354113/Portal+Desktop+Application+-+Local+Setup)
* [OpenRAP](https://sunbird.org/explore/articles/16-sunbird-openrap-an-offline-content-distribution-platform)
* [electron](https://www.electronjs.org/)

#### &#x20;<a href="#title-text" id="title-text"></a>
