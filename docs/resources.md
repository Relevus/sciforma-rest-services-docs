# Resources Endpoint
Relative URL: */v1/resources*

## Available services
  - [Get resources](#get-resources)
  - [Get one resource record](#get-one-resource-record)
  - [Save resources](#save-resources)
  
---
- ### GET RESOURCES

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of records from a type of resource

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**:

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
                "id": "ADMIN",
                "organization": "ABC Corporation",
                "writable": "No",
                "number": 41,
                "rBS": "A",
                "firstName": "",
                "middleName": "",
                "lastName": "Administrator",
                "name": "Administrator",
                "cost": [
                    {
                        "startDate": "1969-12-31 16:00:00",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": 0
                    }
                ],
                "availability": [
                    {
                        "startDate": "1969-12-31 16:00:00",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": 1
                    }
                ],
                "calendarStatus": "SUBMITTED",
                "organizationHistory": [
                    {
                        "startDate": "2019-04-10 10:14:08",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": "ABC Corporation"
                    }
                ],
                "jobClassification": "Employee",
                "skills": [],
                "defaultRate": 1,
                "emailAddress1": "",
                "emailAddress2": "",
                "emailAddress3": "",
                "status": "ACTIVE",
                "timeEntrySet": "None",
                "timeEntryOverrideSet": "None",
                "timeEntryOverrideStart": "1969-12-31 15:59:59",
                "timeEntryOverrideStop": "1969-12-31 15:59:59",
                "availableEffort": [],
                "actualEffort": [],
                "remainingEffort": [],
                "totalEffort": [],
                "actualCost": [],
                "remainingCost": [],
                "totalCost": [],
                "percentageAllocated": [],
                "userRole": "Super User",
                "startDate": "1969-12-31 15:59:59",
                "endDate": "1969-12-31 15:59:59",
                "shouldLevel": true,
                "referencedUser": "Administrator",
                "actualEffortAdjustment": [],
                "totalCommitmentEffort": [],
                "submittedCommitmentEffort": [],
                "pendingOrganization": "",
                "mappedPendingOrganization": "",
                "pendingAvailableEffort": [],
                "internalID": 2,
                "totalCommitmentRate": [],
                "submittedCommitmentRate": [],
                "calendarFeeds": [],
                "expectedEffort": 0,
                "permissions": "*System Default",
                "isUser": true,
                "remainingEffortMix": [],
                "remainingCostMix": [],
                "actualEffortMix": [],
                "actualCostMix": [],
                "totalEffortMix": [],
                "totalCostMix": [],
                "requestedEffort": 0,
                "resourceText": "",
                "menu": "",
                "expenseCalculationMethod": "Per Meal",
                "userPicture": "/tmp/tomcat8-tomcat8-tmp/sci5008824816169313459.png",
                "costCenter": ""
            }
        },
        {
            "object": {
                "id": "JDOW4",
                "organization": "ABC Corporation.Non-Union",
                "writable": "No",
                "number": 106,
                "rBS": "A.Code2000",
                "firstName": "John",
                "middleName": "",
                "lastName": "Doe",
                "name": "Doe, John",
                "cost": [
                    {
                        "startDate": "1969-12-31 04:00:00",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": 150
                    },
                    {
                        "startDate": "+292278994-08-17 00:12:55",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": 0
                    }
                ],
                "availability": [
                    {
                        "startDate": "1969-12-31 04:00:00",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": 1
                    },
                    {
                        "startDate": "+292278994-08-17 00:12:55",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": 0
                    }
                ],
                "calendarStatus": "",
                "organizationHistory": [
                    {
                        "startDate": "1969-12-31 16:00:00",
                        "finishDate": "2019-05-29 01:42:09",
                        "value": "ABC Corporation.Non-Union"
                    },
                    {
                        "startDate": "2019-05-29 01:42:09",
                        "finishDate": "2019-06-13 17:22:31",
                        "value": "ABC Corporation"
                    },
                    {
                        "startDate": "2019-06-13 17:22:31",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": "ABC Corporation.Non-Union"
                    }
                ],
                "jobClassification": "Employee.R&D.Product Engineer",
                "skills": [],
                "defaultRate": 1,
                "emailAddress1": "",
                "emailAddress2": "",
                "emailAddress3": "",
                "status": "ACTIVE",
                "timeEntrySet": "None",
                "timeEntryOverrideSet": "None",
                "timeEntryOverrideStart": "1969-12-31 15:59:59",
                "timeEntryOverrideStop": "1969-12-31 15:59:59",
                "availableEffort": [],
                "actualEffort": [],
                "remainingEffort": [],
                "totalEffort": [],
                "actualCost": [],
                "remainingCost": [],
                "totalCost": [],
                "percentageAllocated": [],
                "userRole": "*Administrator",
                "startDate": "2019-04-30 23:00:00",
                "endDate": "2019-05-31 22:59:59",
                "shouldLevel": true,
                "referencedUser": "Doe, John",
                "actualEffortAdjustment": [],
                "totalCommitmentEffort": [],
                "submittedCommitmentEffort": [],
                "pendingOrganization": "",
                "mappedPendingOrganization": "",
                "pendingAvailableEffort": [],
                "internalID": 995101,
                "totalCommitmentRate": [],
                "submittedCommitmentRate": [],
                "calendarFeeds": [],
                "expectedEffort": 0,
                "permissions": "*System Default",
                "isUser": true,
                "remainingEffortMix": [],
                "remainingCostMix": [],
                "actualEffortMix": [],
                "actualCostMix": [],
                "totalEffortMix": [],
                "totalCostMix": [],
                "requestedEffort": 0,
                "resourceText": "",
                "menu": "",
                "expenseCalculationMethod": "Per Meal",
                "userPicture": "",
                "costCenter": "TRANSACTIONAL/OPEX"
            }
        }
    ],
    "numberOfRecords": 2
}
```
<br/>

---
- ### GET ONE RESOURCE RECORD

**Method**: GET

**Path**: */{resourceId}*

**Description**: Action to obtain one resource record	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| resourceId | Resource identifier | :white_check_mark: |

**Query parameters**

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
        "id": "JDOW1",
        "organization": "ABC Corporation.Non-Union",
        "writable": "No",
        "number": 104,
        "rBS": "A.Code2000",
        "firstName": "John",
        "middleName": "",
        "lastName": "Doe",
        "name": "Doe, John",
        "cost": [
            {
                "startDate": "1969-12-31 04:00:00",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 150
            },
            {
                "startDate": "+292278994-08-17 00:12:55",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 0
            }
        ],
        "availability": [
            {
                "startDate": "1969-12-31 04:00:00",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 1
            },
            {
                "startDate": "+292278994-08-17 00:12:55",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 0
            }
        ],
        "calendarStatus": "",
        "organizationHistory": [
            {
                "startDate": "1969-12-31 16:00:00",
                "finishDate": "2019-05-29 01:42:09",
                "value": "ABC Corporation.Non-Union"
            },
            {
                "startDate": "2019-05-29 01:42:09",
                "finishDate": "2019-06-13 17:18:25",
                "value": "ABC Corporation"
            },
            {
                "startDate": "2019-06-13 17:18:25",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": "ABC Corporation.Non-Union"
            }
        ],
        "jobClassification": "Employee.R&D.Product Engineer",
        "skills": [],
        "defaultRate": 1,
        "emailAddress1": "",
        "emailAddress2": "",
        "emailAddress3": "",
        "status": "ACTIVE",
        "timeEntrySet": "None",
        "timeEntryOverrideSet": "None",
        "timeEntryOverrideStart": "1969-12-31 15:59:59",
        "timeEntryOverrideStop": "1969-12-31 15:59:59",
        "availableEffort": [],
        "actualEffort": [],
        "remainingEffort": [],
        "totalEffort": [],
        "actualCost": [],
        "remainingCost": [],
        "totalCost": [],
        "percentageAllocated": [],
        "userRole": "*Administrator",
        "startDate": "2019-04-30 23:00:00",
        "endDate": "2019-05-31 22:59:59",
        "shouldLevel": true,
        "referencedUser": "Doe, John",
        "actualEffortAdjustment": [],
        "totalCommitmentEffort": [],
        "submittedCommitmentEffort": [],
        "pendingOrganization": "",
        "mappedPendingOrganization": "",
        "pendingAvailableEffort": [],
        "internalID": 995019,
        "totalCommitmentRate": [],
        "submittedCommitmentRate": [],
        "calendarFeeds": [],
        "expectedEffort": 0,
        "permissions": "*System Default",
        "isUser": true,
        "remainingEffortMix": [],
        "remainingCostMix": [],
        "actualEffortMix": [],
        "actualCostMix": [],
        "totalEffortMix": [],
        "totalCostMix": [],
        "requestedEffort": 0,
        "resourceText": "",
        "menu": "",
        "expenseCalculationMethod": "Per Meal",
        "userPicture": "",
        "costCenter": "TRANSACTIONAL/OPEX"
    }
}
```
<br/>

---

- ### SAVE RESOURCES

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single resource record or a list of resource records

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |
| Sciforma-Create-User | true / false | Indicates whether an associated user will be created for a new resource. FALSE by default. | :x: |
| Sciforma-Update-User | true / false | Indicates whether an associated user will be created / updated for an existing resource. FALSE by default. | :x: |
| preLoadAllRecords | true / false | Indicates whether just before processing the entire request the full resource list should be loaded. It is recomended when sending multiple resources in a sigle request, it will speed up the processing time. FALSE by default. | :x: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

| Code | Description | Required |
| --- | --- | :---: |
| id | Equivalent to the field 'ID' in sciforma's 'Resource' objects| :white_check_mark: *[^1]* |
| organization | Equivalent to the field 'Organization' in sciforma's 'Resource' objects| :white_check_mark: *[^1]* |
| user.object | Equivalent to sending a Sciforma' [USER](users.md) with all its properties | :white_check_mark: *[^1]* |
| writable | Equivalent to the field 'Writable' in sciforma's 'Resource' objects| :x: *[^1]* |
| number | Equivalent to the field '#' in sciforma's 'Resource' objects| :x: *[^1]* |
| rBS | Equivalent to the field 'RBS' in sciforma's 'Resource' objects| :x: *[^1]* |
| firstName | Equivalent to the field 'First Name' in sciforma's 'Resource' objects| :x: *[^1]* |
| middleName | Equivalent to the field 'Middle Name' in sciforma's 'Resource' objects| :x: *[^1]* |
| lastName | Equivalent to the field 'Last Name' in sciforma's 'Resource' objects| :x: *[^1]* |
| name | Equivalent to the field 'Name' in sciforma's 'Resource' objects| :x: *[^1]* |
| cost | Equivalent to the field 'Cost' in sciforma's 'Resource' objects| :x: *[^1]* |
| availability | Equivalent to the field 'Availability' in sciforma's 'Resource' objects| :x: *[^1]* |
| calendar | Equivalent to the field 'Calendar' in sciforma's 'Resource' objects| :x: *[^1]* |
| pendingCalendar | Equivalent to the field 'Pending Calendar' in sciforma's 'Resource' objects| :x: *[^1]* |
| calendarStatus | Equivalent to the field 'Calendar Status' in sciforma's 'Resource' objects| :x: *[^1]* |
| organizationHistory | Equivalent to the field 'Organization History' in sciforma's 'Resource' objects| :x: *[^1]* |
| jobClassification | Equivalent to the field 'Job Classification' in sciforma's 'Resource' objects| :x: *[^1]* |
| skills | Equivalent to the field 'Skills' in sciforma's 'Resource' objects| :x: *[^1]* |
| defaultRate | Equivalent to the field 'Default Rate' in sciforma's 'Resource' objects| :x: *[^1]* |
| emailAddress1 | Equivalent to the field 'Email Address 1' in sciforma's 'Resource' objects| :x: *[^1]* |
| emailAddress2 | Equivalent to the field 'Email Address 2' in sciforma's 'Resource' objects| :x: *[^1]* |
| emailAddress3 | Equivalent to the field 'Email Address 3' in sciforma's 'Resource' objects| :x: *[^1]* |
| status | Equivalent to the field 'Status' in sciforma's 'Resource' objects| :x: *[^1]* |
| timeEntrySet | Equivalent to the field 'Time Entry Set' in sciforma's 'Resource' objects| :x: *[^1]* |
| timeEntryOverrideSet | Equivalent to the field 'Time Entry Override Set' in sciforma's 'Resource' objects| :x: *[^1]* |
| timeEntryOverrideStart | Equivalent to the field 'Time Entry Override Start' in sciforma's 'Resource' objects| :x: *[^1]* |
| timeEntryOverrideStop | Equivalent to the field 'Time Entry Override Stop' in sciforma's 'Resource' objects| :x: *[^1]* |
| availableEffort | Equivalent to the field 'Available Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| actualEffort | Equivalent to the field 'Actual Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| remainingEffort | Equivalent to the field 'Remaining Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| totalEffort | Equivalent to the field 'Total Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| actualCost | Equivalent to the field 'Actual Cost' in sciforma's 'Resource' objects| :x: *[^1]* |
| remainingCost | Equivalent to the field 'Remaining Cost' in sciforma's 'Resource' objects| :x: *[^1]* |
| totalCost | Equivalent to the field 'Total Cost' in sciforma's 'Resource' objects| :x: *[^1]* |
| percentageAllocated | Equivalent to the field '% Allocated' in sciforma's 'Resource' objects| :x: *[^1]* |
| userRole | Equivalent to the field 'User Role' in sciforma's 'Resource' objects| :x: *[^1]* |
| startDate | Equivalent to the field 'Start Date' in sciforma's 'Resource' objects| :x: *[^1]* |
| endDate | Equivalent to the field 'End Date' in sciforma's 'Resource' objects| :x: *[^1]* |
| shouldLevel | Equivalent to the field 'Should Level' in sciforma's 'Resource' objects| :x: *[^1]* |
| referencedUser | Equivalent to the field 'Referenced User' in sciforma's 'Resource' objects| :x: *[^1]* |
| baseCalendar | Equivalent to the field 'Base Calendar' in sciforma's 'Resource' objects| :x: *[^1]* |
| actualEffortAdjustment | Equivalent to the field 'Actual Effort Adjustment' in sciforma's 'Resource' objects| :x: *[^1]* |
| totalCommitmentEffort | Equivalent to the field 'Total Commitment Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| submittedCommitmentEffort | Equivalent to the field 'Submitted Commitment Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| pendingOrganization | Equivalent to the field 'Pending Organization' in sciforma's 'Resource' objects| :x: *[^1]* |
| mappedPendingOrganization | Equivalent to the field 'Mapped Pending Organization' in sciforma's 'Resource' objects| :x: *[^1]* |
| pendingAvailableEffort | Equivalent to the field 'Pending Available Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| internalID | Equivalent to the field 'Internal ID' in sciforma's 'Resource' objects| :x: *[^1]* |
| totalCommitmentRate | Equivalent to the field 'Total Commitment Rate' in sciforma's 'Resource' objects| :x: *[^1]* |
| submittedCommitmentRate | Equivalent to the field 'Submitted Commitment Rate' in sciforma's 'Resource' objects| :x: *[^1]* |
| calendarFeeds | Equivalent to the field 'Calendar Feeds' in sciforma's 'Resource' objects| :x: *[^1]* |
| expectedEffort | Equivalent to the field 'Expected Effort' in sciforma's 'Resource' objects| :x: *[^1]* |
| permissions | Equivalent to the field 'Permissions' in sciforma's 'Resource' objects| :x: *[^1]* |
| isUser | Equivalent to the field 'Is User' in sciforma's 'Resource' objects| :x: *[^1]* |
| remainingEffortMix | Equivalent to the field 'Remaining Effort (mix)' in sciforma's 'Resource' objects| :x: *[^1]* |
| remainingCostMix | Equivalent to the field 'Remaining Cost (mix)' in sciforma's 'Resource' objects| :x: *[^1]* |
| actualEffortMix | Equivalent to the field 'Actual Effort (mix)' in sciforma's 'Resource' objects| :x: *[^1]* |
| actualCostMix | Equivalent to the field 'Actual Cost (mix)' in sciforma's 'Resource' objects| :x: *[^1]* |
| totalEffortMix | Equivalent to the field 'Total Effort (mix)' in sciforma's 'Resource' objects| :x: *[^1]* |
| totalCostMix | Equivalent to the field 'Total Cost (mix)' in sciforma's 'Resource' objects| :x: *[^1]* |
| requestedEffort | Equivalent to the field 'Requested Effort' in sciforma's 'Resource' objects| :x: *[^1]* |

> Note: In general, the user must know what are the resource definition. Check [definitions](definitions.md)

Sample request

```json
{
    "object": {
        "id": "JDOW1",
        "organization": "ABC Corporation.Non-Union",
        "writable": "No",
        "number": 104,
        "rBS": "A.Code2000",
        "firstName": "John",
        "middleName": "",
        "lastName": "Doe",
        "name": "Doe, John",
        "cost": [
            {
                "startDate": "1969-12-31 04:00:00",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 150
            },
            {
                "startDate": "+292278994-08-17 00:12:55",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 0
            }
        ],
        "availability": [
            {
                "startDate": "1969-12-31 04:00:00",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 1
            },
            {
                "startDate": "+292278994-08-17 00:12:55",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": 0
            }
        ],
        "calendarStatus": "",
        "organizationHistory": [
            {
                "startDate": "1969-12-31 16:00:00",
                "finishDate": "2019-05-29 01:42:09",
                "value": "ABC Corporation.Non-Union"
            },
            {
                "startDate": "2019-05-29 01:42:09",
                "finishDate": "2019-06-13 17:18:25",
                "value": "ABC Corporation"
            },
            {
                "startDate": "2019-06-13 17:18:25",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": "ABC Corporation.Non-Union"
            }
        ],
        "jobClassification": "Employee.R&D.Product Engineer",
        "skills": [],
        "defaultRate": 1,
        "emailAddress1": "",
        "emailAddress2": "",
        "emailAddress3": "",
        "status": "ACTIVE",
        "timeEntrySet": "None",
        "timeEntryOverrideSet": "None",
        "timeEntryOverrideStart": "1969-12-31 15:59:59",
        "timeEntryOverrideStop": "1969-12-31 15:59:59",
        "availableEffort": [],
        "actualEffort": [],
        "remainingEffort": [],
        "totalEffort": [],
        "actualCost": [],
        "remainingCost": [],
        "totalCost": [],
        "percentageAllocated": [],
        "userRole": "*Administrator",
        "startDate": "2019-04-30 23:00:00",
        "endDate": "2019-05-31 22:59:59",
        "shouldLevel": true,
        "referencedUser": "Doe, John",
        "actualEffortAdjustment": [],
        "totalCommitmentEffort": [],
        "submittedCommitmentEffort": [],
        "pendingOrganization": "",
        "mappedPendingOrganization": "",
        "pendingAvailableEffort": [],
        "internalID": 995019,
        "totalCommitmentRate": [],
        "submittedCommitmentRate": [],
        "calendarFeeds": [],
        "expectedEffort": 0,
        "permissions": "*System Default",
        "isUser": true,
        "remainingEffortMix": [],
        "remainingCostMix": [],
        "actualEffortMix": [],
        "actualCostMix": [],
        "totalEffortMix": [],
        "totalCostMix": [],
        "requestedEffort": 0,
        "resourceText": "",
        "menu": "",
        "expenseCalculationMethod": "Per Meal",
        "userPicture": "",
        "costCenter": "TRANSACTIONAL/OPEX"
    }
}
```

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
