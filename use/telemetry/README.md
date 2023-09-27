# Telemetry

### Telemetry V3 Event Structure

All events follow a common data structure, though the event data structure ("edata") differs for each event. The complete data structure is as follows:

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

* All events have the same structure with only difference in edata structures.
* All events have unique event codes i.e., (IDs).
* All events are as per platform schema

### Events Specs

* [Start](./#start) - This method initialises capture of telemetric data associated to the start of user action
* [Impression](./#impression) - This method is used to capture telemetry for user visits to a specific page.
* [Interact](./#interact) - This method is used to capture user interactions on a page. For example, search, click, preview, move, resize, configure
* [Assess](./#assess) - This method is used to capture user assessments that happen while playing content.
* [Response](./#response) - This method is used to capture user responses. For example; response to a poll, calendar event or a question.
* [Interrupt](./#interrupt) - This method is used to capture interrupts triggered during user activity. For example; mobile app sent to background, call on the mobile, etc.
* [Feedback](./#feedback) - This method is used to capture user feedback
* [Share](./#share) - This method is used to capture everything associated with sharing. For example; Share content, telemetry data, link, file etc.
* [Audit](./#audit) - This method is used to log telemetry when an object is changed. This includes life-cycle changes as well
* [Error](./#error) - This method is used to capture when users face an error
* [Heartbeat](./#heartbeat) - This method is used to log telemetry for heartbeat event to denote that the process is running
* [Log](./#log) - This method is used to capture generic logging of events. For example; capturing logs for API calls, service calls, app updates etc.
* [Search](./#search) - This method is used to capture the search state i.e. when search is triggered for content, item, assets etc.
* [Metrics](./#metrics) - This method is used to log telemetry for service business metrics
* [Summary](./#summary) - This method is used to log telemetry summary event
* [Exdata](./#exdata) - This method is used as a generic wrapper event to capture encrypted or serialized data
* [End](./#end) - This method is used to capture closure after all the activities are completed

#### Start

This API is used to log telemetry when users view content or initiate game play

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "", // Required. app, session, editor, player, workflow, assessment
    "dspec": DSPEC, // Optional. Device spec
    "uaspec": UASPEC, // Optional. User agent spec
    "loc": "", // Optional. Location of the device
    "mode": "", // Optional. Mode of start. For "player" it would be "play/edit/preview". For Workflow it would be Review/Flag/Publish. For editor it could be "content", "textbook", "generic", "lessonplan" etc
    "duration": , // Optional. Time taken to initialize/start
    "pageid": "" // Optional. Page/Stage id where the start has happened.
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device1",
      "env": "Genie",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "1.0"
      },
      "sid": "3f2a0cc4-7bde-4044-8261-500dc13ef285"
    },
    "edata": {
      "mode": "edit",
      "pageid": "",
      "type": "player"
    },
    "eid": "START",
    "ets": 1518500741582,
    "mid": "92a9a779-ea2c-4f4e-8d07-fc7c3e851993",
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-13T05:45:48.588Z",
    "ts": "2018-02-13T05:45:41.582+0000"
  }
```

#### Impression

This API is used to log telemetry when users visit a specific page.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "", // Required. Impression type (list, detail, view, edit, workflow, search)
    "subtype": "", // Optional. Additional subtype. "Paginate", "Scroll"
    "pageid": "", // Required. Unique page id
    "uri": "", // Required. Relative URL of the content
    "visits": [VISIT] // Optional. Capture the object visits
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device1",
      "env": "ContentPlayer",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "1.0"
      },
      "rollup": {},
      "sid": "7d6c6c9a-8323-49b2-84e0-3b46ae32eada"
    },
    "edata": {
      "visits": [
        {
          "objid": "course1",
          "objtype": "Course",
          "section": "Latest Courses",
          "index": 0
        },
        {
          "objid": "course2",
          "objtype": "Course",
          "section": "Latest Courses",
          "index": 1
        }
      ],
      "pageid": "home-page",
      "type": "workflow",
      "uri": ""
    },
    "eid": "IMPRESSION",
    "ets": 1518503128479,
    "mid": "4273778a-8f35-4945-97ae-bf5033c84425",
    "object": {
      "id": "test-content1",
      "type": "Content",
      "ver": "2.0"
    },
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-13T06:25:32.914Z",
    "ts": "2018-02-13T06:25:28.479+0000"
  }
```

#### Interact

This API is used to log telemetry of user interactions on the page. For example, search, click, preview, move, resize, configure

The "edata" structure of Start is as follows:

```
data - Object //Required
{
  "edata": {
    "type": "", // Required. Type of interaction TOUCH,DRAG,DROP,PINCH,ZOOM,SHAKE,ROTATE,SPEAK,LISTEN,WRITE,DRAW,START,ENDCHOOSE,ACTIVATE,SHOW,HIDE,SCROLL,HEARTBEAT,OTHER
    "subtype": "", // Optional. Additional types for a global type. For ex: for an audio the type is LISTEN and thesubtype can be one of PLAY,PAUSE,STOP,RESUME,END
    "id": "", // Required. Resource (button, screen, page, etc) id on which the interaction happened - use systemidentifiers when reporting device events
    "pageid": "", // Optional. Stage or page id on which the event happened
    "target": TARGET, // Optional. Target context where the interaction has happened
    "plugin": PLUGIN, // Optional. Plugin on which the interaction has happend
    "extra": { // Optional. Extra attributes for an interaction
      "pos": [{"x":,"y":,"z":}], // Array of positional attributes. For ex: Drag and Drop has two positional attributes. One where the drag has started and the drop point
      "values": [], // Array of values, e.g. for timestamp of audio interactions
    }
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device1",
      "env": "ContentPlayer",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "1.0"
      },
      "rollup": {},
      "sid": "7d6c6c9a-8323-49b2-84e0-3b46ae32eada"
    },
    "edata": {
      "id": "id1",
      "pageid": "end-page",
      "subtype": "",
      "type": "TOUCH"
    },
    "eid": "INTERACT",
    "ets": 1518503441413,
    "mid": "41c5632f-a47e-4910-99b3-3b351c3ca3bf",
    "object": {
      "id": "id1",
      "type": "Content",
      "ver": "1.0"
    },
    "tags": [],
    "ver": "3.0",
    "@version": "1",
    "@timestamp": "2018-02-13T06:30:33.578Z",
    "ts": "2018-02-13T06:30:41.413+0000"
  }
```

#### Assess

This API is used to log telemetry of assessments that have occured when the user is viewing content

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "item": QUESTION, // Required. Question Data
    "index": , // Optional. Index of the question within a content.
    "pass": "", // Required. Yes, No. This is case-sensitive. default value: No.
    "score": , // Required. Evaluated score (Integer or decimal) on answer(between 0 to 1), default is 1 if pass=YES or 0 if pass=NO. 
    "resvalues": [{"id":"value"}], // Required. Array of key-value pairs that represent child answer (result of this assessment)
    "duration":  // Required. time taken (decimal number) for this assessment in seconds
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device",
      "env": "ContentPlayer",
      "pdata": {
        "id": "producer1",
        "ver": "1.0"
      },
      "rollup": {},
      "sid": "ci4gjqokrccvbdl4kss4pbhnh0"
    },
    "edata": {
      "duration": 9,
      "item": {
        "desc": "",
        "exlength": 0,
        "id": "ques1",
        "maxscore": 1,
        "mc": [],
        "mmc": [],
        "params": [],
        "uri": ""
      },
      "pass": "No",
      "resvalues": [
        {
          "ans1": "6"
        }
      ],
      "score": 0
    },
    "eid": "ASSESS",
    "ets": 1518503832030,
    "mid": "4399a98d6c50c5d70a3150f3a5ab649e",
    "object": {
      "id": "test-content",
      "type": "Content",
      "ver": "1.0"
    },
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-13T06:37:25.333Z",
    "ts": "2018-02-13T06:37:12.030+0000"
  }
```

#### Response

This API is used to log telemetry of user response. For example; Responded to assessments.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "target": TARGET, // Required. Target of the response
    "type": "", // Required. Type of response. CHOOSE, DRAG, SELECT, MATCH, INPUT, SPEAK, WRITE
    "values": [{"key":"value"}] // Required. Array of response tuples. For ex: if lhs option1 is matched with rhs optionN - [{"lhs":"option1"}, {"rhs":"optionN"}]
  }
}  
```

Example event data:

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device",
      "env": "ContentPlayer",
      "pdata": {
        "id": "producer1",
        "ver": "1.0"
      },
      "rollup": {},
      "sid": ""
    },
    "edata": {
      "target": {
        "id": "ques1",
        "type": "AssessmentItem",
        "ver": "1.0"
      },
      "type": "SELECT",
      "values": [
        {
          "option": "A",
          "state": "selected"
        }
      ]
    },
    "eid": "RESPONSE",
    "ets": 1518503809778,
    "mid": "RESPONSE:55ea33c06880c9179c92d223661172c6",
    "object": {
      "id": "test-content1",
      "type": "Content",
      "ver": "1"
    },
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-13T06:37:01.255Z",
    "ts": "2018-02-13T06:36:49.778+0000"
  }
```

#### Interrupt

This API is used to log telemetry for any interruptions that have occurred when a user is viewing content or playing games. For example; screen lock, incoming call, etc.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "", // Required. [m:background, m:resume]
    "pageid": "" // Optional. Page id where the interrupt has happened
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "eid": "INTERRUPT",
    "edata": {
      "type": "resume"
    },
    "ver": "3.0",
    "@timestamp": "2018-02-13T06:48:56.626Z",
    "ets": 1518504535560,
    "context": {
      "channel": "test-channel",
      "env": "Genie",
      "sid": "a9da9668-d3f0-4edf-8c2a-e92c0b4cb24f",
      "did": "test-device",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "1.0.25"
      },
      "cdata": []
    },
    "mid": "INTERRUPT:15704362-aa2a-4b4c-b99c-0f4296a98f52",
    "object": {
      "parent": {}
    },
    "tags": [
      "registered-tag1"
    ],
    "ts": "2018-02-13T06:48:55.560+0000"
  }
```

#### Feedback

This API is used to log telemetry of feedback provided by the user.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "rating": 3, // Optional. Numeric score (+1 for like, -1 for dislike, or 4.5 stars given in a rating)
    "comments": "User entered feedback" // Optional. Text feedback (if any)
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device",
      "env": "ContentPlayer",
      "pdata": {
        "id": "producer",
        "pid": "genieservice.android",
        "ver": "1.0"
      },
      "rollup": {},
      "sid": "fe6e4b5f-ef32-4a20-827f-eb094df05e8a"
    },
    "edata": {
      "comments": "",
      "rating": 2
    },
    "eid": "FEEDBACK",
    "ets": 1518456436008,
    "mid": "5a7bee12-a4ed-49b1-9ac9-e03343045d08",
    "object": {
      "id": "test-content1",
      "type": "Content",
      "ver": "1.0"
    },
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-12T17:27:27.297Z",
    "ts": "2018-02-12T17:27:16.008+0000"
  }
```

#### Share

This API is used to log telemetry when a user shares any content with other users.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "dir": "", // In/Out
    "type": "", // File/Link/Message
    "items": [{ // Required. array of items shared
      "id": "",
      "type": "",
      "ver": ""
      "params": [
        {"key": "value"}
      }],
      "origin": { // Origin of the share file/link/content
        "id": "", // Origin id
        "type": "" // Origin type
      },
      "to": {
        "id": "",
        "type": ""
      }
    }]
  }
}  
```

Example event data:\\

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "eid": "SHARE",
    "edata": {
      "dir": "In",
      "type": "File",
      "items": [
        {
          "ver": "1.0",
          "origin": {
            "id": "devcie1",
            "type": "device"
          },
          "id": "content1",
          "to": {
            "id": "",
            "type": ""
          },
          "type": "CONTENT",
          "params": [
            {
              "transfers": 0,
              "count": 0
            }
          ]
        },
        {
          "ver": "2.0",
          "origin": {
            "id": "device1",
            "type": "device"
          },
          "id": "content2",
          "to": {
            "id": "",
            "type": ""
          },
          "type": "CONTENT",
          "params": [
            {
              "transfers": 0,
              "count": 0
            }
          ]
        }
      ]
    },
    "ver": "3.0",
    "@timestamp": "2018-02-13T07:00:59.995Z",
    "ets": 1518505245934,
    "context": {
      "channel": "test-channel",
      "env": "Genie",
      "sid": "6aa26dab-672e-4507-a2b5-c63fe926796c",
      "did": "test-device",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "1.0.25"
      },
      "cdata": []
    },
    "mid": "SHARE:ec607e89-7d5f-4898-ae86-c690e35432fa",
    "object": {
      "parent": {}
    },
    "tags": [
      "tag1"
    ],
    "ts": "2018-02-13T07:00:45.934+0000"
  }
```

#### Audit

This API is used to log telemetry when an object is changed. This includes life-cycle changes as well.

The "edata" structure of Start is as follows:

```
data - Object //Required
{
  "edata": {
    "props": [""], // Updated properties
    "state": "", // Optional. Current state
    "prevstate": "" // Optional. Previous state
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "",
      "type": ""
    },
    "eid": "AUDIT",
    "edata": {
      "state": "Draft",
      "prevstate": ""
    },
    "ver": "3.0",
    "@timestamp": "2018-02-13T07:09:04.183Z",
    "ets": 1518505742782,
    "context": {
      "channel": "test-channel",
      "env": "",
      "sid": "",
      "did": "",
      "pdata": {
        "id": "producer1",
        "pid": "ObjectLifecycle",
        "ver": "1.0"
      },
      "cdata": []
    },
    "mid": "AUDIT:6ef03ef3a9fa8308204ea4d8570591e0",
    "object": {
      "id": "test-content1",
      "type": "Content",
      "ver": "",
      "subtype": "Story",
      "parent": {
        "id": "",
        "type": ""
      }
    },
    "tags": [],
    "ts": "2018-02-13T07:09:02.782+0000"
  }
```

#### Error

This API is used to log telemetry of any error that has occurred when a user is viewing content or playing games.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "err": "", // Required. Error code
    "errtype": "", // Required. Error type classification - "SYSTEM", "MOBILEAPP", "CONTENT"
    "stacktrace": "", // Required. Detailed error data/stack trace
    "pageid": "", // Optional. Page where the error has occured
    "object": OBJECT, // Optional. Object on which the error occured
    "plugin": PLUGIN // Optional. Plugin in which the error occured
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device",
      "env": "Genie",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "6.0"
      },
      "sid": "a8506bb6-edc5-4b59-b935-07dbabd1e9f3"
    },
    "edata": {
      "err": "ERR_TOKEN_INVALID",
      "errtype": "UNAUTHORIZED_ACCESS",
      "stacktrace": "{\"id\":\"api.upload.url\",\"ver\":\"1.0\",\"ts\":\"2018-02-12T17:04:21.726Z\",\"params\":{\"resmsgid\":\"id1\",\"msgid\":null,\"status\":\"failed\",\"err\":\"ERR_TOKEN_INVALID\",\"errmsg\":\"Access denied\"},\"responseCode\":\"UNAUTHORIZED_ACCESS\",\"result\":{}}"
    },
    "eid": "ERROR",
    "ets": 1518505910718,
    "mid": "58a11d49-22c8-4535-a28b-7a323005d930",
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-13T07:12:10.415Z",
    "ts": "2018-02-13T07:11:50.718+0000"
  }
```

#### Error

This API is used to log telemetry of any error that has occurred when a user is viewing content or playing games.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "err": "", // Required. Error code
    "errtype": "", // Required. Error type classification - "SYSTEM", "MOBILEAPP", "CONTENT"
    "stacktrace": "", // Required. Detailed error data/stack trace
    "pageid": "", // Optional. Page where the error has occured
    "object": OBJECT, // Optional. Object on which the error occured
    "plugin": PLUGIN // Optional. Plugin in which the error occured
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device",
      "env": "Genie",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "6.0"
      },
      "sid": "a8506bb6-edc5-4b59-b935-07dbabd1e9f3"
    },
    "edata": {
      "err": "ERR_TOKEN_INVALID",
      "errtype": "UNAUTHORIZED_ACCESS",
      "stacktrace": "{\"id\":\"api.upload.url\",\"ver\":\"1.0\",\"ts\":\"2018-02-12T17:04:21.726Z\",\"params\":{\"resmsgid\":\"id1\",\"msgid\":null,\"status\":\"failed\",\"err\":\"ERR_TOKEN_INVALID\",\"errmsg\":\"Access denied\"},\"responseCode\":\"UNAUTHORIZED_ACCESS\",\"result\":{}}"
    },
    "eid": "ERROR",
    "ets": 1518505910718,
    "mid": "58a11d49-22c8-4535-a28b-7a323005d930",
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-02-13T07:12:10.415Z",
    "ts": "2018-02-13T07:11:50.718+0000"
  }
```

#### Heartbeat

This API is used to log telemetry for heartbeat event to denote that the process is running.

The "edata" structure of Start is as follows:

```
data - Object //Required
{
  "edata": {
  }
}
```

#### Log

This API is used to log telemetry of generic log events. For example; API calls, service calls, app updates, etc.

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "", // Required. Type of log (system, process, api_access, api_call, job, app_update etc)
    "level": "", // Required. Level of the log. TRACE, DEBUG, INFO, WARN, ERROR, FATAL
    "message": "", // Required. Log message
    "pageid": "", // Optional. Page where the log event has happened
    "params": [{"key":"value"}] // Optional. Additional params in the log message
  }
}  
```

Example event data:

```
{
    "actor": {
      "id": "test-user1",
      "type": "User"
    },
    "eid": "LOG",
    "edata": {
      "level": "trace",
      "type": "api_call",
      "message": "successful",
      "params": [
        {
          "mode": "WIFI"
        }
      ]
    },
    "ver": "3.0",
    "@timestamp": "2018-02-12T13:00:24.918Z",
    "ets": 1518460198146,
    "context": {
      "channel": "test-channel",
      "env": "Genie",
      "sid": "85a8b3af-362f-48a5-9454-ac050dfe5a3a",
      "did": "test-device",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "1.0.25"
      },
      "cdata": []
    },
    "mid": "LOG:69e9ca45-c7e2-4a94-af50-50a4ff854cc9",
    "object": {
      "parent": {}
    },
    "tags": [
      "tag1"
    ],
    "ts": "2018-02-12T18:29:58.146+0000"
  }
```

#### Search

This API is used to log telemetry when a user triggers a search for any content, item or asset

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "",
    "query": "", // Required. Search query string 
    "filters": {}, // Optional. Additional filters (see the API spec)
    "sort": {}, // Optional. Additional sort parameters
    "correlationid": "", // Optional. Server generated correlation id (for mobile app's telemetry)
    "size": 333, // Required. Number of search results
    "topn": [{}] // Required. top N (configurable) results with their score
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "context": {
      "cdata": [],
      "channel": "test-channel",
      "did": "test-device",
      "env": "Genie",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android",
        "ver": "6.6"
      },
      "sid": "0ec7c32e-8058-4624-be72-623760c9c5c3"
    },
    "edata": {
      "correlationid": "abcd",
      "filters": {
        "compatibilityLevel": {
          "max": 3,
          "min": 1
        },
        "contentType": [
          "Story",
          "Worksheet",
          "Game",
          "Collection",
          "TextBook"
        ],
        "objectType": [
          "Content"
        ],
        "status": [
          "Live"
        ]
      },
      "query": "hshshshhs",
      "size": 0,
      "topn": [],
      "type": "Content"
    },
    "eid": "SEARCH",
    "ets": 1516001242930,
    "mid": "7cfb0376-45b6-4e05-885b-081b7097b938",
    "tags": [],
    "ver": "3.0",
    "@timestamp": "2018-01-15T07:29:12.553Z",
    "ts": "2018-01-15T07:27:22.930+0000"
  }
```

#### Metrics

This API is used to log telemetry for service business metrics (also accessible via health API).

The "edata" structure of Start is as follows:

```
data - Object - Required
{
  "edata": {
    "metric1": Int,
    "metric2": Int
    /// more metrics, each is a key value
  }
}
```

#### Summary

This API is used to log telemetry summary event

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "", // Required. Type of summary. Free text. "session", "app", "tool" etc
    "mode": "", // Optional.
    "starttime": Long, // Required. Epoch Timestamp of app start. Retrieved from first event.
    "endtime": Long, // Required. Epoch Timestamp of app end. Retrieved from last event.
    "timespent": Double, // Required. Total time spent by visitor on app in seconds excluding idle time.
    "pageviews": Long, // Required. Total page views per session(count of CP_IMPRESSION)
    "interactions": Long, // Required. Count of interact events
    "envsummary": [{ // Optional
        "env": String, // High level env within the app (content, domain, resources, community)
        "timespent": Double, // Time spent per env
        "visits": Long // count of times the environment has been visited
    }],
    "eventssummary": [{ // Optional
        "id": String, // event id such as CE_START, CE_END, CP_INTERACT etc.
        "count": Long // Count of events.
    }],
    "pagesummary": [{ // Optional
        "id": String, // Page id
        "type": String, // type of page - view/edit
        "env": String, // env of page
        "timespent": Double, // Time taken per page
        "visits": Long // Number of times each page was visited
    }]
  }
}
```

#### Exdata

This API is used to log telemetry for external data, while playing content

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": "", // Free flowing text. For ex: partnerdata, xapi etc
    "data": "" // Serialized data (can be either encrypted/encoded/stringified)
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "eid": "EXDATA",
    "edata": {
      "data": "\"dc:APA91bFi4zDhvOiymoL4uMszNfOBnPXTzPiohtVEQ5pmoKD7Hwo_1MYgZVdkk9fPne7xHP7cUu_eic6NU2RKldKiISefqilYJfpoCHe8ouidqLUNfhjKr\"",
      "type": "partnerdata"
    },
    "ver": "3.0",
    "@timestamp": "2018-02-13T07:43:25.271Z",
    "ets": 1518507781930,
    "context": {
      "channel": "test-channel",
      "env": "Genie",
      "sid": "8aaf8a9e-7c23-44e2-b262-dffc2935a3b7",
      "did": "test-device",
      "pdata": {
        "id": "producer1",
        "pid": "genieservice.android"
      },
      "cdata": []
    },
    "mid": "EXDATA:32b880df-a2d9-41e6-9821-9c9108fddbcc",
    "object": {
      "parent": {}
    },
    "tags": [],
    "ts": "2018-02-13T07:43:01.930+0000"
  }
```

#### End

This API is used to log telemetry while the user is closing or exiting the content or game

The "edata" structure of Start is as follows:

```
{
  "edata": {
    "type": , // Required. app, session, editor, player, workflow, assessment
    "mode": "", // Optional. Mode of start. For "player" it would be "play/edit/preview". For Workflow it would be Review/Flag/Publish. For editor it could be "content", "textbook", "generic", "lessonplan" etc
    "duration": , // Optional. Total duration from start to end in seconds
    "pageid": "", // Optional. Page/Stage id where the end has happened.
    "summary": [{"key":"value"}] // Optional. Summary of the actions done between start and end. For ex: "progress" for player session, "nodesModified" for collection editor
  }
}
```

Example event data:

```
{
    "actor": {
      "id": "test-user",
      "type": "User"
    },
    "eid": "END",
    "edata": {
      "mode": "play",
      "duration": 21,
      "summary": [
        {
          "progress": 50
        }
      ],
      "type": "player",
      "pageid": "play_video"
    },
    "ver": "3.0",
    "@timestamp": "2018-02-13T08:55:16.041Z",
    "ets": 1518512093695,
    "context": {
      "channel": "test-channel",
      "env": "ContentPlayer",
      "sid": "575d41ea-01fb-4e5e-86e0-5af15d82c7ee",
      "did": "test-device",
      "pdata": {
        "id": "producer",
        "pid": "genieservice.android",
        "ver": "1.0"
      },
      "cdata": [ ]
    },
    "mid": "END:54b2e8ea-e376-4d91-94eb-9cd4356a934e",
    "object": {
      "id": "test-content",
      "type": "Content",
      "ver": "1.0"
    },
    "tags": [
      "tag1"
    ],
    "ts": "2018-02-13T08:54:53.695+0000"
  }
```
