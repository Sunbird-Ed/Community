---
description: Cassandra database used in Form service
---

# Data model

| Column Name        | Data Type | Description                                             | Sample Data                                          |
| ------------------ | --------- | ------------------------------------------------------- | ---------------------------------------------------- |
| id                 | string    | Represents an API uniquely                              | api.form.create                                      |
| type\*             | varchar   | Represents the type of form being created               | content, user, forum, app, program-dashboard, config |
| subtype\*          | varchar   | Represents the sub-category of form being created       | course, collection, textbook, resource, login        |
| action\*           | varchar   | Represents the user action on the form                  | ilter, create, get, save, review , search            |
| component\*        | varchar   | Represents the consumption platform for the form        | portal, mobile                                       |
| root\_org          | varchar   | Represents the form accesabilty to all (\*) or specific | \*, 123213232332323                                  |
| framework          | varchar   | Represents the form accesabilty to all (\*) or specific | \*, 121324324274724                                  |
| created\_on        | timestamp | created time                                            | 2023-04-13T11:08:21.260Z                             |
| last\_modified\_on | timestamp | modified time                                           | 2023-04-13T12:35:52.143Z                             |
