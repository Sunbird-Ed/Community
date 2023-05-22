---
description: >-
  This guide provides a comprehensive overview of the Form Configurations, which
  are specifically designed for the mobile version of Sunbird.
---

# Mobile form configurations

The Form Configurations are a set of predefined forms that enable users to easily create, modify, and manage content on the mobile version of Sunbird. These forms are designed to be simple and intuitive, making it easy for users to quickly create and manage content on the go.

In this guide, we will explore the various features and functionalities of Form Configurations and provide instructions on how to use them effectively.

{% swagger method="post" path="" baseUrl="User type config" summary="This Form is used for giving labels and images for the user type selection on the onboarding of users." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config",&#x20;

"subType": "userType\_v2",&#x20;

"action": "get",&#x20;

"component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
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

The user can modify the mandatory and optional fields of the form configuration according to their needs. In this example, the "board", "medium", and "gradeLevel" fields are mandatory, while the "subject" field is optional. The user can add or remove fields from the configuration as required.

The user can use the "ambiguousFilters" and "searchFilter" fields to specify the search terms that are associated with the form. In this example, "teacher" and "instructor" are the ambiguous filters, while "Teacher" and "Instructor" are the search filters.

Overall, the form config response provides a lot of flexibility and customization options for users to tailor the form to their specific needs and preferences.

![](../../.gitbook/assets/ksnip\_20230504-143920.png)

The user can customize the image and labels that is displayed for the form by modifying the fields. In this example, the "ic\_teacher.svg" image is used for the "Teacher" profile.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Framework config" summary="This Form is used for getting various framework category details." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config",&#x20;

"subType": "frameworkCategory",&#x20;

"action": "get",&#x20;

"component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
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

This form is designed to provide a framework for selecting educational categories such as board, medium, class, and subject. Each category has a code, label, placeholder, frameworkCode, and supportedUserTypes.&#x20;

![](<../../.gitbook/assets/processed-3013f805-7c53-4bfb-b528-08c840595bda\_pT6PG12j (2).jpeg>)![](../../.gitbook/assets/processed-6e1f0eec-8831-4aa4-9977-ef191fcafbde\_T23xUMH6.jpeg)

The supportedUserTypes specify which types of users can access the form, including teachers, students, parents, and others. This form is dynamic and can be customized to accommodate different categories or additional user types.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Web view version config" summary="This form is used to get the web view version of the mobile application when it is opened." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config",&#x20;

"subType": "webview\_version",&#x20;

"action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"type": "config",
         "subtype": "webview_version",
         "action": "get",
         "component": "*",
         "framework": "*",
         "data": {
             "templateName": "webview_version",
             "action": "get",
             "fields": [
                 {
                     "version": "43"
                 }
             ]
         }

```
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Admin user home page labels config" summary="This form is used to give labels on the Learn, Manage, and Act section on the admin user home page" %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config",&#x20;

"subType": "adminHome",&#x20;

"action": "get",&#x20;

"component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
       "code": "program",
       "title": "{\"en\":\"Programs\"}",
       "search": {}
   },
   {
       "code": "project",
       "title": "{\"en\":\"Projects\"}",
       "search": {}
   },
   {
       "code": "observation",
       "title": "{\"en\":\"Observations\"}",
       "search": {}
   }

```

The form configuration includes three codes: "program," "project," and "observation." Each code has a corresponding title that can be used as a label on a page. The titles are currently set to "Programs," "Projects," and "Observations," respectively, and they are available in English language.

These labels are useful for categorizing and organizing data, making it easier to locate and manage specific types of information.

![](../../.gitbook/assets/ksnip\_20230505-171523.png)

If needed, additional labels can be added to the configuration to further categorize data. The search key is currently left blank, indicating that no search functionality is currently implemented for this form. However, it could be added in the future to allow users to search for specific codes or titles.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Login. config" summary="This form is used for login purpose." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config",\
"subType": "login\_v2", "action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"context": "login",
"target": {
  "host": "https://diksha.gov.in",
  "path": "/auth/realms/sunbird/protocol/openid-connect/auth",
  "params": [
    {
      "key": "redirect_uri",
      "value": "https://diksha.gov.in/oauth2callback"
    },
    {
      "key": "response_type",
      "value": "code"
    },
    {
      "key": "scope",
      "value": "offline_access"
    },
    {
      "key": "client_id",
      "value": "android"
    },
    {
      "key": "version",
      "value": "4"
    }
  ]
}
```

The above form configuration code provides the necessary information for a login form. The "context" field specifies that this form is for logging in. The "target" field provides the login page's URL, including the necessary parameters for the authentication process.

The "host" field specifies the domain name of the login page, while the "path" field provides the URL path for the authentication endpoint. The "params" section provides additional parameters needed for authentication, including the redirect URL, response type, scope, client ID, and version.

![](../../.gitbook/assets/ksnip\_20230505-171838.png)

Users can modify this form configuration to customize the login page's appearance and behavior according to their preferences. They can also adjust the parameters in the "params" section to include or exclude specific authentication requirements. Overall, this form configuration provides a straightforward and easy-to-use method for users to log in to a website or application.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="App upgrade" summary="This form will show the reminder to upgrade the application to its latest version." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "app", "subType": "install", "action": "upgrade" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "type": "force",
  "title": "আমি এই কনটেন্টৰ অন্তৰ্গত হেৰোৱা ইমেজ আৰু অ’ডিঅ’ৰ ক্ষেত্ৰত হোৱা সমস্যা সংশোধন কৰিলোঁ। উৎকৃষ্ট অভিজ্ঞতাৰ বাবে, আমি আপোনাক DIKSHA ৰ শেহতীয়া সংস্কৰণটো উন্নীত কৰাৰ পৰামৰ্শ দিওঁ।",
  "desc": "",
  "actionButtons": [
    {
      "action": "yes",
      "label": "এতিয়া আপডেট কৰক",
      "link": "https://play.google.com/store/apps/details?id=in.gov.diksha.app&hl=en"
    }
  ]
}
```

When application needs updation, this form provides the link to update to its latest version.

![](../../.gitbook/assets/ksnip\_20230505-190209.png)

This link can be replaced as per user’s convenience.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Search filter " summary="In the search filter page, this form wll give nine types of filters. Users can change the filters and number of filters, by using this form." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "search", "action": "filter\_v3", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "se_boards",
  "translations": "{\"en\":\"Board/Syllabus\",\"as\":\"ব'ৰ্ড\",\"bn\":\"পর্ষদ\",\"gu\":\"બોર્ડ\",\"hi\":\"बोर्ड\",\"kn\":\"ಮಂಡಳಿ\",\"mr\":\"बोर्ड\",\"or\":\"ବୋର୍ଡ\",\"pa\":\"ਬੋਰਡ\",\"ta\":\"வாரியம்\",\"te\":\"బోర్డు\",\"ur\":\"بورڈ\"}",
  "values": [
    
  ],
  "name": "Board/Syllabus",
  "index": 1
},
{
  "code": "se_gradeLevels",
  "translations": "{\"en\":\"Class\",\"as\":\"শ্ৰেণী\",\"bn\":\"শ্রেনী\",\"gu\":\"વર્ગ\",\"hi\":\"कक्षा\",\"kn\":\"ತರಗತಿ\",\"mr\":\"इयत्ता\",\"or\":\"ଶ୍ରେଣୀ\",\"pa\":\"ਜਮਾਤ\",\"ta\":\"வகுப்பு\",\"te\":\"క్లాసు\",\"ur\":\"کلاس\"}",
  "values": [
    
  ],
  "name": "Class",
  "index": 2
}
```

The form configuration includes two codes: "se\_boards" and "se\_gradeLevels." Each code has a corresponding name and translations, which can be used as labels in filters on a page.

The "se\_boards" code corresponds to a label called "Board/Syllabus," which can be used to categorize information based on the specific board or syllabus it pertains to. The translations for this label are available in multiple languages including English, Assamese, Bengali, Gujarati, Hindi, Kannada, Marathi, Odia, Punjabi, Tamil, Telugu, and Urdu.

The "se\_gradeLevels" code corresponds to a label called "Class," which can be used to categorize information based on the specific grade or class level it pertains to. The translations for this label are also available in multiple languages including English, Assamese, Bengali, Gujarati, Hindi, Kannada, Marathi, Odia, Punjabi, Tamil, Telugu, and Urdu.

![](../../.gitbook/assets/ksnip\_20230505-190525.png)

The "values" key is currently empty, indicating that no specific values have been assigned to these labels. However, values can be added to these labels in the future to help further categorize and organize information based on the specific board/syllabus and class levels.

The "index" key indicates the position of the label in a list or dropdown menu, which can be useful for ordering the labels in a specific way.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="User consent" summary="This form is used to share users’ data with the state." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "user", "subType": "tenantPersonaInfo\_v2", "action": "get", "component": "app" } }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"code": "tenant",
"type": "select",
"templateOptions": {
  "label": "I wish to share my data with:",
  "placeHolder": "Select State/Institution",
  "options": [
    {
      "label": "State (Punjab)",
      "value": "012775810960252928563",
      "index": 1
    },
    {
      "label": "Andra Pradesh",
      "value": "0129109366089728000",
      "index": 2
    },
    {
      "label": "Haryana State",
      "value": "0127674553846579203",
      "index": 3
```

This is a select form field, where users can choose from a dropdown list of options. The form field is configured to allow the user to select which state or institution they wish to share their data with, with the label "I wish to share my data with:".

The form configuration also includes additional template options, such as a placeholder text that appears in the dropdown when no option is selected. The options themselves are defined by the values assigned to each label, such as "012775810960252928563" and "0129109366089728000".

![](../../.gitbook/assets/ksnip\_20230505-191307.png)

One of the advantages of form configuration is its flexibility in allowing users to customize the form to their specific needs. For example, if the dropdown values needed to be changed to organizations instead of states, the label and options could be easily reconfigured. This adaptability can make the form more user-friendly and tailored to the specific use case or audience.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Self declaration" summary="The Form is used for entering the ID requested by the state, board, or org." %}
{% swagger-description %}
**Form Create API:**

{ "request": { "from": "server", "type": "user", "subType": "selfDeclaration\_v3", "action": "submit", "component": "app" } }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "declared-ext-id",
  "fieldName": "Your ID from State/Board/Org",
  "type": "input",
  "templateOptions": {
    "labelHtml": {
      "contents": "<span>$0</span>",
      "values": {
        "$0": "ENTER_ID_AS_REQUESTED_BY_STATE_BOARD_ORG"
      }
    },
    "placeHolder": "ENTER_ID"
  },
  "validations": [
    {
      "type": "pattern",
      "value": "^[^\"',(\\r\\n|\\r|\\n)]*$",
      "message": "SPECIAL_CHARACTERS_NOT_SUPPORTED"
    }
  ]
}
```

The above response describes a configuration for a form, which allows users to input a unique identifier code. The configuration includes several properties such as "code," "fieldName," "type," and "templateOptions" that define the appearance and behavior of the input field.

The "templateOptions" property specifies the label to display for the input field, which is currently set to "ENTER\_ID\_AS\_REQUESTED\_BY\_STATE\_BOARD\_ORG". This label can be customized to reflect the specific type of ID that the user needs to input. The "placeHolder" property provides a placeholder text to be displayed in the input field before any text is entered.

The "validations" property includes a regular expression pattern that restricts the characters that can be entered in the input field. The current pattern allows all characters except for some special characters, and displays a custom error message if any of these unsupported characters are entered.

![](../../.gitbook/assets/ksnip\_20230505-192357.png)

The values from the response above can be configured and use it in the form. If the user wants the form to get School ID, they can put the necessary label instead of “Enter ID requested by State, Board or Org”.

Overall, this form configuration provides flexibility and customization options for users to input a unique identifier code, while ensuring that the entered data meets certain validation criteria.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Notifications" summary="This form will list all the notifications for the user. Users can see all the notifications by clicking on the bell notification icon on the mobile app." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "notification", "action": "get", "component": "app" } }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"action": {
  "template": {
    "ver": "4.3.0",
    "data": {
      "title": "you have been added to 123 group by td37@yopmail.com"
    },
    "type": "JSON"
  },
  "createdBy": {
    "name": "td37@yopmail.com",
    "id": "a1cbdaa3-ee20-4bdc-94c0-8b8672e6a4c2",
    "type": "user"
  },
  "additionalInfo": {
    "group": {
      "name": "123",
      "id": "e140251b-ac26-4e46-81c7-b3cefaccd86e"
    }
  },
  "type": "member-added",
  "category": "group"
}
```

![](../../.gitbook/assets/ksnip\_20230505-192838.png)

Notifications will list down and shows title from the response. This makes users’ life easier by allowing them to show their notifications similar to this.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Location mapping config" summary="This form is used for showing the dropdown list of location values. This form is called location mapping config and using this config, location values are selected by users, to update the profile." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "profileConfig\_v2", "subType": "default", "action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "state",
  "type": "select",
  "templateOptions": {
    "labelHtml": {
      "contents": "<span>$0&nbsp;<span class=\"required-asterisk\">*</span></span>",
      "values": {
        "$0": "State"
      }
    },
    "placeHolder": "Select State",
    "multiple": false,
    "dataSrc": {
      "marker": "STATE_LOCATION_LIST",
      "params": {
        "useCase": "SIGNEDIN_GUEST"
      }
    }
  },
  "validations": [
    {
      "type": "required"
    }
  ]
}
```

![](../../.gitbook/assets/ksnip\_20230508-124157.png)

This is a form configuration for a select field that allows users to choose a state from a list. Here are some ways in which a user can improvise this form configuration and use it according to their convenience:

1\. Change the field type: The user can change the "type" field from "select" to other types such as "radio", "checkbox", or "text" based on their requirements.

2\. Modify the label and placeholder text: The user can modify the "labelHtml" and "placeHolder" fields to change the label and placeholder text of the select field. In this example, the label is "State" with an asterisk to indicate it is a required field, and the placeholder text is "Select State". The user can customize these values as per their needs.

3\. Customize the data source: The user can customize the "dataSrc" field to change the data source for the select field. In this example, the data source is specified using a "marker" and "params". The user can modify these values to use a different data source or provide additional parameters for the existing data source.

4\. Add or modify validation rules: The user can add or modify the validation rules specified in the "validations" field. In this example, the only validation rule is to check if the field is required. The user can add other validation rules such as minimum and maximum length, regular expressions, or custom validation functions to ensure data integrity.

Overall, this form configuration provides a lot of flexibility and customization options for users to tailor the select field to their specific needs and preferences. The values from the response can be taken as labels in the form and can be altered and used as per the user's requirements.


{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Content feedback" summary="This form is used for displaying the contents/criteria for the checkboxes on the feedback page. The feedback will be provided through this page and this form makes it easier by providing the opportunity to change these contents." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "contentfeedback", "subType": "en", "action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "key": "CONTENT_INACCURATE",
  "idx": 1,
  "value": "Content is inaccurate"
},
{
  "key": "CONTENT_NOT_DISPLAYED",
  "idx": 2,
  "value": "Content is not displayed properly"
}
```

![](<../../.gitbook/assets/ksnip\_20230508-124624 (1).png>)

This form configuration consists of two options that users can select to provide feedback on the content of a page or application. The "key" field corresponds to the feedback option, the "idx" field represents the order of the option in the list, and the "value" field contains the text that will be displayed to the user.

Here are some ways in which a user can improvise this form configuration and use it according to their convenience:

1\. Add or remove feedback options: The user can add or remove feedback options by modifying the "key" and "value" fields. In this example, there are two options - "CONTENT\_INACCURATE" and "CONTENT\_NOT\_DISPLAYED". The user can add new options such as "LOADING\_ISSUES" or "POOR\_NAVIGATION" or remove the existing options.

2\. Rearrange the order of options: The user can rearrange the order of feedback options by modifying the "idx" field. In this example, "CONTENT\_INACCURATE" is assigned an index of 1, and "CONTENT\_NOT\_DISPLAYED" is assigned an index of 2. The user can change the index values to change the order of options.

3\. Modify the display text: The user can modify the "value" field to change the text that will be displayed to the user. In this example, the display text for "CONTENT\_INACCURATE" is "Content is inaccurate", and the display text for "CONTENT\_NOT\_DISPLAYED" is "Content is not displayed properly". The user can customize these values to use different display text for each feedback option.

Overall, this form configuration allows for easy customization of feedback options for users. The "key" field corresponds to the feedback option and can be modified to add new options or remove existing ones. The "value" field contains the text that will be displayed to the user and can be customized. The "idx" field represents the order of the feedback option and can be used to rearrange the order of options.\

{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Deep link " summary="This form is used to get the deep link for QRcode and splash screen." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "deeplink", "action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
 "code": "primaryCategory",
 "values": [
     "Collection",
     "Resource",
     "Content Playlist",
     "Course",
     "Course Assessment",
     "Digital Textbook",
     "eTextbook",
     "Explanation Content",
     "Learning Resource",
     "Practice Question Set",
     "Teacher Resource",
     "LessonPlan",
     "FocusSpot",
     "Learning Outcome Definition",
     "Curiosity Questions",
     "MarkingSchemeRubric",
     "ExplanationResource",
     "ExperientialResource",
     "Practice Resource",
     "TVLesson"
 ],
 "type": "default"
}
```



This form configuration defines the possible values for the "primaryCategory" field in a form. It provides a list of options that the user can choose from, and the options are pre-defined in the "values" field of the configuration. The user can only select one option from the list as the configuration specifies the type as "default", which allows only one selection at a time.

The "primaryCategory" field is a categorical variable, and this configuration makes it easier for the user to select a suitable value from the list. The user can add new values or remove existing ones from the list according to their needs.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Managed User" summary="This form is used to add another managed user. We can enter the new user to be added using this form." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "user", "subType": "manageduser", "action": "create", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "name",
  "type": "input",
  "templateOptions": {
    "label": "FULL_NAME",
    "placeholder": "ENTER_USER_NAME"
  },
  "validations": [
    {
      "type": "required",
      "value": true,
      "message": "NAME_IS_REQUIRED"
    }
  ]
}
```

![](../../.gitbook/assets/ksnip\_20230508-125224.png)

The above configuration code is for an input field that is used to collect a user's full name. The field is labeled "FULL\_NAME" and the placeholder text reads "ENTER\_USER\_NAME".

The "validations" section ensures that the user must enter a value in the field, as indicated by the "required" validation type.

This form configuration can be easily customized by changing the labels to fit the needs of the user or application. The input type can also be modified to support different types of data entry. Overall, this form configuration is a simple and effective way to gather important user information.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Pdf Player" summary="The form is used to choose the type of player and open the corresponding player." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "pdfPlayer\_v2", "action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"form": {
  "type": "config",
  "subtype": "pdfplayer_v2",
  "action": "get",
  "component": "*",
  "framework": "*",
  "data": {
    "templateName": "pdfPlayer_v2",
    "action": "get",
    "fields": [
      {
        "name": "pdfPlayer",
        "code": "pdf",
        "values": [
          {
            "isEnabled": true
          }
        ]
      },
      {
        "name": "epubPlayer",
        "code": "epub",
        "values": [
          {
            "isEnabled": true
          }
        ]
      },
      {
        "name": "videoPlayer",
        "code": "video",
        "values": [
          {
            "isEnabled": true
          }
        ]
      },
      {
        "name": "qumlPlayer",
        "code": "quml",
        "values": [
          {
            "isEnabled": true
          }
        ]
      }
    ]
```

The above form configuration code provides information about a PDF player form. The "type" field specifies that this is a configuration form, while the "subtype" field indicates that this is a PDF player form of version 2.

The "action" field indicates that this form is used for getting information about the PDF player. The "component" and "framework" fields are set to "\*" to indicate that they are not specified.

The "data" field contains information about the PDF player form's fields, including the PDF player, EPUB player, video player, and Quml player. The "isEnabled" parameter is set to "true" for each field, indicating that they are all enabled.

Based on the type of content, the appropriate player will be selected and opened. Users can customize the PDF player form by modifying the values of the fields or by adding new fields to meet their specific requirements.

Overall, this form configuration provides a straightforward and efficient method for users to access and display PDF content using a player.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Utility popups" summary="The form will provide popups for some use cases such as experience switch between classic and new App experiences." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "utility", "action": "get", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"fields": [
  {
    "name": "Course BatchEnd Config",
    "code": "batchEndTimerConfig",
    "config": {
      "batchEndDateTimer": "2"
    }
  },
  {
    "name": "Experience Switch Popup Config",
    "code": "experienceSwitchPopupConfig",
    "config": {
      "isEnabled": true
    }
  }
]
```

![](../../.gitbook/assets/ksnip\_20230508-125623.png)

The above form configuration code provides information about two fields, namely "Course BatchEnd Config" and "Experience Switch Popup Config". The "code" field is used to identify each field uniquely.

The "config" field contains information about the configuration settings for each field. In the case of the "Course BatchEnd Config" field, the "batchEndDateTimer" parameter is set to "2". This parameter determines the time interval after which the batch should end.

Similarly, in the case of the "Experience Switch Popup Config" field, the "isEnabled" parameter is set to "true". This parameter enables the experience switch popup, which allows users to switch between different versions of the application.

Users can modify the values of these fields to suit their needs. For example, they can change the "batchEndDateTimer" parameter to a different value to set a different time interval for the batch end, or they can disable the "Experience Switch Popup" by setting the "isEnabled" parameter to "false".

Overall, this form configuration provides users with the flexibility to customize the configuration settings for various use cases, making their life easier by providing a more personalized experience.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Vendor applications" summary="This form provides the supported third-party reader applications to open any content." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "vendorapps", "action": "get", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"form": {
  "type": "config",
  "subtype": "vendorapps",
  "action": "get",
  "component": "app",
  "framework": "*",
  "data": {
    "templateName": "vendorapps",
    "action": "get",
    "fields": [
      {
        "name": "Google Bolo",
        "logo": "https://img.icons8.com/doodle/48/000000/league-of-legends.png",
        "provider": {
          "name": "Google",
          "copyright": "",
          "license": ""
        },
        "android": {
          "packageId": "io.ionic.sender",
          "appVersion": "54",
          "compatibilityVer": ""
        },
        "ios": {
          "packageId": "",
          "appVersion": "",
          "urlScheme": "",
          "compatibilityVer": ""
        },
        "target": {
          "mimeType": [
            "application/pdf"
          ],
          "primaryCategory": [
            "LearningResource"
          ]
        }
      }
    ]
  },
  "created_on": "2021-03-18T10:02:07.932Z",
  "last_modified_on": "2021-03-19T10:34:56.264Z",
  "rootOrgId": "*"
}
```

![](../../.gitbook/assets/ksnip\_20230508-125925.png)

This form configuration is used to display a list of vendor apps and their associated details. In this specific case, the form displays information about the Google Bolo app, such as its logo, provider, and app version for both Android and iOS. It also specifies the file type and primary category that this app is able to handle. Users can use this information to open specific content using the Google Bolo app and can customize the configuration to suit their needs by updating the packageId, appVersion, and other details as necessary.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Create project" summary="The form will be used to create projects. The labels will be provided according to the configuration this form provides. It will make user’s life easier by allowing them to change the labels in the form according to their preferences." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "user", "subType": "project", "action": "create" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "field": "title",
  "label": "Project Title (mandatory)",
  "labelTranslations": "{\"en\":\"Project Title (mandatory)\",\"hi\":\"शीर्षक\"}",
  "value": "",
  "visible": true,
  "editable": true,
  "input": "text",
  "validation": {
    "required": true
  },
  "max": 50,
  "hint": "Name your project",
  "hintTranslations": "{\"en\":\"Name your project\"}"
}
```

![](../../.gitbook/assets/ksnip\_20230508-130112.png)

This form configuration specifies a field called "Project Title" that is mandatory for the user to fill in. The label for this field is provided in both English and Hindi translations. The field is currently empty and can be edited by the user. The input type for this field is "text" and it has a maximum character limit of 50. Additionally, there is a hint for the user to provide a title for their project. This hint is also provided in English. Overall, this form configuration allows for easy customization of the label and hint text to fit the user's language preferences.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Create task" summary="The form is used to get labels for the task creation page." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "user", "subType": "project", "action": "createTask" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "field": "name",
  "label": "Name",
  "labelTranslations": "{\"en\":\"Name\",\"hi\":\"नाम\"}",
  "value": "",
  "visible": true,
  "editable": true,
  "input": "text",
  "validation": {
    "required": true
  }
}
```

The response API includes configuration for the "Name" field on a create task page, with labels provided in both English and Hindi. This field is editable and visible to the user, and its input is limited to text with a validation requirement of being mandatory. Users can customize the label according to their preferences, making it easier to navigate and use the create task page
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Category labels" summary="In the browse other categories section of the home page, the labels are being given using this configuration." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "category", "subType": "targetedCategory", "action": "homeListing" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"form": {
  "type": "category",
  "subtype": "targetedcategory",
  "action": "homelisting",
  "component": "*",
  "framework": "*",
  "data": {
    "templateName": "defaultTemplate",
    "action": "homeListing",
    "fields": {
      "cbse": {
        "teacher": [
          {
            "name": "observation",
            "icon": {
              "web": "assets/images/mask-image/observation_category.png",
              "app": "assets/imgs/ic_observation_category.png"
            }
          },
          {
            "name": "project",
            "icon": {
              "web": "",
              "app": "assets/imgs/ic_project.svg"
            }
          }
        ]
      },
      "ekstep_ncert_k-12": {
        "teacher": [
          {
            "name": "observation",
            "icon": {
              "web": "assets/images/mask-image/observation_category.png",
              "app": "assets/imgs/ic_observation_category.png"
            }
          }
        ]
      },
      "tn_k-12_5": {
        "teacher": [
          {
            "name": "observation",
            "icon": {
              "web": "assets/images/mask-image/observation_category.png",
              "app": "assets/imgs/ic_observation_category.png"
            }
          }
        ]
      },
      "cg_k-12": {
        "teacher": [
          {
            "name": "observation",
            "icon": {
              "web": "assets/images/mask-image/observation_category.png",
              "app": "assets/imgs/ic_observation_category.png"
            }
          }
        ]
      },
      "pb_k-12": {
        "teacher": [
          {
            "name": "observation",
            "icon": {
              "web": "assets/images/mask-image/observation_category.png",
              "app": "assets/imgs/ic_observation_category.png"
            }
          }
        ]
      }
    }
```

![](../../.gitbook/assets/ksnip\_20230508-130346.png)

The form configuration contains a category-based selection component with a targeted category subtype. The response data specifies different categories and their associated subcategories. The category and subcategory names are used as labels in the "Browse other categories" section of the component. Users can customize these labels to better suit their needs. The form also contains additional data such as the template name, creation and modification dates, and root organization ID.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Segmentation" summary="This form is used to create segmentation for notifications and banner." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "segmentation\_v2", "action": "get", "component": "app" }


{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "filter": {
    "offset": 0,
    "fields": [
      
    ],
    "filters": {
      "keywords": [
        "NISHTHASEC"
      ],
      "status": "Live",
      "contentType": "Course",
      "channel": [
        "01246375399411712074"
      ],
      "batches.enrollmentType": "open",
      "softConstraints": "{}"
    },
    "exists": [
      
    ],
    "sort_by": {
      
    }
  }
}
```

![](../../.gitbook/assets/ksnip\_20230508-130619.png)

Suppose user selects State(Tamilnadu), Board as English and Grade as Class 1, then for this segment, the banners are shown. Similarly for particular set of values, particular notifications are shown. So using this form we can target specific users and show the banners and notifications.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Supported url regex" summary="This form is used for getting the deep link regex and dial code regex." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "supportedUrlRegex", "action": "get" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "name": "Dialcode parser",
  "code": "dialcode",
  "values": "(\/dial\/(?<sunbird>[a-zA-Z0-9]+)|(\/QR\/\\?id=(?<epathshala>[a-zA-Z0-9]+)))"
},
{
  "name": "Identifier parser",
  "code": "identifier",
  "values": "(?:\/(?:resources\/play\/content|play\/quiz)\/(?<quizId>\\w+))|(?:\/play\/(?:content|collection)\/(?<contentId>\\w+))|(?:\/(?:explore-course|learn)\/course\/(?<courseId>\\w+))"
}
```

The "Dialcode parser" is particularly useful for applications that deal with alphanumeric codes, such as voucher codes or product codes. By customizing the regular expression in the "values" field, developers can easily extract the codes from URLs and use them to perform specific actions within their application.

Similarly, the "Identifier parser" is a versatile tool that can be used to extract information about courses, quizzes, or other types of content from URLs. By customizing the regular expression in the "values" field, developers can easily extract the relevant information from URLs and use it to provide a better user experience within their application.

Overall, the form config provided in the code block gives developers the flexibility to create custom URL parsers that suit their specific needs. By leveraging the power of regular expressions, developers can make their web applications more efficient, user-friendly, and easy to use.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Content filter" summary="This form is used to get the supported content filter for Library, Course, Download and Dialcode." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "content\_v2", "action": "filter" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "primaryCategory",
  "values": [
    "Course",
    "Learning Resource",
    "Explanation Content",
    "Teacher Resource",
    "Content Playlist",
    "Digital Textbook",
    "Practice Question Set",
    "eTextBook",
    "Course Assessment"
  ],
  "name": "library"
}
```

![](../../.gitbook/assets/ksnip\_20230508-130905.png)

The 'values' in the response represent the different types of content that can be filtered in the library section. Users can select the filters they need from the available options and use them to refine their search. The 'name' field specifies the category of the filter, in this case, it is the library.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="External ID verification." summary="The form is used to verify the teacher profile." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "user", "subType": "externalIdVerification", "action": "onboarding", "from": "server" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "externalIdVerificationLabels",
  "name": "externalIdVerification",
  "range": [
    {
      "headerLabel": "Are you a government school teacher ?",
      "fieldLabel": "Enter your teacher ID for verification",
      "popupHeaderLabel": "User Verification",
      "verificationSuccessfulLabel": "Teacher profile verified successfully",
      "incorrectIDLabel": "The ID entered is incorrect. Enter the ID again",
      "verficationFailureLabel": "Could not verify teacher profile as the ID entered is incorrect"
    }
  ]
}
```

The form configuration provides a set of labels for the external ID verification process, specifically for verifying teacher profiles. The range field includes header, field, and popup labels for the verification process, including successful and unsuccessful verification labels. This simplifies the process for users and ensures that all the necessary information is available for verifying teacher profiles.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Support form" summary="The form is used to provide a text area for describing user’s issues." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "dynamicform", "subType": "support\_v2", "action": "get", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "details",
  "type": "textarea",
  "context": null,
  "templateOptions": {
    "label": "Tell us more",
    "placeHolder": "Enter Details"
  },
  "validations": [
    {
      "type": "maxLength",
      "value": 1000
    }
  ]
}
```

![](../../.gitbook/assets/ksnip\_20230508-132349.png)

This form configuration provides a text area field with a maximum length of 1000 characters for users to provide additional details related to their support request. The label "Tell us more" and placeholder "Enter Details" help users understand what information is required in the text area field. The validation ensures that the input does not exceed the maximum allowed length. This form can be customized as per the user's requirements to suit their needs for submitting any type of request, complaint, or feedback.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Board contact info" summary="This form is used to provide contact details of all boards for any support user needs." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "form", "subType": "boardContactInfo", "action": "get", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "id": "up_k-12",
  "code": "board",
  "name": "Uttar Pradesh",
  "message": "(between 9 AM to 6 PM from Monday to Friday)",
  "contactinfo": {
    "number": "18001800666",
    "email": null
  }
}
```

![](../../.gitbook/assets/ksnip\_20230508-132536.png)

The "name" field specifies the name of the board, and the "message" field indicates the hours during which the board can be contacted. The "contactinfo" object includes a phone number and email address for users to reach out for any queries.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Content Request" summary="This form is used for requesting more content with more filters used." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "dynamicForm", "subType": "contentRequest", "action": "submit", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "board",
  "type": "select",
  "templateOptions": {
    "placeHolder": "Select Board",
    "multiple": false,
    "dataSrc": {
      "marker": "ACTIVE_CHANNEL.SUGGESTED_FRAMEWORK_LIST.MAPPED_TO_FRAMEWORKCATEGORIES",
      "params": {
        "relevantTerms": [
          "CBSE"
        ]
      }
    }
  },
  "validations": [
    {
      "type": "required"
    }
  ]
}
```

The form allows the user to select the educational board for which they want to request content. The options for the board field are dynamically populated using the data source specified in the form configuration. In this case, the options are fetched from a system that maps the suggested frameworks to framework categories and filters for the relevant term "CBSE". The user can only select one option as the field does not allow multiple selections. The form also includes a required validation to ensure the user selects an option before submitting the form. The form is a part of the "contentrequest" subtype and can be used to request specific educational content based on the selected board.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Consent declaration" summary="This form is used for asking consent from users to share details." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "dynamicForm", "subType": "consentDeclaration\_v3", "action": "submit", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "code": "name",
  "type": "text",
  "templateOptions": {
    "placeHolder": "{\"en\":\"User name :\"}",
    "dataSrc": {
      "marker": "SERVER_PROFILE",
      "params": {
        "categoryCode": "firstName"
      }
    }
  }
}
```

![](../../.gitbook/assets/ksnip\_20230508-132959.png)

The form configuration provided describes a field for capturing the user's name. The field is of type "text" and has a placeholder that displays "User name :" in English. The placeholder is defined using a JSON object with the "en" key, which specifies the language code.

The "dataSrc" property of the field refers to a data source that provides the value for the field. In this case, the data source is a marker called "SERVER\_PROFILE", which may be used to fetch data related to the user's profile from the server. The "params" property specifies additional parameters to be passed to the server, such as the category code for the user's first name.

This form configuration can be used to generate a form with a single field for capturing the user's name, and the data for this field can be fetched from the server using the specified data source. However, the description does not mention any other fields such as state or userId, so it is unclear whether these fields are part of the same form or not.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Board alias" summary="This form is used for getting the aliased board names." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "config", "subType": "boardAlias", "action": "get", "component": "app" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"data": {
  "templateName": "boardAlias",
  "action": "get",
  "fields": [
    {
      "name": "CBSE",
      "code": "ekstep_ncert_k-12",
      "alias": "CBSE/NCERT"
    }
  ]
}

```

The form configuration is used to fetch data related to a board using a specified template name and action. The "templateName" property specifies the name of the template used to fetch data, and "action" property specifies the type of action performed on the data.

Using this form configuration, the UI can be updated to display the aliased name "CBSE/NCERT" instead of the original name "CBSE". The form configuration may be used to fetch other data related to the board as well, but the description only specifies one field.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Supported activities" summary="This form is used to request more content." %}
{% swagger-description %}
**Form Create API:**

"request": { "type": "group", "subType": "supported\_activities", "action": "list" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
  "index": 2,
  "activityType": "Course",
  "objectType": "Content",
  "isEnabled": true,
  "sortBy": [
    {
      "name": "asc"
    }
  ],
  "searchQuery": "{\"request\":{\"filters\":{\"primaryCategory\":[\"Course\"],\"batches.status\":1,\"batches.enrollmentType\":\"open\",\"objectType\":[\"Content\"],\"status\":[\"Live\"]},\"fields\":[\"name\",\"appIcon\",\"contentType\",\"identifier\",\"objectType\",\"createdBy\"]}}",
  "title": "Course",
  "translations": "{\"en\": \"Course\", \"as\": \"পাঠ্যক্ৰমসমুহ\", \"bn\": \"পাঠ্যধারাগুলি\", \"gu\":\"કોર્સ\", \"hi\":\"कोर्स\", \"kn\":\"ಕೋರ್ಸ್ ಗಳು\", \"mr\":\"कोर्सेस\", \"or\":\"ପାଠ୍ୟକ୍ରମଗୁଡ଼ିକ\", \"pa\":\"ਕੋਰਸਿਸ\", \"ta\":\"பாடநெறிகள்\", \"te\":\"కోర్సులు\", \"ur\":\"کورسز\"}"
}
```

The form configuration provided is used to enable users to browse content by specific categories such as courses, digital textbooks, and explanation content. The form contains several properties to define the behavior and display of the content.

The "index" property specifies the position of the form in a list of forms, and the "activityType" and "objectType" properties specify the types of activities and objects that can be displayed in the form.

The "isEnabled" property indicates whether the form is currently enabled or disabled, and the "sortBy" property specifies the sorting order for the content. In this case, there is only one sorting option defined with the name "asc", which likely stands for ascending.

The "searchQuery" property specifies a JSON object that contains the search criteria used to filter the content. The search criteria include primary category, batch status, enrollment type, object type, and status. The "fields" property specifies the specific fields to be included in the search results, such as name, app icon, content type, identifier, object type, and createdBy.

The "title" property specifies the title of the form, which in this case is "Course". The "translations" property contains a JSON object that specifies translations of the form title in multiple languages, such as English, Assamese, Bengali, Gujarati, Hindi, Kannada, Marathi, Oriya, Punjabi, Tamil, Telugu, and Urdu.

![](../../.gitbook/assets/ksnip\_20230508-133414.png)

Using this form configuration, users can browse content by the specified categories and search criteria, with the form displaying the relevant content in the desired sorting order.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Frequently asked questions" summary="This form is used to get the list of all frequently asked questions." %}
{% swagger-description %}
**Form Create API:**

"/api/data/v1/system/settings/get/appFaqURL"
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
{
   "id": "appFaqURL",
   "field": "appFaqURL",
   "value":   "https://sunbirdstagingpublic.blob.core.windows.net/public/app-faq/resources/res"
}
```

The system setting is identified by its unique ID, which is also "appFaqURL". This setting controls the URL of the frequently asked questions (FAQ) page for the application.

![](../../.gitbook/assets/ksnip\_20230508-133645.png)

This system settings form configuration can be used to retrieve and modify the URL of the application's FAQ page, allowing users to customize the page's content or redirect it to a different location altogether.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Custodian org ID" summary="This form is used for getting the custodian org ID which is a required value." %}
{% swagger-description %}
**Form Create API:**

request: { path: "/api/data/v1/system/settings/get/custodianOrgId" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"response": {
  "id": "custodianOrgId",
  "field": "custodianOrgId",
  "value": "0126796199493140480"
}
```

The configuration response returns a JSON object that contains the following fields:

This system settings form configuration allows users to retrieve the unique identifier of the custodian organization, which is used to manage the system's data and resources. By modifying this setting, users can change the custodian organization and transfer control of the system to a different organization.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Deployment key" summary="This form is used to get the deployment key." %}
{% swagger-description %}
**Form Create API:**

request: { path: "/api/data/v1/system/settings/get/hotCodePush" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"response": {
 "id": "hotCodePush",
 "field": "hotCodePush",
 "value": "{ \"deploymentKey\": \"\"}"
}
```

The configuration response returns a JSON object that contains the following fields:

Hot code push is a feature that allows developers to update the application code without requiring users to download a new version of the application. By updating the "hotCodePush" system setting, developers can specify the deployment key used for hot code push, which determines which code updates are applied to the application.

This system settings form configuration allows users to retrieve the current value of the hot code push deployment key, which can be used to diagnose issues related to code updates or to modify the deployment key to enable hot code push functionality.
{% endswagger-response %}
{% endswagger %}

{% swagger method="post" path="" baseUrl="Group terms and conditions" summary="This form is used to get the terms and conditions related to groups." %}
{% swagger-description %}
**Form Create API:**

request: { path: "/api/data/v1/system/settings/get/groupsTnc" }
{% endswagger-description %}

{% swagger-response status="200: OK" description="" %}
```
"response": {
 "id": "groupsTnc",
 "field": "groupsTnc",
 "value": "{\"latestVersion\":\"3.5.0\",\"3.5.0\":{\"url\":\"https://sunbirdstagingpublic.blob.core.windows.net/termsandcondtions/terms-and-conditions-v9.html#groupGuidelines\"}}"
```

The configuration response returns a JSON object that contains the following fields:

This system settings form configuration allows users to retrieve the latest version and URL of the terms and conditions for groups in the application. By modifying this setting, users can update the terms and conditions or change the URL to a different location.

The terms and conditions for groups are typically used to inform users about the guidelines and rules for creating and managing groups within the application. The URL provided in the system setting configuration can be accessed by users to review the terms and conditions before creating or joining a group.
{% endswagger-response %}
{% endswagger %}
