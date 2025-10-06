---
description: Release notes for Sunbird Release 8.0.0 -  06/10/2025
---

# Sunbird Release 8.0.0(Latest)

This release delivers major feature enhancements, security updates, removal of hardcoded branding, BGMS(board, grade, medium and subject ) category, smarter content discovery via NLQ(Natural language query), and mobile app readiness.

📌 **Jira Tickets for Release 8.0.0:**

[https://project-sunbird.atlassian.net/issues/?filter=13080](https://project-sunbird.atlassian.net/issues/?filter=13080)

***

#### 🛠️ **Key Highlights of the Release**

1. **Security and Vulnerability Fixes**
   * Continued hardening of code and Docker images across core services.
   * Addressed CVEs and upgraded libraries/dependencies as needed.
2. **Implemented Delete Account Functionality**
   * Allows users to permanently delete their accounts from the system.
3. **Removed BMGS Hardcoding**
   * Eliminated all BMGS\[**B**oard, **M**edium, **G**rade, **S**ubject] specific hardcoding across portal, editor, and common components.
4. **Removed Diksha Branding Hardcoding**
   * Diksha-specific logos, terms, and configurations are now replaced with **Sunbird**-compliant defaults.
5. **Support for Special Characters in Email**
   * Provided a ability to register and log in with email addresses containing special characters.
6. **Mobile App Publication to Google Play Store**\
   Resolved all issues, including security vulnerabilities and Play Store policy compliance fixes. Verified the Sunbird app by building the AAB file and successfully uploading it to the Play Store, where it passed all verification checks. Additionally, other adopters can now publish their apps seamlessly without encountering any issues.
7. **Content Players Enhanced with i18n Support**
   * Integrated content players with both portal and mobile app; now supports localization.
8. **Language Switching Fixes in Player**
   * Addressed issues with RTL/LTR switching and moved defaults to configurable properties.
9. **NLQ-Based Content Discovery Enabled**
   * Natural Language Query (NLQ) support integrated using **NLWeb** for smarter search.
10. **Elastic search Downgrade to 7.10.2**
    * Downgraded from incompatible versions for improved system stability.
11. **Quiz Support in Online Mode**
    * The mobile app allows users to play quizzes online in addition to offline quizzes. .
12. **Bitnami Image Deprecation**
    * Bitnami images are being deprecated.
    * To ensure long-term stability, compatibility, and support, all Bitnami images have been retagged in ACR (Azure container registry).

Link to Release Tag:&#x20;

[https://github.com/project-sunbird/sunbird-ed-installer/releases/tag/v8.0.0](https://github.com/project-sunbird/sunbird-ed-installer/releases/tag/v8.0.0)
