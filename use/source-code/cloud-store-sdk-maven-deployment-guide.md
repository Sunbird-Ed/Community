---
description: >-
  This guide provides a step-by-step process for deploying a dependency to Maven
  Central Repository via OSS Sonatype.
---

# Cloud-Store SDK Maven Deployment Guide

#### Prerequisites

* Ensure you have the `cloud-store-sdk-maven` project directory, containing the necessary `settings.xml` and `sunbird.asc` files.

#### Steps to Push a Dependency to a Maven Repository

1. **Access the Repository:**
   * Open your web browser and navigate to OSS Sonatype.
2. **Login:**
   * Use the username and password from the `cloud-store-sdk-maven/settings.xml` file.
3. **Generate a User Token:**
   * After logging in, go to your profile.
   * From the profile drop-down menu, select **User Token**.
   * Click on **Access User Token** to generate a new username and token.
4. **Update Maven Settings:**
   * Add the newly generated username and token to your `settings.xml` file.
   * Copy the updated `settings.xml` file to your `.m2` folder.
5. **Deploy the Dependency:**
   * Navigate to the directory `cloud-store-sdk_2.12`.
   * If you encounter GPG key errors, run: `mvn deploy -DskipTests`
   * _Note:_ If you encounter GPG key errors, ensure that your GPG keys are valid or adjust your deployment command as needed.
6. **Verify Deployment:**
   * Open your browser and navigate to the Staging Repositories page to confirm your dependency has been pushed to the staging repository.
7. **Release the Dependency:**
   * Once confirmed, click the **Release** button to promote the dependency from the Staging Repository to Maven Central.

