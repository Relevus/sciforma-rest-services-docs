# :clock5: Timesheets Endpoint
Relative URL: */v1/resources/**{resourceId}**/timesheets*

## Available services
  - [Get time entries](#get-time-entries)
  - [Save time entries](#save-time-entries)
  
---
- ### GET TIME ENTRIES

**Method**: GET

**Path**: */*

**Description**: Action to obtain the values and notes of the time entries of a resource	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| resourceId | Resource identifier | :white_check_mark: |

**Query parameters**: 
The following parameters only apply for **GET** requests:

| Code | Description | Required |
| --- | --- | :---: |
| timeIntervalDistributed | Indicates the distribution used to return the actual effort. The list of valid values are: NONE, HOUR, DAY, WEEK, MONTH, QUARTER, YEAR. The default value is NONE. | :x: |

> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**:

| Code | Description | Data type |
| --- | --- | :---: |
| referenceDate | Indicates a reference date to obtain the entries in the time sheets. The REST API searches for the range from Monday to Sunday that contains that date. | Date in format yyyy-MM-dd |
| fromDate | Indicates the initial date for the search of time entries. It requires 'toDate' filter. | Date in format yyyy-MM-dd |
| toDate | Indicates the final date for the search of time entries. It requires 'fromDate' filter. | Date in format yyyy-MM-dd |
| projectID | Unique identifier of the project. OPTIONAL. | String |

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
                "actualEffort": [
                    {
                        "startDate": "2019-05-13 00:00:00",
                        "finishDate": "2019-05-14 00:00:00",
                        "value": 8,
                        "notes": "Monday 13"
                    },
                    {
                        "startDate": "2019-05-14 00:00:00",
                        "finishDate": "2019-05-15 00:00:00",
                        "value": 7,
                        "notes": "Thursday 14"
                    }
                ],
                "lastUpdate": "2019-06-21 16:30:28",
                "completedDate": "2019-05-25 00:00:00",
                "name": "Tarea 03",
                "id": "JX6JJX1S",
                "start": "2019-05-13 10:00:00",
                "finish": "2019-07-05 19:00:00",
                "projectName": "AA JAHR PRJ 02",
                "projectID": "JAHRPRJ01",
                "workPackageName": "",
                "workPackageID": "",
                "workPackageTaskID": "JX6JJX1S",
                "description": "",
                "resource": "Administrator",
                "resourceOrganization": "Entire Organization",
                "projectIID": 1162460,
                "resourceIID": 2,
                "taskIID": 1162473
            }
        },
        {
            "object": {
                "actualEffort": [
                    {
                        "startDate": "2019-05-13 00:00:00",
                        "finishDate": "2019-05-14 00:00:00",
                        "value": 0,
                        "notes": ""
                    },
                    {
                        "startDate": "2019-05-14 00:00:00",
                        "finishDate": "2019-05-15 00:00:00",
                        "value": 0,
                        "notes": ""
                    }
                ],
                "lastUpdate": "2019-06-10 05:56:08",
                "actualStart": "2018-07-23 08:00:00",
                "completedDate": "2019-06-06 00:00:00",
                "name": "Build",
                "id": "J4O7L3GS",
                "start": "2018-07-23 08:00:00",
                "finish": "2019-06-05 17:00:00",
                "projectName": "Agile",
                "projectID": "J4O8XMCQ",
                "workPackageName": "",
                "workPackageID": "",
                "workPackageTaskID": "J4O7L3GS",
                "description": "",
                "resource": "Administrator",
                "resourceOrganization": "Entire Organization",
                "projectIID": 6142,
                "resourceIID": 2,
                "taskIID": 6147
            }
        }
    ],
    "numberOfRecords": 2
}
```
<br/>

---

- ### SAVE TIME ENTRIES

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values and notes in the time entries. Daily distribution is the **only one supported**.	

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| resourceId | Resource identifier | :white_check_mark: |

**Query parameters**: NONE

**Request body**:

| Attribute | Description | Required |
| --- | --- | :---: |
| actualEffort | List of time entries with their start and end date, value and notes | :white_check_mark: |
| id | TimeSheet assigment ID | :x: *[^1]* |
| workPackageTaskID | Alphanumeric Task ID | :x: *[^1]* |
| taskIID | Numeric Task ID | :x: *[^1]* |

*[^1]: Some of these is required to identify the timesheet assignment.*

Sample request

```json
{
	"records": [
		{
			"object": {
				"actualEffort": [
					{
						"startDate": "2019-05-13 00:00:00",
						"finishDate": "2019-05-14 00:00:00",
						"value": 8,
						"notes": "Monday 13"
					},
					{
						"startDate": "2019-05-14 00:00:00",
						"finishDate": "2019-05-15 00:00:00",
						"value": 7,
						"notes": "Tuesday 14"
					},
					{
						"startDate": "2019-05-15 00:00:00",
						"finishDate": "2019-05-16 00:00:00",
						"value": 6,
						"notes": "Wednesday 15"
					}
				],
				"workPackageTaskID": "JX6JJX1S"
			}
		}
	]
}
```
> The properties "finishDate" and "notes" are optional. If you do not send "finishDate", the system will calculate it using the "startDate".

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
