---
description: >-
  Manage Learn is a vertical within the Sunbird project that focuses on
  implementing project, observation, and survey capabilities. Currently, in the
  portal, only the Observation flow is enabled.
---

# Portal - Manage Learn - component diagram

<figure><img src="../../.gitbook/assets/340946b3-f9b7-45d4-b340-8d35b799697b (1).png" alt=""><figcaption><p>Core modules of Manage Learn</p></figcaption></figure>



### [Observation](https://sunbird-ed.github.io/docs/portal/modules/ObservationModule.html)

This module consists of flows like observation listing, Observation details, entity addition, etc. Only the logged-in user will be able to access these features.

_**Observation Listing**_ -Observation can be targeted to specific roles or roles in the system. If the logged-in user role/roles matches with the targetted roles of the observation, the observation will be shown to the user. Targeted observations will be listed in the Observation tile of the portal.

_**Observation details**_ - This page shows the complete information about the observation and also allows the user to add an entity, remove an entity, etc. Users will be only able to add entities as specified in the observation.



### [Questionnaire](https://sunbird-ed.github.io/docs/portal/modules/QuestionnaireModule.html)

Observation has the ability to render seven different types of question types(radio, multi-select, text, number, date, etc). This module consists of the sl-questionnaire library which will enable the rendering of all types of questions.  Post completing the  form the user will be able to submit the form to the backend



### [Program Dashboard](https://sunbird-ed.github.io/docs/portal/modules/programDashboardModule.html)

The Program Manager (PM) and Program Designers (PD) will have access to the Program level reports of the submitted user. This will help them to track the progress and other information of the program and observation. The PM and PD  will be able to view multiple reports and CSV. All  components and libraries for this flow are included in this module&#x20;



### [Report](https://sunbird-ed.github.io/docs/portal/modules/ReportModule.html)

Logged-in users will be able to view the reports of submissions he/she had made. This module contains all the components and flows for the report viewing.&#x20;

