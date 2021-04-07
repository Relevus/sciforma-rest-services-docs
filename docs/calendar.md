# :calendar: Resource Calendar Endpoint
Relative URL: */v1/resources/**{resourceId}**/calendar/**{pending|active}***

## Available services
  - [Get special days](#get-special-days)
  - [Get default days](#get-time-entries)
  - [Save special days](#save-special-days)
  
---
- ### GET SPECIAL DAYS

**Method**: GET

**Path**: */specialDays*

**Description**: Action to obtain the configuration of special days in the resource calendar	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| resourceId | Resource identifier | :white_check_mark: |
| Calendar type | PENDING or ACTIVE | :white_check_mark: |

**Query parameters**: NONE
> Note: Check the common query parameters for [requests](README.md#generating-your-request)

**Allowed filters**:

| Code | Description | Data type |
| --- | --- | :---: |
| fromDate | Indicates the initial date for the search of special days. It requires 'toDate' filter. | Date in format yyyy-MM-dd |
| toDate | Indicates the final date for the search of special days entries. It requires 'fromDate' filter. | Date in format yyyy-MM-dd |

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
  "numberOfRecords": 5,
  "records": [
    {
      "date": "2020-04-06",
      "nonWorkPeriods": [
        {
          "startTime": "13:00",
          "finishTime": "17:00",
          "type": "Paid Time Off"
        }
      ]
    },
    {
      "date": "2020-04-08",
      "nonWorkPeriods": [
        {
          "startTime": "13:00",
          "finishTime": "17:00",
          "type": "Paid Time Off"
        }
      ]
    },
    {
      "date": "2020-05-05",
      "nonWorkPeriods": [
        {
          "startTime": "09:00",
          "finishTime": "13:00",
          "type": "Paid Time Off"
        }
      ]
    },
    {
      "date": "2020-05-06",
      "nonWorkPeriods": [
        {
          "startTime": "13:00",
          "finishTime": "17:00",
          "type": "Paid Time Off"
        }
      ]
    },
    {
      "date": "2020-05-08",
      "nonWorkPeriods": [
        {
          "startTime": "13:00",
          "finishTime": "17:00",
          "type": "Paid Time Off"
        }
      ]
    }
  ]
}
```
<br/>

---

- ### SAVE SPECIAL DAYS

**Method**: POST

**Path**: */specialDays*

**Description**: Action to add or modify the special days configuration for a resource

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| resourceId | Resource identifier | :white_check_mark: |
| Calendar type | PENDING or ACTIVE | :white_check_mark: |

**Query parameters**: NONE

**Request body**:

| Attribute | Description | Required |
| --- | --- | :---: |
| date | Date of the special day | :white_check_mark: |
| Type of period | workPeriods or nonWorkPeriods. Configuration list with hours for the work type. When no time is specified, it is assumed to be all day. | :x: |
| type | It only apply for when is time off. It indicates the reason. |  |


Sample request

```json
{
  "records": [
    {
      "object" : {
	      "date": "2020-05-06",
	      "workPeriods": [
	        {
	          "startTime": "7:0",
	          "finishTime": "10:0"
	        },
	        {
	          "startTime": "14:0",
	          "finishTime": "16:0"
	        }
	      ]
      }
    },
    {
      "object" : {
	      "date": "2020-05-19",
	      "nonWorkPeriods": [
	        {
	          "startTime": "8:0",
	          "finishTime": "12:0",
	          "type": "Paid Time Off"
	        },
	        {
	          "startTime": "13:0",
	          "finishTime": "17:0",
	          "type": "Paid Time Off"
	        }
	      ]
      }
    },
    {
    	"object" : {
	      "date": "2020-05-21",
	      "nonWorkPeriods": [
	        {
	          "type": "Jury Duty"
	        }
	      ]
    	}
    }
  ]
}
```
> The properties "startTime" and "finishTime" are optional. If you do not send them, the system will calculate the time as 00:00 and 23:59.

**Response codes**:

| Code | Description |
| --- | --- |
| 400 | There is a problem parsing the json content, check your json payload |

> Note: Check the common codes in [responses](README.md#processing-your-response)

**Sample response**:

```json
{
  "successfulCount": 1,
  "failureCount": 0,
  "records": [
    {
      "id": "ADMIN",
      "status": "VALIDATION_SUCCESS",
      "isNew": true,
      "validationMessages": []
    }
  ]
}
```
