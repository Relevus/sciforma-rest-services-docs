# Organizations Endpoint
Relative URL: */v1/organizations*

## Available services
  - [Get Organizations](#get-organizations)
  - [Get one Organization record](#get-one-organization-record)
  - [Save Organizations](#save-organizations)
  
---
- ### GET Organizations

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of Organization records

**Headers**: 

| Key | Values | Description | Default value |
| --- | --- | --- | --- | 
| Organization-Key | code / name | Defines the unique key used to identify records | name |

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
    "numberOfRecords": 50,
    "records": [
        {
            "object": {
                "name": "Entire Organization",
                "description": "Entire Organization",
                "organizationCode": "A",
                "timesheetLockDate": "1969-12-31 18:59:59",
                "manager1": "",
                "manager2": "",
                "manager3": "Douglas, Michael",
                "pendingOrganization": "",
                "permissions": "*System Default",
                "parent": "",
                "next": "",
                "previous": "",
                "internalID": 1,
                "requestedEffort": 0,
                "costCenter": "",
                "fullName": "Entire Organization"
            }
        },
        {
            "object": {
                "name": "BUSINESS DEVELOPMENT VP HO",
                "description": "",
                "organizationCode": "BDC",
                "timesheetLockDate": "1969-12-31 18:59:59",
                "manager1": "",
                "manager2": "",
                "manager3": "Heckler, Mark",
                "pendingOrganization": "",
                "permissions": "*System Default",
                "parent": "Entire Organization",
                "next": "Entire Organization.MARKETING GM HO",
                "previous": "",
                "internalID": 102413,
                "requestedEffort": 0,
                "costCenter": "",
                "fullName": "Entire Organization.BUSINESS DEVELOPMENT VP HO"
            }
        }
    ]
}
```
<br/>

---
- ### GET ONE ORGANIZATION RECORD

**Method**: GET

**Path**: */{organizationName}*

**Description**: Action to obtain one organization record	

**Headers**: 

| Key | Values | Description | Default value |
| --- | --- | --- | --- | 
| Organization-Key | code / name | Defines the unique key used to identify records | name |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| organizationName | Full organization name | :white_check_mark: |

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
        "name": "2083381-PDC COST ADMIN",
        "description": "",
        "organizationCode": "3413381",
        "timesheetLockDate": "1969-12-31 18:59:59",
        "manager1": "",
        "manager2": "",
        "manager3": "",
        "pendingOrganization": "",
        "permissions": "*System Default",
        "parent": "Company.CUSTOMER SOLUTIONS & SUPPORT",
        "next": "Company.CUSTOMER SOLUTIONS & SUPPORT.2087036-WARRANTY ADMIN",
        "previous": "",
        "internalID": 13783,
        "requestedEffort": 0,
        "costCenter": ""
    }
}
```
<br/>

---

- ### SAVE ORGANIZATIONS

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single organization record or a list of organization records

**Headers**:

| Key | Value | Description | Default value | Required |
| --- | --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | | :white_check_mark: |
| Organization-Key | code / name | Defines the unique key used to identify records | name | :x: |


> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

| Code | Description | Required |
| --- | --- | :---: |
| name | It must be a full organization name | :x: *[^1]* |
| description | Equivalent to the field 'Description' in sciforma's 'Organizations' objects| :x: *[^1]* |
| cost | Equivalent to the field 'Cost' in sciforma's 'Organizations' objects| :x: *[^1]* |
| organizationCode | Equivalent to the field 'Organization Code' in sciforma's 'Organizations' objects| :x: *[^1]* |
| timesheetLockDate | Equivalent to the field 'Timesheet lock date' in sciforma's 'Organizations' objects| :x: *[^1]* |
| manager1 | Sciforma's manager full name | :x: *[^1]* |
| manager2 | Sciforma's manager full name | :x: *[^1]* |
| manager3 | Sciforma's manager full name | :x: *[^1]* |
| pendingOrganization | Equivalent to the field 'Pending Organization' in sciforma's 'Organizations' objects| :x: *[^1]* |
| permissions | Equivalent to the field 'Permissions' in sciforma's 'Organizations' objects| :x: *[^1]* |
| internalID | Equivalent to the field 'Internal ID' in sciforma's 'Organizations' objects| :x: *[^1]* |
| requestedEffort | Equivalent to the field 'Request Effort' in sciforma's 'Organizations' objects| :x: *[^1]* |
| lastQualifiedName | Equivalent to the field 'Last Qualified Name' in sciforma's 'Organizations' objects| :x: *[^1]* |
| costCenter | Cost Center associated to Organization | :x: *[^1]* |

> Note: In general, the user must know what are the organization definition. Check [definitions](definitions.md)

Sample request

```json
{
    "object": {
        "name": "Managed and Support Services.Test01 from REST-API.Child 01",
        "manager1": "Soler, Carlos"
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
            "validationMessages": []
        }
    ]
}
```
