# Folder Structure

ML Core Service folder structure is designed to organize the different modules and files that constitute the core service of the Learn application. It follows a modular approach, facilitating easy management and development of the service.

### The structure is as follows

```
.
├── config
│   └── db
├── controllers
│   ├── v1
│   └── v2
├── generics
│   ├── constants
│   ├── helpers
│   ├── http-status-codes
│   ├── kafka
│   ├── middleware
│   │   └── validator
│   └── services
├── healthCheck
├── keycloak-public-keys
├── locales
├── migrations
├── models
├── module
│   ├── admin
│   │   └── validator
│   ├── app-releases
│   │   └── validator
│   ├── apps
│   │   └── validator
│   ├── certificateBaseTemplates
│   │   └── validator
│   ├── certificateTemplates
│   │   └── validator
│   ├── cloud-services
│   │   ├── aws
│   │   │   └── validator
│   │   ├── azure
│   │   │   └── validator
│   │   ├── files
│   │   │   └── validator
│   │   └── gcp
│   │       └── validator
│   ├── email
│   │   └── validator
│   ├── entities
│   │   └── validator
│   ├── entityTypes
│   ├── files
│   ├── forms
│   │   └── validator
│   ├── programUsers
│   ├── programs
│   │   └── validator
│   ├── solutions
│   │   └── validator
│   ├── static-links
│   │   └── validator
│   ├── user-extension
│   │   └── validator
│   ├── user-profile
│   │   └── validator
│   ├── user-roles
│   │   └── validator
│   └── users
│       └── validator
├── release-notes
├── routes
├── template
└── test
```

#### config

Within this folder, you can find configuration files specific to the core service, such as database configuration and other settings.

#### controllers

The controllers folder contains various modules representing the application's endpoints or routes. It is organized into different versions, denoted as "v1" and "v2," to allow for backward compatibility and feature evolution.

#### generics

This folder is dedicated to generic utilities and helper functions utilized throughout the core service. It includes subdirectories for constants, helpers, HTTP status codes, Kafka-related code, middleware (e.g., request validation), and services.

#### healthCheck

This folder is designated to hold files that pertain to health checks or monitoring endpoint, ensuring the service's health and availability is monitored effectively.

#### locales:

The locales folder contains language-specific translation files that enable internationalization and localization for the service.

#### migrations

This folder houses database migration scripts, enabling smooth transitions between different versions of the database schema.

#### models

This folder contains the data models and database schema definitions for the core service.

#### module

The "module" folder consists of individual folders for each controller. Within each controller folder, there is a "helper" file that contains all the business logic for that specific controller. Additionally, there is a "validator" folder dedicated to API validation, ensuring that incoming data meets the required criteria and is sanitized appropriately.

#### release-notes

This folder contains release notes or changelogs that document the changes made in each version of the core service.

#### routes

The "routes" folder contains a single file named "index" that serves as the central location for all routes in the core service. These routes are created dynamically, making it a dynamic and flexible approach to managing the service's endpoints.

#### template

This folder is intended for storing templates
