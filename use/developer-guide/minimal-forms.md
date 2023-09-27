---
description: >-
  Minimal forms that should be configured for mobile build to create by any
  adopter
---

# Minimal forms

**Minimal forms**&#x20;

Sunbird can be customized and adapted by developers to suit their needs. In order to adapt Sunbird to work with different systems, there are certain forms that need to be configured in mobile.&#x20;

1. _**User type selection**_

The first form we must use here is user type selection.  This Form is used for giving labels and images for the user type selection on the onboarding of users.

<details>

<summary>Form Read API request:</summary>

```
"request": {
  "type": "config",
  "subType": "userType_v2",
  "action": "get",
  "component": "app"
}
```

</details>

<details>

<summary>Form Read API response:</summary>

```
{
                     "code": "teacher",
                     "name": "Teacher",
                     "formConfig": {
                         "request": {
                             "type": "profileConfig",
                             "subType": "default",
                             "action": "get"
                         },
                         "url": "/api/data/v1/form"
                     },
                     "translations": "{\"en\":\"Teacher\",\"as\":\"শিক্ষক\",\"bn\":\"শিক্ষক\",\"gu\":\"શિક્ષક\",\"hi\":\"शिक्षक\",\"kn\":\"ಶಿಕ್ಷಕ/ಕಿ\",\"mr\":\"शिक्षक\",\"or\":\"ଶିକ୍ଷକ\",\"pa\":\"ਅਧਿਆਪਕ\",\"ta\":\"ஆசிரியர்\",\"te\":\"ఉపాధ్యాయుడు\",\"ur\":\"استاد\"}",
                     "image": "ic_teacher.svg",
                     "ambiguousFilters": [
                         "teacher",
                         "instructor"
                     ],
                     "searchFilter": [
                         "Teacher",
                         "Instructor"
                     ],
                     "attributes": {
                         "mandatory": [
                             "board",
                             "medium",
                             "gradeLevel"
                         ],
                         "optional": [
                             "subject"
                         ]
                     }
                 }

```

</details>

In the user onboarding, users can select their role through this page.

2\. _**Framework config**_

&#x20;  The second form we must use is framework config. This Form is used for getting the framework details.

<details>

<summary>Form Read API request:</summary>

```
"request": {
       "type": "config",
       "subType": "frameworkCategory",
       "action": "get",
       "component": "app"
   }
```

</details>

<details>

<summary>Form Read API response:</summary>

```
{
   "id": "api.form.read",
   "params": {
       "resmsgid": "e11a28b8-ae2a-4bef-a70b-55643616bf6f",
       "msgid": "bc62b4dc-b623-465d-9995-c366bf7a73da",
       "status": "successful"
   },
   "responseCode": "OK",
   "result": {
       "form": {
           "type": "config",
           "subtype": "frameworkcategory",
           "action": "get",
           "component": "app",
           "framework": "*",
           "data": {
               "templateName": "frameworkCategory",
               "action": "get",
               "fields": [
                   {
                       "code": "category1",
                       "label": "{\"en\":\"Board\"}",
                       "placeHolder": "{\"en\":\"Selected Board\"}",
                       "frameworkCode": "board",
                       "supportedUserTypes": [
                           "teacher",
                           "student",
                           "administrator",
                           "parent",
                           "other"
                       ]
                   },
                   {
                       "code": "category2",
                       "label": "{\"en\":\"Medium\"}",
                       "placeHolder": "{\"en\":\"Selected Medium\"}",
                       "frameworkCode": "medium",
                       "supportedUserTypes": [
                           "teacher",
                           "student",
                           "parent",
                           "other"
                       ]
                   },
                   {
                       "code": "category3",
                       "label": "{\"en\":\"Class\"}",
                       "placeHolder": "{\"en\":\"Selected Class\"}",
                       "frameworkCode": "gradeLevel",
                       "supportedUserTypes": [
                           "teacher",
                           "student",
                           "parent",
                           "other"
                       ]
                   },
                   {
                       "code": "category4",
                       "label": "{\"en\":\"Subject\"}",
                       "placeHolder": "{\"en\":\"Selected Subject\"}",
                       "frameworkCode": "subject",
                       "supportedUserTypes": [
                           "teacher",
                           "student",
                           "parent",
                           "other"
                       ]
                   }
               ]
           },
           "created_on": "2022-11-17T09:05:04.872Z",
           "last_modified_on": "2022-12-08T11:01:27.862Z",
           "rootOrgId": "*"
       }
   },
   "ts": "2023-01-27T04:51:06.808Z",
   "ver": "1.0"
}

```

</details>

By implementing these forms, developers can seamlessly integrate Sunbird with different platforms, making it easier for users to access and utilize the application.

\
