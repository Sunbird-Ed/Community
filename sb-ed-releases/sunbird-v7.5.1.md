---
description: >-
  Release notes for the latest Sunbird ED release v7.5.1 - released on 14 March
  2024.
---

# Latest Release - Sunbird v7.5.1

Sunbird release v7.5.1 is the latest release for the SB platform.

This release primarily incorporates bug fixes from 7.5.&#x20;

This is a certified and preferred release, and should be used by all adopters.



Link to Release Tag:

{% embed url="https://github.com/project-sunbird/sunbird-ed-installer/releases/tag/7.5.1" %}

Jira Filter for this release : [Link](https://project-sunbird.atlassian.net/jira/software/c/projects/SBCOSS/issues/?filter=allissues\&jql=project%20%3D%20%22SBCOSS%22%20AND%20sprint%20IN%20%28595%2C%20596%2C%20630%29%20AND%20parent%20IN%20%28SBCOSS-41%2C%20SBCOSS-119%2C%20SBCOSS-114%29%0AORDER%20BY%20created%20DESC)



**RELEASE NOTES:**

### Overview

The latest Sunbird release (v7.5.1) brings significant improvements in infrastructure, deployment, and platform functionality. This update streamlines installation, enhances service management, and introduces critical feature updates.

### Key Changes

#### **Infrastructure & Deployment Updates**

* **Kubernetes-Only Deployment:**
  * Sunbird automation releases will now exclusively support Kubernetes-based deployment.
  * Mixed environments (Kubernetes + VMs) will no longer be supported.
  * Helm bundles introduced for simplified installation, with each building block encapsulated as its own bundle.
  * Elimination of multiple jobs across Ansible/Jenkins in favor of a streamlined Helm-based approach.

#### **Service Enhancements & Refactoring**

* **Renaming & Optimization:**
  * Enhanced `Flink` job management with new jobs added for inquiry and learning services.
  * Various Cassandra database migration fixes for `inquirybb`.
* **Configuration & Security Enhancements:**
  * Updated certificate configuration functions to inject cert keys.
  * Improved Postman collections for API testing and validation.

#### **Feature Updates**

* **Form & API Enhancements:**
  * Templates added for `ED-7.0` forms and APIs.

### Migration & Compatibility

* Existing deployments on mixed environments (Kubernetes + VMs) need to be migrated to the new Helm-based system.
* Upgrade paths from v6.0.0 to v7.5.1 have been tested and validated.

### Next Steps

* For detailed guides and installation steps, refer to the official Sunbird documentation.
* Report issues or request support via the Sunbird Discussions.

This release is a major step forward in simplifying Sunbird’s deployment, making it more scalable, manageable, and future-proof. Happy upgrading!



