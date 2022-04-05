# Rich and Diverse Content

The **Rich and Diverse** **Content** capability is enabled by the following components of Sunbird Knowlg-

1. **Content players**

Content players are Javascript-enabled components used to help the users to access content on the application. These components are used to analyse the progress, and interactions of the user on the content using Telemetry. Every Content Player is enabled to raise the following events:\
a) Start Event: Every Content Play in the player is acknowledged by "START" event to represent the initiation of content on the player\
b) End Event: End Event of Content Player confirms the completion of Content along with metadata.\
c) Summary Event: Raised for once before the "END" event can act as metadata that captures the user behaviour on the content.\
d) HeartBeat Event - Raised almost every 5 seconds to let the system know on last known status.\
\
These event data are critically computed for the specific business logic of the application. For e.g.\
a) User with at least 20% progress in the Video can be set as a precondition for content consumption to be acknowledged.\
b) User reaching the last page can be a precondition for content consumption to be acknowledged. \
&#x20;\
For more information about **Content player** please click [here](https://app.gitbook.com/s/aanfWbeVT74C5lXDPde3/learn/product-and-developer-guide/player)

**2. Content service**

Content service is a set of microservices to manage the lowest consumable entity in the system. SunbirdED leverages the content search Services extensively to enable the personalisation of content to the user. \
Ex: A student's learning experience can be personalised by providing more learning resources like explanation content videos, Question paper PDF, puzzles, and games based on his level of competence.\
Sunbird ED has the capability to capture, record, and assess candidate's learning outcomes based on these assets.

For more information about **Content  services** please click [here](https://app.gitbook.com/s/aanfWbeVT74C5lXDPde3/learn/product-and-developer-guide/content-service)&#x20;

{% hint style="info" %}
Powered by [Sunbird Knowlg](https://app.gitbook.com/o/-Mi9QwJlsfb7xuxTBc0J/s/aanfWbeVT74C5lXDPde3/ "mention")
{% endhint %}
