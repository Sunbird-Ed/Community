---
description: Cassandra database used in Form service
---

# Data model



| Column Name        | Data Type | Description                                                      | Sample Data                                                                                                                                                                                |
| ------------------ | --------- | ---------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id                 | string    | Represents an API uniquely                                       | api.form.create                                                                                                                                                                            |
| ver                | string    | Represents the version of the API which was used                 | 1.0                                                                                                                                                                                        |
| ts                 | integer   | Represents the EPOCH (UTC) timestamp in milliseconds since EPOCH | 2023-04-13T11:04:52.333Z                                                                                                                                                                   |
| params             | object    |                                                                  | <p>{</p><p>        "resmsgid": "bb6c9650-5a04-44e8-9077-452ef7aa5cdf",</p><p>        "msgid": "6f64bd31-cf55-4f80-9f13-d19a799fe6fa",</p><p>        "status": "successful"</p><p>    }</p> |
| msgid              | string    | Represents the unique ID of the message being sent               | 6f64bd31-cf55-4f80-9f13-d19a799fe6fa                                                                                                                                                       |
| did                | string    | Represents the device UUID from which API is called              | bb6c9650-5a04-44e8-9077-452ef7aa5cdf                                                                                                                                                       |
| type\*             | varchar   | Represents the type of form being created                        | content, user, forum, app, program-dashboard, config                                                                                                                                       |
| subtype\*          | varchar   | Represents the sub-category of form being created                | course, collection, textbook, resource, login                                                                                                                                              |
| action\*           | varchar   | Represents the user action on the form                           | ilter, create, get, save, review , search                                                                                                                                                  |
| component\*        | varchar   | Represents the consumption platform for the form                 | portal, mobile                                                                                                                                                                             |
| root\_org          | varchar   | Represents the form accesabilty to all (\*) or specific          | \*, 123213232332323                                                                                                                                                                        |
| framework          | varchar   | Represents the form accesabilty to all (\*) or specific          | \*, 121324324274724                                                                                                                                                                        |
| created\_on        | timestamp | created time                                                     | 2023-04-13T11:08:21.260Z                                                                                                                                                                   |
| last\_modified\_on | timestamp | modified time                                                    | 2023-04-13T12:35:52.143Z                                                                                                                                                                   |
