---
description: Sunbird Releases and planned dates
---

# Releases and Dates

**RELEASE 7.5.1** :: 10th MARCH 2025&#x20;

* Image Consolidation - All images to be pulled from sunbird ACR instead of personal ones
* Superset for visualization and reporting to be included as part of Easy Installer for Sunbird ED.
* Report Services Configuration Fixes
* Flink jobs configuration fixes
* Domain in postman collection will use the global domain name instead of having to change manually for each installation
* Report service upgraded to 5.x instead of 4.x which supports all cloud providers
* Resources configuration updates, to prevent jobs from running out of memory
* Generalize the cassandra and postgres configurations to work with the global values
* Missing bundles in downloadable artifacts are added, to support smooth installation.
* Fixes to support publishing content on GCP
* Velero  for cluster backups

**RELEASE 7.6** :: 20 MARCH 2025

* ~~Keycloak upgrade to 21~~ (to be taken up in a later releast)
* Mobile App:
  * Android version upgrade to 34
  * Angular updated to 19
  * Plugins Migration to Capacitor as a replacement for Cordova within Ionic
  * Workflow fixes
    * Google Login
    * Offline Access and share
    * Course Consumption with certification
  * Bug fixes
