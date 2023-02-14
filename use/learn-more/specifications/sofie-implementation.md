# SOFIE Implementation

#### Registration steps for third-party apps with the Sunbird platform

Each third-party app should be registered with Sunbird to enable integrations. Registration aims to verify the authenticity of the app providing integration/extension to sunbird and also allow policy-makers (of the sunbird instance) to do an appropriate review and accept the integration.

Following is the info/specification required for the registration

```json
{
   name: "", // Required. Name of the app. For ex: "Sunbird ReadAlong"
   logo: "", // Required. Logo of the app. This is used to show the user to select the extension app he chooses to open with.
   provider: {
      name: "", // Required. Name of the company that has built the app
      copyright: "", // Optional. Any copyright information to be shown
      license: "" // Optional. License of the app.
   },
   osType: "", // Required. OS of the App. Android/iOS
   osMetadata: { // Required. Metata of the OS
      packageId: "", // Required. A fully qualified app name matching the play store app id. For ex: "com.sunbird.readalong.app"
      appVersion: "", // Required. Version of the app. Sunbird uses this to check if the app is installed locally
      urlScheme: "", // Required for iOS. The URL scheme of the app. Used for the app invocation.
      compatibilityVer: "" // Required. Compatible with which version of sunbird app.
   },
   target: {
      mimeType: [...],// Required. Supported mimeTypes
      primaryCategory: [...] // Required. Supported primaryCategory
   }
   actions: [ActionData] // Actions to register with
}
```

For example, suppose a third-party app called "**ReadAlong**" wants to integrate with Sunbird. So "**ReadAlong**" team can approach the Sunbird team and can provide the above info about "**ReadAlong**". On the mobile app side, the following form is used to fetch all integrated apps.

<pre class="language-json"><code class="lang-json"><strong>    "type": "config",
</strong>    "subType": "vendorapps",
    "action": "get",
    "component": "app"
</code></pre>

Once the form is updated the form should look like following

```json
{
    "id": "api.form.read",
    "params": {
        "resmsgid": "64775740-5234-42f3-8156-0e4439cbf962",
        "msgid": "82ca7783-560d-42f1-bbe3-c09fde360bd6",
        "status": "successful"
    },
    "responseCode": "OK",
    "result": {
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
                        "name": "Read Along,
                        "logo": "https://img.icons8.com/doodle/48/000000/league-of-legends.png",
                        "provider": {
                            "name": "Read Along Team",
                            "copyright": "",
                            "license": ""
                        },
                        "android": {
                            "packageId": "io.ionic.readalong",
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
    },
    "ts": "2023-02-13T17:35:21.288Z",
    "ver": "1.0"
}
```

#### Technical Specification for third-party apps

Every app that registers with sunbird would register for the actions supported by the app. For ex: Let us assume that the sunbird app at the content level supports actions such as "open" and "share". Any extension app which registers for these actions would be shown as available options to the user when the corresponding actions are triggered.

The technical specification is broken down into the following sections:

1. **Action Data Structure**:-  Structure of the action data
2. **Integration specification**:- Data specification of integration
3. **Integration via intent**:- Data specification for integration via intent
4. **Integration via deep link**:- Data specification for integration via deeplink

#### Action Data Structure

Following is the structure of generalized action data for which an app can register for.

```
{
    "action": {
        "type": "IN/OUT", // Required. Whether the action is an in-ward/out-ward actions.
        "id": "", // Required. ID of the action. For ex: Play/Share/Search
        "payload": "", // Optional. Payload of the action. JSON String
        "ctx_id": "", // Optional. Context of the action. For ex: Content Id of the action is Play
        "ctx_type": "", // Optional. Context type. For ex: Content/Assessment etc
        "subctx_id": "", // Optional. Any Sub Context? For ex: CollectionId/TextbookId/GroupId etc
        "subctx_type": "", // Optional. Sub context type. For ex: Course/Textbook/Group etc
        "extra": "" // Optional. JSON String. Any extra params/data to be passed?
    }
}
```

#### Integration specification

Following is the specification of the integration, the data to be passed from one app to another

```
{
    "packageId": "", // Required. Package details of referrer app
    "referenceID": "", // Optional. Reference ID to be sent back to sunbird app
    "authKey": "", // Optional. Authorization Key for referrer app
    "data": ActionData // ActionData
}
```

#### Integration via intent

Following is how the specification is transformed when integrated via intent.

```
{
    package: "", // Required. Package id of the invoking app
    action: "android.intent.action.VIEW", // Required. A constant value specific to android
    extras: {
        "packageId": "", // Required. Package details of referrer app
        "referenceID": "", // Optional. Reference ID to be sent back to sunbird app
        "authKey": "", // Optional. Authorization Key for referrer app
        "data": { // Action Data
            "type": "IN/OUT", // Required. Whether the action is an in-ward/out-ward actions.
            "id": "", // Required. ID of the action. For ex: Play/Share/Search
            "payload": "", // Optional. Payload of the action. JSON String
            "ctx_id": "", // Optional. Context of the action. For ex: Content Id of the action is Play
            "ctx_type": "", // Optional. Context type. For ex: Content/Assessment etc
            "subctx_id": "", // Optional. Any Sub Context? For ex: CollectionId/TextbookId/GroupId etc
            "subctx_type": "", // Optional. Sub context type. For ex: Course/Textbook/Group etc
            "extra": "" // Optional. JSON String. Any extra params/data to be passed?
        }
    }
}
```

#### Example

```
// Example invoking an search intent on sunbird app
{
    package: "org.sunbird.app",
    action: "android.intent.action.VIEW",
    extras: {
        packageId: "org.xyz.readalong",
        data: {
            type: "IN",
            id: "Search",
            payload: "{\"filters\":{\"se_boards\":[\"CBSE\"],\"se_mediums\":[\"English\"],\"se_gradeLevels\":[\"Class 10\"],\"subject\":[],\"audience\":[],\"primaryCategory\":[\"Digital Textbook\"]},\"fields\":[\"name\",\"appIcon\",\"mimeType\",\"gradeLevel\",\"identifier\",\"medium\",\"pkgVersion\",\"board\",\"subject\",\"resourceType\",\"primaryCategory\",\"contentType\",\"channel\",\"organisation\",\"trackable\",\"se_boards\",\"se_subjects\",\"se_mediums\",\"se_gradeLevels\"],\"facets\":[\"subject\"]}"
        }
    }
}

```

#### Integration via deeplink

Following is how the specification is transformed when integrated via intent.

```
https://<urlscheme>/sofie/?packageId=""&referenceID=""&authKey=""&data=""
```

#### Example

```
// Example invoking an search intent on sunbird app
https://sunbird.org/sofie/?packageId="org.xyz.readalong"&data="{\"type\":\"IN\",\"id\":\"Search\",\"payload\":\"{\\\"filters\\\":{\\\"se_boards\\\":[\\\"CBSE\\\"],\\\"se_mediums\\\":[\\\"English\\\"],\\\"se_gradeLevels\\\":[\\\"Class 10\\\"],\\\"subject\\\":[],\\\"audience\\\":[],\\\"primaryCategory\\\":[\\\"Digital Textbook\\\"]},\\\"fields\\\":[\\\"name\\\",\\\"appIcon\\\",\\\"mimeType\\\",\\\"gradeLevel\\\",\\\"identifier\\\",\\\"medium\\\",\\\"pkgVersion\\\",\\\"board\\\",\\\"subject\\\",\\\"resourceType\\\",\\\"primaryCategory\\\",\\\"contentType\\\",\\\"channel\\\",\\\"organisation\\\",\\\"trackable\\\",\\\"se_boards\\\",\\\"se_subjects\\\",\\\"se_mediums\\\",\\\"se_gradeLevels\\\"],\\\"facets\\\":[\\\"subject\\\"]}\"}"
```
