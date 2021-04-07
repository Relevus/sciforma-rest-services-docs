# Users Endpoint
Relative URL: */v1/users*

## Available services
  - [Get users](#get-users)
  - [Get one user record](#get-one-user-record)
  - [Save users](#save-users)
  
---
- ### GET USERS

**Method**: GET

**Path**: */*

**Description**: Action to obtain a list of records from a type of user

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
                "organization": "ABC Corporation.IT.Development",
                "name": "Wood, Nicole",
                "id": "NWOOD",
                "resources": true,
                "projectControl": true,
                "projects": true,
                "costItems": true,
                "approvals": true,
                "myWork": true,
                "documents": true,
                "issues": true,
                "forms": true,
                "staticReports": true,
                "formDesign": true,
                "system": true,
                "users": true,
                "reorganization": true,
                "globalDataAccess": true,
                "portfolioControl": true,
                "rAM": true,
                "writeDocuments": true,
                "writeResources": true,
                "writeResourceCommitments": true,
                "writeResourceCalendars": true,
                "writeCostItems": true,
                "writeProjects": true,
                "writeTasks": true,
                "writePortfolioFolders": true,
                "writeTimesheetsandResourceCalenders": true,
                "writeOrganizations": true,
                "writeJobClasses": true,
                "writeSkills": true,
                "writeConfigurationData": true,
                "writeFormDefinitions": true,
                "writeUsers": true,
                "mappedPendingOrganization": "",
                "internalID": 757899,
                "isResource": true,
                "loginID": "nwood",
                "firstName": "Nicole",
                "middleName": "",
                "lastName": "Wood",
                "organizationHistory": [
                    {
                        "startDate": "2018-01-08 02:40:53",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": "ABC Corporation.IT.Development"
                    }
                ],
                "emailAddress1": "",
                "emailAddress2": "",
                "emailAddress3": "",
                "invalidLogins": 0,
                "loginLockout": false,
                "picture": "/tmp/tomcat8-tomcat8-tmp/sci3556019521429177868.png",
                "passwordNeverExpires": false,
                "userRole": "*Project Manager (WP)",
                "writeIssues": false,
                "pendingOrganization": " ",
                "corporatePreferenceSet": "",
                "tokensUsed": 27,
                "permissions": "*System Default",
                "userText": "",
                "menu": ""
            }
        },
        {
            "object": {
                "organization": "ABC Corporation",
                "name": "Administrator",
                "id": "ADMIN",
                "resources": true,
                "projectControl": true,
                "projects": true,
                "costItems": true,
                "approvals": true,
                "myWork": true,
                "documents": true,
                "issues": true,
                "forms": true,
                "staticReports": false,
                "formDesign": true,
                "system": true,
                "users": true,
                "reorganization": true,
                "globalDataAccess": true,
                "portfolioControl": false,
                "rAM": false,
                "writeDocuments": true,
                "writeResources": true,
                "writeResourceCommitments": false,
                "writeResourceCalendars": true,
                "writeCostItems": true,
                "writeProjects": true,
                "writeTasks": true,
                "writePortfolioFolders": true,
                "writeTimesheetsandResourceCalenders": true,
                "writeOrganizations": true,
                "writeJobClasses": true,
                "writeSkills": true,
                "writeConfigurationData": true,
                "writeFormDefinitions": true,
                "writeUsers": true,
                "mappedPendingOrganization": "",
                "internalID": 2,
                "isResource": true,
                "loginID": "psnextadmin",
                "firstName": "",
                "middleName": "",
                "lastName": "Administrator",
                "organizationHistory": [
                    {
                        "startDate": "2019-04-10 10:14:08",
                        "finishDate": "+292278994-08-17 00:12:55",
                        "value": "ABC Corporation"
                    }
                ],
                "emailAddress1": "",
                "emailAddress2": "",
                "emailAddress3": "",
                "invalidLogins": 0,
                "loginLockout": false,
                "picture": "/tmp/tomcat8-tomcat8-tmp/sci5008824816169313459.png",
                "passwordNeverExpires": false,
                "userRole": "Super User",
                "writeIssues": true,
                "pendingOrganization": " ",
                "corporatePreferenceSet": "",
                "tokensUsed": 27,
                "permissions": "*System Default",
                "userText": "",
                "menu": ""
            }
        }
    ],
    "numberOfRecords": 2
}
```
<br/>

---
- ### GET ONE USER RECORD

**Method**: GET

**Path**: */{userId}*

**Description**: Action to obtain one user record	

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| userId | User identifier | :white_check_mark: |

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
        "organization": "ABC Corporation",
        "name": "Administrator",
        "id": "ADMIN",
        "resources": true,
        "projectControl": true,
        "projects": true,
        "costItems": true,
        "approvals": true,
        "myWork": true,
        "documents": true,
        "issues": true,
        "forms": true,
        "staticReports": false,
        "formDesign": true,
        "system": true,
        "users": true,
        "reorganization": true,
        "globalDataAccess": true,
        "portfolioControl": false,
        "rAM": false,
        "writeDocuments": true,
        "writeResources": true,
        "writeResourceCommitments": false,
        "writeResourceCalendars": true,
        "writeCostItems": true,
        "writeProjects": true,
        "writeTasks": true,
        "writePortfolioFolders": true,
        "writeTimesheetsandResourceCalenders": true,
        "writeOrganizations": true,
        "writeJobClasses": true,
        "writeSkills": true,
        "writeConfigurationData": true,
        "writeFormDefinitions": true,
        "writeUsers": true,
        "mappedPendingOrganization": "",
        "internalID": 2,
        "isResource": true,
        "loginID": "psnextadmin",
        "firstName": "",
        "middleName": "",
        "lastName": "Administrator",
        "organizationHistory": [
            {
                "startDate": "2019-04-10 10:14:08",
                "finishDate": "+292278994-08-17 00:12:55",
                "value": "ABC Corporation"
            }
        ],
        "emailAddress1": "",
        "emailAddress2": "",
        "emailAddress3": "",
        "invalidLogins": 0,
        "loginLockout": false,
        "picture": "/tmp/tomcat8-tomcat8-tmp/sci5008824816169313459.png",
        "passwordNeverExpires": false,
        "userRole": "Super User",
        "writeIssues": true,
        "pendingOrganization": " ",
        "corporatePreferenceSet": "",
        "tokensUsed": 27,
        "permissions": "*System Default",
        "userText": "",
        "menu": ""
    }
}
```
<br/>

---

- ### SAVE USERS

**Method**: POST

**Path**: */*

**Description**: Action to add or modify the values of a single user record or a list of user records

**Headers**:

| Key | Value | Description | Required |
| --- | --- | --- | :---: |
| Content-Type | application/json | Defines the content format | :white_check_mark: |

> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

| Code | Description | Required |
| --- | --- | :---: |
| organization | Equivalent to the field 'Organization' in sciforma's 'User' objects| :x: *[^1]* |
| name | Equivalent to the field 'Name' in sciforma's 'User' objects| :x: *[^1]* |
| id | Equivalent to the field 'ID' in sciforma's 'User' objects| :x: *[^1]* |
| resources | Equivalent to the field 'Resources' in sciforma's 'User' objects| :x: *[^1]* |
| projectControl | Equivalent to the field 'Project Control' in sciforma's 'User' objects| :x: *[^1]* |
| projects | Equivalent to the field 'Projects' in sciforma's 'User' objects| :x: *[^1]* |
| costItems | Equivalent to the field 'Cost Items' in sciforma's 'User' objects| :x: *[^1]* |
| approvals | Equivalent to the field 'Approvals' in sciforma's 'User' objects| :x: *[^1]* |
| myWork | Equivalent to the field 'My Work' in sciforma's 'User' objects| :x: *[^1]* |
| documents | Equivalent to the field 'Documents' in sciforma's 'User' objects| :x: *[^1]* |
| issues | Equivalent to the field 'Issues' in sciforma's 'User' objects| :x: *[^1]* |
| forms | Equivalent to the field 'Forms' in sciforma's 'User' objects| :x: *[^1]* |
| staticReports | Equivalent to the field 'Static Reports' in sciforma's 'User' objects| :x: *[^1]* |
| formDesign | Equivalent to the field 'Form Design' in sciforma's 'User' objects| :x: *[^1]* |
| system | Equivalent to the field 'System' in sciforma's 'User' objects| :x: *[^1]* |
| users | Equivalent to the field 'Users' in sciforma's 'User' objects| :x: *[^1]* |
| reorganization | Equivalent to the field 'Reorganization' in sciforma's 'User' objects| :x: *[^1]* |
| globalDataAccess | Equivalent to the field 'Global Data Access' in sciforma's 'User' objects| :x: *[^1]* |
| portfolioControl | Equivalent to the field 'Portfolio Control' in sciforma's 'User' objects| :x: *[^1]* |
| rAM | Equivalent to the field 'RAM' in sciforma's 'User' objects| :x: *[^1]* |
| writeDocuments | Equivalent to the field 'Write Documents' in sciforma's 'User' objects| :x: *[^1]* |
| writeResources | Equivalent to the field 'Write Resources' in sciforma's 'User' objects| :x: *[^1]* |
| writeResourceCommitments | Equivalent to the field 'Write Resource Commitments' in sciforma's 'User' objects| :x: *[^1]* |
| writeResourceCalendars | Equivalent to the field 'Write Resource Calendars' in sciforma's 'User' objects| :x: *[^1]* |
| writeCostItems | Equivalent to the field 'Write Cost Items' in sciforma's 'User' objects| :x: *[^1]* |
| writeProjects | Equivalent to the field 'Write Projects' in sciforma's 'User' objects| :x: *[^1]* |
| writeTasks | Equivalent to the field 'Write Tasks' in sciforma's 'User' objects| :x: *[^1]* |
| writePortfolioFolders | Equivalent to the field 'Write Portfolio Folders' in sciforma's 'User' objects| :x: *[^1]* |
| writeTimesheetsandResourceCalenders | Equivalent to the field 'Write Timesheets and Resource Calenders' in sciforma's 'User' objects| :x: *[^1]* |
| writeOrganizations | Equivalent to the field 'Write Organizations' in sciforma's 'User' objects| :x: *[^1]* |
| writeJobClasses | Equivalent to the field 'Write Job Classes' in sciforma's 'User' objects| :x: *[^1]* |
| writeSkills | Equivalent to the field 'Write Skills' in sciforma's 'User' objects| :x: *[^1]* |
| writeConfigurationData | Equivalent to the field 'Write Configuration Data' in sciforma's 'User' objects| :x: *[^1]* |
| writeFormDefinitions | Equivalent to the field 'Write Form Definitions' in sciforma's 'User' objects| :x: *[^1]* |
| writeUsers | Equivalent to the field 'Write Users' in sciforma's 'User' objects| :x: *[^1]* |
| mappedPendingOrganization | Equivalent to the field 'Mapped Pending Organization' in sciforma's 'User' objects| :x: *[^1]* |
| internalID | Equivalent to the field 'Internal ID' in sciforma's 'User' objects| :x: *[^1]* |
| isResource | Equivalent to the field 'Is Resource' in sciforma's 'User' objects| :x: *[^1]* |
| loginID | Equivalent to the field 'Login ID' in sciforma's 'User' objects| :x: *[^1]* |
| firstName | Equivalent to the field 'First Name' in sciforma's 'User' objects| :x: *[^1]* |
| middleName | Equivalent to the field 'Middle Name' in sciforma's 'User' objects| :x: *[^1]* |
| lastName | Equivalent to the field 'Last Name' in sciforma's 'User' objects| :x: *[^1]* |
| organizationHistory | Equivalent to the field 'Organization History' in sciforma's 'User' objects| :x: *[^1]* |
| emailAddress1 | Equivalent to the field 'Email Address 1' in sciforma's 'User' objects| :x: *[^1]* |
| emailAddress2 | Equivalent to the field 'Email Address 2' in sciforma's 'User' objects| :x: *[^1]* |
| emailAddress3 | Equivalent to the field 'Email Address 3' in sciforma's 'User' objects| :x: *[^1]* |
| invalidLogins | Equivalent to the field 'Invalid Logins' in sciforma's 'User' objects| :x: *[^1]* |
| loginLockout | Equivalent to the field 'Login Lockout' in sciforma's 'User' objects| :x: *[^1]* |
| picture | Equivalent to the field 'Picture' in sciforma's 'User' objects| :x: *[^1]* |
| passwordNeverExpires | Equivalent to the field 'Password Never Expires' in sciforma's 'User' objects| :x: *[^1]* |
| userRole | Equivalent to the field 'User Role' in sciforma's 'User' objects| :x: *[^1]* |
| writeIssues | Equivalent to the field 'Write Issues' in sciforma's 'User' objects| :x: *[^1]* |
| pendingOrganization | Equivalent to the field 'Pending Organization' in sciforma's 'User' objects| :x: *[^1]* |
| corporatePreferenceSet | Equivalent to the field 'Corporate Preference Set' in sciforma's 'User' objects| :x: *[^1]* |
| tokensUsed | Equivalent to the field 'Tokens Used' in sciforma's 'User' objects| :x: *[^1]* |
| permissions | Equivalent to the field 'Permissions' in sciforma's 'User' objects| :x: *[^1]* |

> Note: In general, the user must know what are the user definition. Check [definitions](definitions.md)

Sample request

```json
{
    "object": {
        "firstName": "Test",
        "id": "TEST31",
        "lastName": "Test",
        "loginID": "test31",
        "menu": "",
        "middleName": "",
        "name": "Test",
        "organization": "ABC Corporation"
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
