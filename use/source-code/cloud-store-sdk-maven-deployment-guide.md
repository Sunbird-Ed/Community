---
description: >-
  This guide provides a step-by-step process for deploying a dependency to Maven
  Central Repository via OSS Sonatype.
---

# Cloud-Store SDK Maven Deployment Guide

### Steps to Push a Dependency to a Maven Repository

#### **Prerequisites:**

Ensure you have the `cloud-store-sdk-maven` project directory, containing the necessary `settings.xml` and `sunbird.asc` files.

#### Steps:

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
   *   If you encounter GPG key errors, run:

       ```bash
       mvn deploy -DskipTests
       ```
   * If you receive an error related to GPG keys while deploying, [follow these steps](cloud-store-sdk-maven-deployment-guide.md#managing-gpg-keys)
6. **Verify Deployment:**
   * Open your browser and navigate to the Staging Repositories page to confirm your dependency has been pushed to the staging repository.
7. **Release the Dependency:**
   * Once confirmed, click the **Release** button to promote the dependency from the Staging Repository to Maven Central.

### Managing GPG Keys

1.  **List Existing GPG Keys**

    To view all stored GPG keys and check for expiry:

    ```
    gpg --list-keys
    ```
2.  **Edit an Expired Key**

    If a key has expired, edit it as follows:

    ```
    gpg --edit-key <KEY_ID>
    ```

    Replace `<KEY_ID>` with the actual ID (e.g., `1FEE445AFBB262B5`).
3.  **Change Key Expiry**

    In the GPG interactive shell, type:

    ```
    expire
    ```

    Provide the new expiration period when prompted.
4.  **Export the Updated Key**

    After updating, export the key:

    ```
    gpg --armor --export <KEY_ID> > <FILE_NAME>.asc
    ```

    Example: `gpg --armor --export 1FEE445AFBB262B5 > sunbird.asc`
5.  **Import an Updated GPG Key**

    To import the updated key:

    ```
    gpg --import <FILE_NAME>.asc
    ```

    Example: `gpg --import sunbird.asc`

