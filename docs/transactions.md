# Transactions Endpoint
Relative URL: */v1/projects/**{projectId}**/transactions

> Note: With the REST-API you can get and push data from projects in **WORKING** or **PUBLISHED** state. Use the __Project-Version__ request header to indicate the version you want to get.

## Available services
  - [Get transactions](#get-transactions)
  - [Get one transaction record](#get-one-transaction-record)
  - [Save transactions](#save-transactions)
  
---
- ### GET TRANSACTIONS

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of records from a type of project

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
    "numberOfRecords": 4,
    "records": [
        {
            "object": {
                "id": "KHV4IBLJ",
                "name": "Transaction test04",
                "type": "Other",
                "actualCost": [],
                "distributedAmount": [
                    {
                        "startDate": "2020-10-20 00:00:00",
                        "finishDate": "2020-10-21 00:00:00",
                        "value": 30
                    },
                    {
                        "startDate": "2020-10-21 00:00:00",
                        "finishDate": "2020-10-22 00:00:00",
                        "value": 30.999999999999996
                    }
                ],
                "distributedAmountMode": true,
                "costCenter": "Land"
            }
        },
        {
            "object": {
                "id": "KHV4IBLL",
                "name": "Building",
                "type": "",
                "actualCost": [],
                "distributedAmount": [],
                "distributedAmountMode": true,
                "costCenter": "Building"
            }
        },
        {
            "object": {
                "id": "KHV4IBLM",
                "name": "Other Project",
                "type": "",
                "actualCost": [],
                "distributedAmount": [],
                "distributedAmountMode": true,
                "costCenter": "Other Project"
            }
        },
        {
            "object": {
                "id": "KHV4IBLN",
                "name": "Vehicles",
                "type": "",
                "actualCost": [],
                "distributedAmount": [],
                "distributedAmountMode": false,
                "costCenter": "Vehicles"
            }
        },
        {
            "object": {
                "id": "KHV4IBLO",
                "name": "IT",
                "type": "",
                "actualCost": [],
                "distributedAmount": [],
                "distributedAmountMode": true,
                "costCenter": "IT"
            }
        }
    ]
}
```
<br/>

---
- ### GET ONE TRANSACTION RECORD

**Method**: GET

**Path**: */{projectId}*
> Note: If you need to get/edit the **Non project** created in Sciforma, use as projectId = _non-project_

**Description**: Action to obtain one project record	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| projectId | Project identifier | :heavy_check_mark: |

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
        "id": "KHV4IBLJ",
        "name": "Transaction test04",
        "type": "Other",
        "comment": "Description for Transaction test04 - From REST-API",
        "amount": [],
        "status": "Forecast",
        "billable": false
    }
}
```
<br/>

---

- ### SAVE TRANSACTIONS

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single transaction record or a list of transaction records

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :heavy_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

| Code | Description | Required |
| --- | --- | :---: |
| id | Equivalent to the field 'ID' in sciforma's 'Transaction' objects. | :heavy_check_mark: *[^1]* |


> Note: In general, the user must know what are the project definition. Check [definitions](definitions.md)

Sample request

```json
{
    "records": [
        {
            "object": {
                "name": "Transaction test04",
                "type": "Other",
                "id": "KHV4IBLJ",
                "actualCost": [],
                "distributedAmount": [
                    {
                        "startDate": "2020-10-20 00:00:00",
                        "finishDate": "2020-10-21 00:00:00",
                        "value": 30
                    },
                    {
                        "startDate": "2020-10-21 00:00:00",
                        "finishDate": "2020-10-22 00:00:00",
                        "value": 31
                    }
                ],
                "distributedAmountMode": true,
                "costCenter": "Land"
            }
        },
        {
            "object": {
                "name": "Building",
                "type": "",
                "id": "KHV4IBLL",
                "distributedAmountMode": true,
                "costCenter": "Building"
            }
        },
        {
            "object": {
                "name": "Other Project",
                "type": "",
                "id": "KHV4IBLM",
                "distributedAmountMode": true,
                "costCenter": "Other Project"
            }
        },
        {
            "object": {
                "name": "Vehicles",
                "type": "",
                "id": "KHV4IBLN",
                "distributedAmountMode": false,
                "costCenter": "Vehicles"
            }
        },
        {
            "object": {
                "name": "IT",
                "type": "",
                "id": "KHV4IBLO",
                "distributedAmountMode": true,
                "costCenter": "IT"
            }
        }
    ]
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
            "validationMessages": []
        }
    ]
}
```
