---
description: >-
  The Sunbird Desktop is the offline-based interface that provides to access &
  distribution of digital content in areas where Internet connectivity is
  challenging.
---

# Component Diagram

## GitHub Repository

{% embed url="https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop" %}

## Architecture

<figure><img src="../../../../.gitbook/assets/Screenshot 2023-08-11 at 6.59.48 PM.png" alt=""><figcaption><p>Desktop Architecture</p></figcaption></figure>

Sunbird desktop run on a platform called [electron](https://www.electronjs.org/)

## Sunbird Desktop&#x20;

![](<../../../../.gitbook/assets/Screenshot 2023-08-10 at 8.14.31 PM (1).png>)



### Sunbird Desktop UI

![](<../../../../.gitbook/assets/image (28).png>)

To render the UI in desktop we need to take the portal clien



### Sunbird Desktop API Server

![](<../../../../.gitbook/assets/Screenshot 2023-08-11 at 8.28.51 PM.png>)

### Code Structure

Important folder

These are the important folder that is used in Sunbird Desktop

* [helpers](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/helper)
* glupfile.js
* main.ts
* modules
* [OpenRAP](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/OpenRAP)
* [Public](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/public)&#x20;
* [env.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/desktop/env.json)
* openrap-sunbirded-plugin

### [helpers](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/helper)

### [OpenRAP](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/OpenRAP)

opern rap is more like a repo by itself, where ewe have content database which is menat for desktop is a sandalone app its run on mainly on offline first

OpenRAP is an open source initiative to enable communities/stakeholders to easily build and deploy WiFI-enabled resource access points within their community.

### &#x20;[Public](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/master/src/desktop/public)

The folder includes  the code to initiate the player in the desktop app

### [env.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/desktop/env.json)

It contains the [env.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-6.0.0/src/desktop/env.json) file which is responsible for storing the env variable such as token,baseurl,id that is required in the Desktop from DevOps.

### openrap-sunbirded-plugin
