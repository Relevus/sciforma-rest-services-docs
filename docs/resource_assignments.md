# :construction_worker: Resource Assignments Endpoint
Relative URL: */v1/projects/**{projectId}**/resourceAssignments

> Note: With the REST-API you can get and push data from projects in **WORKING** or **PUBLISHED** state. Use the __Project-Version__ request header to indicate the version you want to get.

## Available services
  - [Assignments by task](#assignments-by-task)
  - [Assignments by resource](#assignments-by-resource)

---
- ### ASSIGNMENTS BY TASK

**Method**: GET

**Path**: /task/*{taskId}*

**Description**: Allows to obtain all the assignments associated with the task	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project common identifier | :white_check_mark: |
| taskId | Task common identifier | :white_check_mark: |

**Query parameters**: NONE
> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**: NONE

| Code | Description | Data type |
| --- | --- | :---: |
| distributed.fromDate | Indicates the initial date for the search of distributed fields. It requires 'distributed.toDate' filter. | Date in format yyyy-MM-dd |
| distributed.toDate | Indicates the final date for the search of distributed fields. It requires 'distributed.fromDate' filter. | Date in format yyyy-MM-dd |

> Note: Check the guidelines for using [filters](filter.md)

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 404 | No object found for the id '{0}' |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json

```
<br/>

---

- ### ASSIGNMENTS BY RESOURCE

**Method**: GET

**Path**: /resources/*{resourceId}*

**Description**: Allows to obtain all the assignments of a resource in a project	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project common identifier | :white_check_mark: |
| resourceId | Resource common identifier | :white_check_mark: |

**Query parameters**: NONE
> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**: NONE

| Code | Description | Data type |
| --- | --- | :---: |
| distributed.fromDate | Indicates the initial date for the search of distributed fields. It requires 'distributed.toDate' filter. | Date in format yyyy-MM-dd |
| distributed.toDate | Indicates the final date for the search of distributed fields. It requires 'distributed.fromDate' filter. | Date in format yyyy-MM-dd |

> Note: Check the guidelines for using [filters](filter.md)

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 404 | No object found for the id '{0}' |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "numberOfRecords": 3,
    "records": [
        {
            "object": {
                "totalEffort": [
                    {
                        "startDate": "2020-09-21 00:00:00",
                        "finishDate": "2020-09-22 00:00:00",
                        "value": 1.6
                    },
                    {
                        "startDate": "2020-09-22 00:00:00",
                        "finishDate": "2020-09-23 00:00:00",
                        "value": 1.6
                    },
                    {
                        "startDate": "2020-09-23 00:00:00",
                        "finishDate": "2020-09-24 00:00:00",
                        "value": 1.6
                    },
                    {
                        "startDate": "2020-09-24 00:00:00",
                        "finishDate": "2020-09-25 00:00:00",
                        "value": 1.6
                    },
                    {
                        "startDate": "2020-09-25 00:00:00",
                        "finishDate": "2020-09-26 00:00:00",
                        "value": 1.6
                    }
                ],
                "id": "PGF368",
                "name": "Apple, Michael",
                "taskIID": 484301
            }
        },
        {
            "object": {
                "totalEffort": [],
                "id": "PGF386",
                "name": "Apple, Michael",
                "taskIID": 484338
            }
        },
        {
            "object": {
                "totalEffort": [
                    {
                        "startDate": "2020-09-21 00:00:00",
                        "finishDate": "2020-09-22 00:00:00",
                        "value": 0.20134228187919465
                    },
                    {
                        "startDate": "2020-09-22 00:00:00",
                        "finishDate": "2020-09-23 00:00:00",
                        "value": 0.20134228187919465
                    },
                    {
                        "startDate": "2020-09-23 00:00:00",
                        "finishDate": "2020-09-24 00:00:00",
                        "value": 0.20134228187919465
                    },
                    {
                        "startDate": "2020-09-24 00:00:00",
                        "finishDate": "2020-09-25 00:00:00",
                        "value": 0.20134228187919465
                    },
                    {
                        "startDate": "2020-09-25 00:00:00",
                        "finishDate": "2020-09-26 00:00:00",
                        "value": 0.20134228187919465
                    }
                ],
                "id": "PGF386",
                "name": "Apple, Michael",
                "taskIID": 484360
            }
        }
    ]
}
```
