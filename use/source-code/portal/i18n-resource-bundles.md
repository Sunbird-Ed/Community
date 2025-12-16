---
description: >-
  Resource bundles provide support to different languages based on the user’s
  preference.
---

# I18N (Resource Bundles)

* Resource bundles takes the json data specified in {language\_code}.json . [Refer this to know about language codes](https://en.wikipedia.org/wiki/List_of_ISO_639_language_codes) .
* Defines two resource types:

&#x20;       1\.    Consumption: Related to content consumed by users.

&#x20;       2\.   Creation: Related to tools for creating content.



To Change the Language Preference:

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdx3zzON4lggvxvNe9uw1-AmnwSCdsKmjcpobQyz-BcZv7SXhk5AO3RAZtGCRs_Nvts5aQWlCSV6SizilXElYlq5Cw9eVEtDmD6CV2GzhUar48NVNdb5e4pqP1Ffg2bbCVxbhNC?key=4wDksYJljHUrao5XV3FDqdYo)

Select one from the dropdown, default is English.

![](https://lh7-rt.googleusercontent.com/docsz/AD_4nXdmHyXcWUi74nQ-HzTDkmRu4ZGlEo7FhiHw1B-FcTC4NqEFwVv2GeaiSjvz4dS0oRWxxkbPPwo0Fz8d0ASn9MlZmOLjNTN8GTclvoWh7_QbvncSiPslLHoKkRj_roUMD0K35WT-?key=4wDksYJljHUrao5XV3FDqdYo)

## To modify existing resource bundle in portal:

* [src->app->resourcebundles->json](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/release-7.0.1/src/app/resourcebundles/json) has the .json  files that contains the resource bundles array.
* For example [en.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-7.0.1/src/app/resourcebundles/json/en.json) has,

&#x20;      `frmelmnts->btn-> "addnuserrole"="Add new role"`

&#x20;       If you want to modify the add new user role button just update the

&#x20;       Add new role  like,

&#x20;      `frmelmnts->btn-> "addnuserrole"="new Add new role"`<br>

## To add new resource bundle in portal:&#x20;

* [src->app->resourcebundles->json](https://github.com/Sunbird-Ed/SunbirdEd-portal/tree/release-7.0.1/src/app/resourcebundles/json)  This folder contains .json files that hold the resource bundle arrays. To add a new resource bundle, create a file named {language\_code}.json.
* Copy and paste the content of [en.json](https://github.com/Sunbird-Ed/SunbirdEd-portal/blob/release-7.0.1/src/app/resourcebundles/json/en.json) into your new file and modify the value. It will display the default(english) value if any of the values are missing.
* A proper format should be followed for example,&#x20;

&#x20;     `frmelmnts->btn-> "addnuserrole"= "Add new role"`

