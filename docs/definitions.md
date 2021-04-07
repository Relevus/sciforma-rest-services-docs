# Definitions Endpoint
Relative URL: */v1/definitions*

## Available services
  - [Get definitions](#get-definitions)
  
- ### GET DEFINITION

**Method**: GET

**Path**: */*

**Description**: Action to add or modify the values and notes in the definitions	

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| name | Name of the definition (projects, resources, tasks, timesheets, users, globals, dataviews) | :white_check_mark: |
| category |  Name of the dataview. It's required when the name is globals or dataviews. (Backlog Item, Global Actions) | :white_check_mark: |

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | There is a problem parsing the json content, check your json payload |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
    "name": "Project",
    "attributes": [
        {
            "dataType": "STRING",
            "name": "ID",
            "code": "id",
            "id": true,
            "initializer": true
        },
        {
            "dataType": "STRING",
            "name": "Name",
            "code": "name",
            "initializer": true
        },
        {
            "dataType": "DOUBLE",
            "name": "Version ID",
            "code": "versionID",
            "exclude": true
        },
        {
            "dataType": "STRING_LIST",
            "name": "allocatedResources",
            "code": "allocatedResources",
            "exclude": true
        },
        {
            "dataType": "STRING",
            "kind": "NORMAL",
            "name": "Manager 1",
            "code": "manager1"
        },
        {
            "dataType": "STRING",
            "kind": "NORMAL",
            "name": "Manager 2",
            "code": "manager2"
        },
        {
            "dataType": "STRING",
            "kind": "NORMAL",
            "name": "Manager 3",
            "code": "manager3"
        },
        {
            "dataType": "DATE",
            "kind": "NORMAL",
            "name": "Start Constraint",
            "code": "startConstraint"
        }
    ]
}
```
