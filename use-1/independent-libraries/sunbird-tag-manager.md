# Sunbird Tag Manager

Library is used to create Edge Computable Tags agnostic to project, framework choice. This works like a Open Specification to enable clients to generate Tags and Evaluate these tags against a criteria from server.

{% hint style="info" %}
[https://github.com/Sunbird-Ed/sb-tag-manager](https://github.com/Sunbird-Ed/sb-tag-manager)
{% endhint %}

{% hint style="info" %}
Supporting Documentation - [https://project-sunbird.atlassian.net/wiki/spaces/CON/pages/1553465352/Criteria+Action+structure](https://project-sunbird.atlassian.net/wiki/spaces/CON/pages/1553465352/Criteria+Action+structure)
{% endhint %}

|                                |                                                                                              |
| ------------------------------ | -------------------------------------------------------------------------------------------- |
| Current Release Branch         | master                                                                                       |
| NPM Published version (Latest) | 3.9.19                                                                                       |
| NPM Package Name               | @project-sunbird/sb-tag-manager                                                              |
| NPM Link                       | [https://www.npmjs.com/package/sb-tag-manager](https://www.npmjs.com/package/sb-tag-manager) |
| Works                          | Across all projects. (Framework and Tech Agnostic Library)                                   |

### Installation

1. Install the library in the project as follows :

```
npm i @project-sunbird/sb-tag-manager
```

### Getting Started

1. Navigate to App Component (or) Equivalent module and add the following import

```
import { SBTagModule } from 'sb-tag-manager';
```

1. Initialise the Library

```
let instance = SBTagModule.instance;
instance.init();
```

### Services

#### SBTagService

1. Tag Interface Methods

```
instance.SBTagService.pushTag({object},"prefix_string");
instance.SBTagService.getTags("prefix_string");
instance.SBTagService.getAllTags();
instance.SBTagService.removeTag("prefix_string");
instance.SBTagService.removeAll();
```
