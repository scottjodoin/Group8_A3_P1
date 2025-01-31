# Music Events in Manitoba

This API provides information about upcoming music-related events in Manitoba. Results given will be based on a provided latitude, longitude, and date.

The API response will contain the name of music events in Manitoba, the headlining performers, their respective venues and dates, admission costs, and website and tags that are describing the event. More information about the response can be found in the [sample response](https://github.com/qinh3uofm/Group8_A3_P1#sample-response) section.

## Endpoints

There is one endpoint for our API. Use a GET a request to get a response from the API. 

GET /events → Lists all music events that will happen in Manitoba.

Parameters

|Parameter|Type|Required|Description|
|---|---|---|---|
|`lat`|float|Yes|The latitude of the event|
|`lon`|float|yes|The longitude of the event|
|`date`|String|yes|The date of the event|

## Sample Request
This a sample request to get information about Manitoba music events for a given location in longitude and latitude as well as the date of the event.
```
https://api.manitobamusicevents.org/events?lat=”44.968046”&lon=”-94.420307”&date=”2022-03-31”
```
## Sample Response
The response is formatted in JSON. The response will contain information regarding the event including: the event name, the headlining performers, the name of the venue, the address, its location given in longitude and latitude, the event date and time, as well as the cost to attend. The response also includes the event website and tags describing the event.

```json
 {
  "results": [
  {
    "eventName" : "Oktoberfest",
    "group" : {
        "groupName" : "2-Direction",
        "genre" : "Metal"
    },
    "venueName" : "Centennial Concert Hall",
    "venueAddress" : "555 Main Street, Winnipeg",
    "lat" : 44.968046,
    "long" : -94.420307,
    "date" : "2022-03-31",
    "time" : "7:30 PM CST",
    "cost" : "15.00",
    "tags" : ["oktoberfest", "party"]
  },
  {
    "eventName" : "DunkMania",
    "group" : {
        "groupName" : "BBPlayersWhoSings",
        "genre" : "Hip-Hop"
    },
    "venueName" : "University of Manitoba",
    "venueAddress" : "33 Chancellor Circle, Winnipeg",
    "lat" : 44.33328,
    "long" : -89.132008,
    "date" : "2022-03-31",
    "time" : "8:30 PM CST",
    "cost" : "15.00",
    "tags" : ["nba", "dunk"]
  }
  ],
 "status":"OK"
}


```

## Response Object Type Definitions

The type definitions for the response JSON object:


| Response   |  Type  |          Description                               |
|------------|--------|----------------------------------------------------|
|`eventName` |string|Name of the event|
|`groupName` |string|Group name of performers|
|`genre` |string| Type of music|
| `venueName`       | string | The name of the venue                        |
| `venueAddress` | string | The address of the venue                 |
| `lat`   | float    |The latitude of the event|
| `long`| float | The longitude of the event                       |
| `date`| string | The date of the event                      |
| `time`   | HH:MM format in CST    | The time of the event |
|`cost` |float| The cost of ticket|
|`tags`|  String list| Tags of events|
