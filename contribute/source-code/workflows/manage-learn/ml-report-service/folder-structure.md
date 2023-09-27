# Folder Structure

ML Reports Service folder structure is designed to organize the different modules and files that constitute the core service of the Learn application. It follows a modular approach, facilitating easy management and development of the service.

### The structure is as follows

```
.
├── ansible
├── common
├── config
├── controllers
│   └── v1
├── healthCheck
├── helper
├── middleware
├── public
│   ├── css
│   └── images
├── release-notes
├── routes
├── test
└── views

```

#### ansible

Within this folder, users can find files pertaining to the orchestration of infrastructure and configuration processes, potentially utilizing Ansible. These files may relate to tasks like deployment or the setup of servers.

#### common

This folder is dedicated to generic utilities and helper functions utilized throughout the core service. It includes subdirectories for constants, helpers, utils and druid queries.

#### config

Within this folder, you can find configuration files specific to the core service, such as database configuration and other settings.

#### controllers

The controllers folder contains various modules representing the application's endpoints or routes. It is organized into different versions, denoted as "v1" and "v2," to allow for backward compatibility and feature evolution.

#### healthCheck

This folder is designated to hold files that pertain to health checks or monitoring endpoint, ensuring the service's health and availability is monitored effectively.

#### helper

The "helper" folder consists of individual folders for each controller. Within each controller folder, there is a "helper" file that contains all the business logic for that specific controller.

#### release-notes

This folder contains release notes or changelogs that document the changes made in each version of the core service.

#### routes

The "routes" folder contains a single file named "index" that serves as the central location for all routes in the core service. These routes are created dynamically, making it a dynamic and flexible approach to managing the service's endpoints.

#### test

The test folder contains test files, including unit tests and integration tests to ensure the reliability and correctness of the core service.

#### views

This directory is likely designated for view templates or files used in rendering the user interface, separating the visual representation from the underlying logic.
