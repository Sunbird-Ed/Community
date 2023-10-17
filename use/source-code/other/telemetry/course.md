# Trackable Collection

"Course" is a type of Trackable collection in Sunbird. A trackable Collection is one in which a User's progress can be measured.\
A course (Trackable Collection) will have the following attributes associated with it.

* Course Unit(collection os resources grouped together)
* Resources
* Collection
* Batches
  * Batches will have a Start Date of the batch
  * Batches can have a End Date of the batch
  * Batches can have a Enrolment End date
  * Batches can have mentors to the batch
  * Batches can have Certificates for a batch
  * Batches can have a discussion

This Page will try to explain and understand the user flow and telemetry that will be created for a user journey

## Step 1:

A user tries to search a course with the course name or ID or QRCODE an Impression event will be triggerd\\

```
{
      "eid": "IMPRESSION",
      "ets": 1672903979125,
      "ver": "3.0",
      "mid": "IMPRESSION:9233e99da2ae1364c4050561a6b97b6f",
      "actor": {
        "id": "88e71f0a-c9b3-4449-b076-e468027e360e",
        "type": "User"
      },
      "context": {
        "channel": "0126796199493140480",
        "pdata": {
          "id": "{<environment in which the telemetry was generated>}",
          "ver": "5.1.0",
          "pid": "sunbird-portal"
        },
        "env": "library",
        "sid": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
        "did": "560884cd9da0e8e61c084559ca2a7b1b",
        "cdata": [
          {
            "id": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
            "type": "UserSession"
          },
          {
            "id": "Desktop",
            "type": "Device"
          },
          {
            "id": "joy",
            "type": "Theme"
          }
        ],
        "rollup": {
          "l1": "0126796199493140480"
        },
        "uid": "88e71f0a-c9b3-4449-b076-e468027e360e"
      },
      "object": {},
      "tags": [
        "0126796199493140480"
      ],
      "edata": {
        "type": "view",
        "pageid": "library-search",
        "uri": "/search/Library/1?key={<Search workd from the user>}&selectedTab=all",
        "subtype": "pageexit",
        "duration": 0.026,
        "visits": []
      }
    }
```

## Step 2:

Once Searched a Course name and got the response user clicks on the course card the following Interact telemetry event will be generated

```
{
      "eid": "INTERACT",
      "ets": 1672903979118,
      "ver": "3.0",
      "mid": "INTERACT:595a19d6ceebc0c6cd5b7fb4f156c4f7",
      "actor": {
        "id": "88e71f0a-c9b3-4449-b076-e468027e360e",
        "type": "User"
      },
      "context": {
        "channel": "0126796199493140480",
        "pdata": {
          "id": "{<environment in which the telemetry was generated>}",
          "ver": "5.1.0",
          "pid": "sunbird-portal"
        },
        "env": "library",
        "sid": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
        "did": "560884cd9da0e8e61c084559ca2a7b1b",
        "cdata": [
          {
            "id": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
            "type": "UserSession"
          },
          {
            "id": "Desktop",
            "type": "Device"
          },
          {
            "id": "joy",
            "type": "Theme"
          }
        ],
        "rollup": {
          "l1": "0126796199493140480"
        },
        "uid": "88e71f0a-c9b3-4449-b076-e468027e360e"
      },
      "object": {
        "id": "do_2136796955344240641444",
        "type": "Course",
        "ver": "3",
        "rollup": {}
      },
      "tags": [
        "0126796199493140480"
      ],
      "edata": {
        "id": "content-card",
        "type": "click",
        "pageid": "home-search"
      }
    }
```

## Step 3

Once the user clicks on the course card and lands into the course TOC page there will be a impression event will be generated as following

```
{
      "eid": "IMPRESSION",
      "ets": 1672903979343,
      "ver": "3.0",
      "mid": "IMPRESSION:07834e60105c059ca0210984472c2727",
      "actor": {
        "id": "88e71f0a-c9b3-4449-b076-e468027e360e",
        "type": "User"
      },
      "context": {
        "channel": "0126796199493140480",
        "pdata": {
          "id": "{<environment in which the telemetry was generated>}",
          "ver": "5.1.0",
          "pid": "sunbird-portal"
        },
        "env": "Course",
        "sid": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
        "did": "560884cd9da0e8e61c084559ca2a7b1b",
        "cdata": [
          {
            "id": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
            "type": "UserSession"
          },
          {
            "id": "Desktop",
            "type": "Device"
          },
          {
            "id": "joy",
            "type": "Theme"
          }
        ],
        "rollup": {
          "l1": "0126796199493140480"
        },
        "uid": "88e71f0a-c9b3-4449-b076-e468027e360e"
      },
      "object": {
        "id": "do_2136796955344240641444",
        "type": "Course",
        "ver": "1.0",
        "rollup": {
          "l1": "do_2136796955344240641444"
        }
      },
      "tags": [
        "0126796199493140480"
      ],
      "edata": {
        "type": "view",
        "pageid": "course-details",
        "uri": "/learn/course/{<ID of the course>}"
      }
    }
```

## Step 4:

User needs to join a batch of a course to take one so once user clicks on the join batch button an interact event is generated as follows

```
{
      "eid": "INTERACT",
      "ets": 1672904391516,
      "ver": "3.0",
      "mid": "INTERACT:9fb8085f1a8122c18cfc96ec81115575",
      "actor": {
        "id": "88e71f0a-c9b3-4449-b076-e468027e360e",
        "type": "User"
      },
      "context": {
        "channel": "0126796199493140480",
        "pdata": {
          "id": "{<environment in which the telemetry was generated>}",
          "ver": "5.1.0",
          "pid": "sunbird-portal"
        },
        "env": "Course",
        "sid": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
        "did": "560884cd9da0e8e61c084559ca2a7b1b",
        "cdata": [
          {
            "id": "jEczuH3QGIAyaxgCwNswZEQOB_rkSB5f",
            "type": "UserSession"
          },
          {
            "id": "Desktop",
            "type": "Device"
          },
          {
            "id": "joy",
            "type": "Theme"
          }
        ],
        "rollup": {
          "l1": "0126796199493140480"
        },
        "uid": "88e71f0a-c9b3-4449-b076-e468027e360e"
      },
      "object": {
        "id": "{<ID of the course>}",
        "type": "Course",
        "ver": "3",
        "rollup": {
          "l1": "{<ID of the course>}"
        }
      },
      "tags": [
        "0126796199493140480"
      ],
      "edata": {
        "id": "join-course",
        "type": "click",
        "pageid": "course-consumption"
      }
    }

```
