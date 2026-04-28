---
description: Release notes for Sunbird Release 8.1.0 -  16th December 2025
---

# Sunbird v8.1.0 (Latest)

This release focuses on **platform modernization, framework upgrades, and service consolidation**, ensuring better maintainability, improved performance, and long-term support readiness. Major backend components have been upgraded to supported versions, and architectural changes have been introduced to streamline services.

**Jira Tickets for Release 8.1.0:**\
[**https://project-sunbird.atlassian.net/issues?filter=13113**](https://project-sunbird.atlassian.net/issues?filter=13113)

### **Key Highlights of the Release**

1.  **Backend Framework Modernization**<br>

    **a. Migration from Akka to Pekko**

    * Replaced **Akka 2.5.22** with **Pekko 1.0.3** across backend services.
    * Removes dependency on Akka’s business source license.
    * Ensures long-term sustainability by adopting a fully open-source alternative.<br>

    **b. Play Framework Upgrade**

    * Upgraded **Play Framework 2.4.x/2.7.x/2.8.x (EOL)** to **Play 3.0.5**.
    * Improves performance, security, and compatibility with modern tooling.
    * Enables better support for newer Java and Scala versions.<br>

    **c. Scala Version Upgrade**

    * Upgraded Scala from **Scala 2.11.x/2.12.x** to **Scala 2.13.12**.<br>
2.  **Frontend Enhancements**<br>

    **Portal Angular Upgrade**

    * Upgraded Angular from **v14 to v16** for improved performance and maintainability.<br>
3.  **Architecture & Service Changes**<br>

    **Deprecation of Learning Service**

    * The **Learning Service** has been officially deprecated.
    * All **Assessment-related APIs** have been moved to the **Inquiry: Assessment Service**.
    * Modernizes the codebase by removing deprecated APIs.<br>
4.  **Node.js Runtime Upgrade (Middleware Services)**<br>

    Upgraded Node.js from version 12 to **22.17.1 (LTS)** for the following services:

    * knowlg-mw-service
    * discussion-middleware

    This change addresses known security vulnerabilities, improves runtime performance, and ensures continued support with an actively maintained Node.js version.

### Discussion Forum Configuration Guide

Refer to the **Sunbird Discussion Forum Configuration Guide** for step-by-step instructions on:

* NodeBB API authorization setup
* Master category (pid) validation and updates
* Rate limit configuration
* Final validation steps\
  \
  [https://docs.google.com/document/d/1FTSCWwTfTr6DGnHAuwwxO9yWtbSdXd3AmvqdYH4Z68U/edit?tab=t.0](https://docs.google.com/document/d/1FTSCWwTfTr6DGnHAuwwxO9yWtbSdXd3AmvqdYH4Z68U/edit?tab=t.0)

### **Link to Release Tag:**

{% embed url="https://github.com/project-sunbird/sunbird-ed-installer/releases/tag/v8.1.0" %}

### **Migration Guide**

1. Import the Postman collection into Postman: [ https://github.com/project-sunbird/sunbird-ed-installer/blob/main/postman-collection/collectionrelease700.json](https://github.com/project-sunbird/sunbird-ed-installer/blob/main/postman-collection/collectionrelease700.json)
2. Load the appropriate `env.json` file containing the required environment variables.
3. Run the following APIs in Postman:
   * **Forms ->** Content: 5 - Book Create API
   * **Forms ->** Ed: 1 - Menubar form - Creation for all rootOrg API
   * **Forms ->** Ed: 13 - Resource Create API
   * **Forms ->** Ed: 17 - Questionset API





