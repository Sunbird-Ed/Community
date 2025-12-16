---
description: >-
  Resource bundles provide support to different languages based on the user’s
  preference.
---

# I18N (Resource Bundles)

## To modify existing resource bundle in Mobile App:

* [src->assets->i18n](https://github.com/Sunbird-Ed/SunbirdEd-mobile-app/blob/release-7.0.0/src/assets/i18n) This folder contains .json files that contain the resource bundles array.
* For example [en.json](https://github.com/Sunbird-Ed/SunbirdEd-mobile-app/blob/release-7.0.0/src/assets/i18n/en.json) has,&#x20;

&#x20;     `"ABOUT": "About"`,

&#x20;     If you want to modify the ABOUT text, simply update its value.  For example,&#x20;

&#x20;    `"ABOUT": "New About Text"`

## To add new resource bundle in Mobile App:

* [src->assets->i18n](https://github.com/Sunbird-Ed/SunbirdEd-mobile-app/blob/release-7.0.0/src/assets/i18n) This folder contains .json files that hold the resource bundle arrays. To add a new resource bundle, create a file named {language\_code}.json and add the required values.
* Copy and paste the content of [en.json](https://github.com/Sunbird-Ed/SunbirdEd-mobile-app/blob/release-7.0.0/src/assets/i18n/en.json) into your new file and modify the value. It will display the default(english) value if any of the values are missing.
* A proper format should be followed for example, `"ACCOUNT_MERGE_CONFIRMATION_BTN_MERGE": "Merge"`

<br>
