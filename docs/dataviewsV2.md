# Dataviews Endpoint
Relative URL: */v2/dataviews*

*The functionality of this endpoint, the available methods and their parameters are the same as its predecessor _v1_.

This endpoint changes the way data records are retrieved from dataviews and reflects changes to the Sciforma GUI more quickly.*

## Available services
  - [Get dataviews](#get-dataviews)
  - [Get one dataview record](#get-one-dataview-record)
  - [Save dataviews](#save-dataviews)
  
---
- ### GET DATAVIEWS

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of records from a type of dataview

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| dvName | Name of the dataview (example: 'Backlog Items') | :white_check_mark: |
| parentId | Identifier of the parent field accesor | :white_check_mark: |
| parentType | Type of FieldAccesor (projects, resources, tasks, timesheets, users). When not set, it is assumed to be a 'globals' dataview | :x: |

> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**:

> Note: Check the guidelines for using [filters](filter.md)

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | 'filter' param has an invalid value. Check your filters. |
| 404 | No object found for the id '{0}' |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "records": [
        {
            "object": {
                "permissions": "System Default",
                "workflowStateVote": "New",
                "key": "JOZHYZZN-4",
                "name": "",
                "uid": 975656,
                "number": 4,
                "acceptanceTest": "",
                "businessValue": 0,
                "completedDate": "1969-12-31 15:59:59",
                "createdDate": "2019-04-08 01:35:45",
                "description": "",
                "dueDate": "1969-12-31 15:59:59",
                "epic": "",
                "iteration": "",
                "link": "",
                "menu": "",
                "owner": "",
                "relatedStory": "",
                "singleTask": false,
                "effort": 0,
                "stretchItem": false,
                "team": "",
                "teamUsers": [],
                "template": false,
                "templateComments": "",
                "toDoEffort": 0,
                "type": "Story"
            }
        },
        {
            "object": {
                "permissions": "System Default",
                "workflowStateVote": "In-Progress",
                "key": "JOZHYZZN-2",
                "name": "Story 1",
                "uid": 973731,
                "number": 2,
                "acceptanceTest": "",
                "businessValue": 0,
                "completedDate": "1969-12-31 15:59:59",
                "createdDate": "2018-11-27 00:56:31",
                "description": "",
                "dueDate": "1969-12-31 15:59:59",
                "epic": "",
                "iteration": "Sprint1",
                "link": "",
                "menu": "",
                "owner": "",
                "relatedStory": "",
                "singleTask": false,
                "effort": 0,
                "stretchItem": false,
                "team": "",
                "teamUsers": [],
                "template": false,
                "templateComments": "",
                "toDoEffort": 0,
                "type": "Story"
            }
        }
    ],
    "numberOfRecords": 2
}
```
<br/>

---
- ### GET ONE DATAVIEW RECORD

**Method**: GET

**Path**: */{dataviewId}*

**Description**: Action to obtain one dataview record	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| dataviewId | Dataview identifier | :white_check_mark: |

**Query parameters**

| Code | Description | Required |
| --- | --- | :---: |
| dvName | Name of the dataview (example: 'Backlog Items') | :white_check_mark: |
| parentId | Identifier of the parent field accesor | :white_check_mark: |
| parentType | Type of FieldAccesor (projects, resources, tasks, timesheets, users). When not set, it is assumed to be a 'globals' dataview | :x: |

> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**:

> Note: Check the guidelines for using [filters](filter.md)

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | 'filter' param has an invalid value. Check your filters. |
| 404 | No object found for the id '{0}' |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "object": {
        "permissions": "System Default",
        "workflowStateVote": "In-Progress",
        "key": "JOZHYZZN-2",
        "name": "Story 1",
        "uid": 973731,
        "number": 2,
        "acceptanceTest": "",
        "businessValue": 0,
        "completedDate": "1969-12-31 15:59:59",
        "createdDate": "2018-11-27 00:56:31",
        "description": "",
        "dueDate": "1969-12-31 15:59:59",
        "epic": "",
        "iteration": "Sprint1",
        "link": "",
        "menu": "",
        "owner": "",
        "relatedStory": "",
        "singleTask": false,
        "effort": 0,
        "stretchItem": false,
        "team": "",
        "teamUsers": [],
        "template": false,
        "templateComments": "",
        "toDoEffort": 0,
        "type": "Story"
    }
}
```
<br/>

---

- ### SAVE DATAVIEWS

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single dataview record or a list of dataview records

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

> Note: Request body varies depending on the type of dataview, in general, the user must know what are the dataview definition. Check [definitions](definitions.md)

Sample request

```json
{
    "object": {
        "permissions": "System Default",
        "key": "JOZHYZZN-2",
        "name": "Story 1",
        "uid": 973731,
        "number": 2,
        "acceptanceTest": "",
        "businessValue": 0,
        "completedDate": "1969-12-31 15:59:59",
        "createdDate": "2018-11-27 00:56:31",
        "description": "",
        "dueDate": "1969-12-31 15:59:59",
        "epic": "",
        "iteration": "Sprint1",
        "link": "",
        "menu": "",
        "owner": "",
        "relatedStory": "",
        "singleTask": false,
        "effort": 0,
        "stretchItem": false,
        "team": "",
        "teamUsers": [],
        "template": false,
        "templateComments": "",
        "toDoEffort": 0,
        "type": "Story",
        "workflowConfiguration": {
            "workflow": "Workflow",
            "workflowState": "In-Progress"
        }
    }
}
```

> Note: When you need to change the workflow status, remove the "workflowStateVote" attribute and then add the "workflowConfiguration" object with two new properties: "workflow" with the flow name and "workflowState" with the new state.

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | There is a problem parsing the json content, check your json payload |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "records": [
        {
            "id": "JX6JJX1S",
            "status": "SUCCESS",
            "isNew": true,
            "validationMessages": [
                {
                    "status": "WARNING",
                    "message": "Field 'workPackageTaskID' is read-only. Value skipped."
                }
            ]
        }
    ]
}
```
