# Observability

The **Observability** capability is enabled by the following components of **Sunbird Observ**-

\
**Telemetry Service -** Telemetry Service is a microservice that is capable of processing one or more events received from clients. Developed in NodeJS, telemetry service has processed more than 2 billion events per day.

### What is Telemetry? <a href="#what-is-telemetry" id="what-is-telemetry"></a>

The word ‘Telemetry’ is derived from its Greek etymological roots, tele - remote and metron - measure.

Telemetry V3 Event Structure

All events follow a common data structure, though the event data structure (“edata”) differs for each event. The complete data structure is as follows:

```
{
 // About the event
 "eid": , // Required. TODO: Shall we rename it to "verb" ?? 
 "ets": , // Required. Epoch timestamp of event (time in milli-seconds. For ex: 1442816723)
 "ver": , // Required. Version of the event data structure, currently "3.0"
 "mid": , // Required. Unique message ID. Used for deduplication, replay and update indexes
 
 // Who did the event
 "actor": { // Required. Actor of the event.
   "id": , // Required. Id of the actor. For ex: uid incase of an user
   "type":  // Required. User, System etc.
 },
 
 // Context of the event
 "context": { // Required. Context in which the event has occured.
   "channel": , // Required. Channel which has produced the event
   "pdata": { // Optional. Producer of the event
     "id": , // Required. unique id assigned to that component
     "pid": , // Optional. In case the component is distributed, then which instance of that component
     "ver":  // Optional. version number of the build
   },
   "env": , // Required. Unique environment where the event has occured.
   "sid": , // Optional. session id of the requestor stamped by portal
   "did": , // Optional. uuid of the device, created during app installation
   "cdata": [{ // Optional. correlation data
     "type":"", // Required. Used to indicate action that is being correlated
     "id": "" // Required. The correlation ID value
   }],
   "rollup": { // Optional. Context rollups
     "l1": "",
     "l2": "",
     "l3": "",
     "l4": ""
   }
 },
 // What is the target of the event
 "object": { // Optional. Object which is the subject of the event.
   "id": , // Required. Id of the object. For ex: content id incase of content
   "type": , // Required. Type of the object. For ex: "Content", "Community", "User" etc.
   "ver": , // Optional. version of the object
   "rollup": { // Optional. Rollups to be computed of the object. Only 4 levels are allowed.
   	"l1": "",
     "l2": "",
     "l3": "",
     "l4": ""
   }
 },
 
 // What is the event data
 "edata": {} // Required.
 
 // Tags
 "tags": [] // Optional. Encrypted dimension tags passed by respective channels
}
```

**Note:**

* All events have the same structure with only differences in edata structures.
* All events have unique event codes i.e., (IDs).
* All events are as per platform schema

For more information about **Telemetry services** please click [here](http://127.0.0.1:5000/s/ttPCtrHlLrl4MRuGlakt/learn/product-and-developer-guide/telemetry-service)

**Telemetry Spec**

* [Start](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#start) - This method initializes the capture of telemetric data associated with the start of user's action
* [Impression](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#impression) - This method is used to capture telemetry for user visits to a specific page.
* [Interact](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#interact) - This method is used to capture user interactions on a page. For example, search, click, preview, move, resize, configure
* [Assess ](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#access)- This method is used to capture user assessments that happen while playing content.
* [Response](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#response) - This method is used to capture user responses. For example; response to a poll, calendar event, or a question.
* [Interrupt](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#interrupt) - This method is used to capture interrupts triggered during user activity. For example;  mobile app sent to the background, call on the mobile, etc.
* [Feedback](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#feedback) - This method is used to capture user feedback
* [Share](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#share) - This method is used to capture everything associated with sharing. For example; Share content, telemetry data, link, file, etc.
* [Audit](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#audit) - This method is used to log telemetry when an object is changed. This includes life-cycle changes as well
* [Error](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#error) - This method is used to capture when users face an error
* [Heartbeat](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#heartbeat) - This method is used to log telemetry for heartbeat events to denote that the process is running
* [Log](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#log) - This method is used to capture generic logging of events. For example; capturing logs for API calls, service calls, app updates, etc.
* [Search](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#search) - This method is used to capture the search state i.e. when a search is triggered for content, item, assets, etc.
* [Metrics](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#metrics) - This method is used to log telemetry for service business metrics
* [Summary](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#summary) - This method is used to log telemetry summary event
* [Exdata](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#exdata) - This method is used as a generic wrapper event to capture encrypted or serialized data
* [End](http://docs.sunbird.org/latest/developer-docs/telemetry/eventdetails/#end) - This method is used to capture closure after all the activities are completed

For more information about **Telemetry Spec** please click [here](http://127.0.0.1:5000/s/-MkM7F4oILSpCJPO0YUu/learn/understand)

**Data Service -**&#x20;

For more information about **Data services** please click [here](http://127.0.0.1:5000/s/ttPCtrHlLrl4MRuGlakt/learn/product-and-developer-guide/data-service)

**Data Pipeline**

For more information about **Data Pipeline** please click [here](http://127.0.0.1:5000/s/ttPCtrHlLrl4MRuGlakt/learn/product-and-developer-guide/data-pipeline)

**Report Service**

For more information about **Report services** please click [here](http://127.0.0.1:5000/s/ttPCtrHlLrl4MRuGlakt/learn/product-and-developer-guide/report-service)

**Report Configurator**

For more information about **Report Configurator** please click [here](http://127.0.0.1:5000/s/ttPCtrHlLrl4MRuGlakt/learn/product-and-developer-guide/report-configurator)

{% hint style="info" %}
Powered By [Sunbird Obsrv](http://127.0.0.1:5000/o/-Mi9QwJlsfb7xuxTBc0J/s/ttPCtrHlLrl4MRuGlakt/ "mention")
{% endhint %}
