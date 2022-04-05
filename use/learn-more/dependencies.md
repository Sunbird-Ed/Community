# Dependencies

{% tabs %}
{% tab title="Sunbird Knowlg" %}


| Category of Dependency | Tools & API End Points | Description |   |
| ---------------------- | ---------------------- | ----------- | - |
| Content Players        | PDF Player             |             |   |
|                        | Video Player           |             |   |
|                        | H5p/HTML Player        |             |   |
|                        | ECML Player            |             |   |
|                        | EPUB Player            |             |   |
| Micro Services         |                        |             |   |
| Content Service        | content/v1/read/       |             |   |
| Collection Service     | course/v1/hierarchy/   |             |   |
| Search Service         | content/v1/search      |             |   |
| Dial Service           | data/v1/dial/assemble  |             |   |
| Taxonomy Service       |                        |             |   |
|                        |                        |             |   |
|                        |                        |             |   |
|                        |                        |             |   |
| Event Service          |                        |             |   |
{% endtab %}

{% tab title="Sunbird Observ" %}
Sunbird _Obsrv_ to measure and observe various actions and activities on Sunbird. It offers a powerful data processing and aggregation infrastructure to process telemetry data, validate, aggregate, and generate insights. It also has built-in open data cataloging and publishing capability. It is built keeping extensibility in mind, so that adopters have the flexibility to adapt the telemetry and tools to their specific use-cases.



| Category of Dependency | API End Point              | Description |   |
| ---------------------- | -------------------------- | ----------- | - |
| Micro Services         |                            |             |   |
| Telemetry Service      | /content/data/v1/telemetry |             |   |
|                        | /device/register/          |             |   |
| Report Service         | /data/reports/public/      |             |   |
{% endtab %}

{% tab title="Sunbird Lern" %}
Sunbird _Lern_ is a building block comprising of core services that enable observation of a user’s learning journey as well as permit for interaction and collaboration among learners to further their learning. These capabilities can be leveraged by any adopter with requirements for measurement of learning progress, creation and management of cohorts/ batches of learners, as well as enabling collaboration capabilities such as Groups or Discussion forums.



| Category of Dependency | API End Point             | Description |   |
| ---------------------- | ------------------------- | ----------- | - |
| Micro Services         |                           |             |   |
| Profile Service        | user/v4/read/             |             |   |
|                        | user/v1/update            |             |   |
|                        | user/v1/tnc/accept        |             |   |
|                        | user/v1/consent/read      |             |   |
| Content Service        | content/state/v1/read     |             |   |
|                        | content/state/v1/update   |             |   |
| Enrolment Service      | course/v1/enrol           |             |   |
| Certificate Service    | certreg/v1/cert/search    |             |   |
|                        | certreg/v1/cert/downloads |             |   |
| Location Service       | data/v1/location/search   |             |   |
| Organisation Service   |                           |             |   |
|                        |                           |             |   |
|                        |                           |             |   |
|                        |                           |             |   |
| Notification Service   | user/v1/feed              |             |   |
{% endtab %}

{% tab title="Sunbird Inquiry" %}
Sunbird inQuiry is a building block that enables question banks that can contain questions and question sets for various use cases such as practice, assessment, quiz, worksheet, survey, observations and many more.



| Category of Dependency | Tools and API End Points | Description |   |
| ---------------------- | ------------------------ | ----------- | - |
| Players                | QuML Player              |             |   |
| Micro Services         |                          |             |   |
| Question Set Service   | questionset/v1/read      |             |   |
{% endtab %}

{% tab title="Sunbird UCI" %}


| Category of Dependency | Tools    | Description |   |
| ---------------------- | -------- | ----------- | - |
| UI                     | Chat Bot |             |   |
{% endtab %}
{% endtabs %}

##













