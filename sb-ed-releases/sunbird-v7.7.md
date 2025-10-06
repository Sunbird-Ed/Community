---
description: Release notes for Sunbird Release 7.7 - 14 July 2025
---

# Sunbird Release 7.7 (Latest)

Sunbird Release 7.7 is now available.

The release includes fixes for some of the vulnerabilities identified, as well as a Keycloak upgrade (from the older version 7 to the newer 21) &#x20;

Jira Tickets for Release 7.7 : [https://project-sunbird.atlassian.net/issues/?filter=13047](https://project-sunbird.atlassian.net/issues/?filter=13047)



#### **Release Highlights – Sunbird v7.7.0**

* GitHub Actions enabled for 90% of repositories
* Keycloak upgraded from version 7 to 21
* Security and vulnerability fixes implemented
* Volume autoscaler added to dynamically increase Persistent Volume (PV) sizes
* Unique suffix added to all bucket names to ensure global uniqueness and prevent conflicts
* Support added for database-level backups with Velero, enabling targeted restore and improved recovery flexibility

#### **Link to Release Tag** [**Release v7.7.0 · project-sunbird/sunbird-ed-installer**](https://github.com/project-sunbird/sunbird-ed-installer/releases/tag/v7.7.0)

📘 Migration Guide

* A unique suffix has been added to all bucket names to ensure global uniqueness and avoid naming conflicts.
* Manually copy backup data from the **old public bucket** (specific directories) to the **corresponding private bucket** that includes the new unique suffix .
* If any data from the old public bucket is still in use, copy it to the new bucket as well.
* Update all references in **Postman collections** to the new unique suffix bucket names and re-run the requests.

#### &#x20;&#x20;

**To validate :**

1. Import the Postman collection into Postman: _Postman Collection v7.0.0_
2. Load the appropriate `env.json` file (containing environment variables).
3. Run the collection to confirm that all APIs work with the updated configuration.

**Example:**\
For APIs like the **TnC config API** under _Learn system settings_, re-run the API with the updated bucket path so that the changes are correctly reflected





