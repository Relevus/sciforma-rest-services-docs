# Sciforma REST API

The Sciforma REST API project offers a fast, secure and friendly mechanism for any application to connect to a SciForma environment using REST calls in JSON format.

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/Context%20Model.png?raw=true" />
</p>

- ## Quick overview
1. Choose an [authentication mechanism](#how-does-security-work)
2. Add the security header or parameter to your call
3. Identify the [service](#services) you want to use
4. Send your [request](#generating-your-request) and [process](#processing-your-response) the response

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/quickOverview.gif?raw=true" />
</p>

## Table of contents
- [Authentication](#how-does-security-work)
- [Authorization](#authorization)
- [Generating your request](#generating-your-request)
- [Processing your response](#processing-your-response)
- [Technical documentation](#technical-documentation)
- [Services](#services)
- [Utilities](#utilities)


***

- ## How does security work?


The REST API has three authentication methods available to log in: [Basic Auth](#1-basic-authentication), [Session ID](#2-generate-a-session-id) and [Api key](#3-get-an-api-key)

<br/>

### 1. Basic Authentication
Standard basic authentication scheme where user and password are provided as a header, encoded in base64. Intended for one time use to save or pull.
Each request will cause the login to ocurr, and logout once processed.
Sample below:

```
Authorization: Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ==
```

**But keep in mind**, as we need to know the URL of SciForma, you must send the URL in the user field, adding it with a pipe |

```
Username: MYUSER|https://mysciformaserver.com/sciforma
Password: MYPASS
```

<br/>

### 2. Generate a Session ID
Session ID based parameter, intended for single session use. When requested via the REST Security Service a **SessionID** will be provided, this **SessionID** can be used for future calls, as long as the session is still valid.
It is not intended for extended periods of time, and will only be available based on the timeout set in the Properties file.

```
{
    "sessionId": "14eb4484-95fd-4344-8f5e-a79d30dabb85"
}
```

<br/>

### 3. Get an Api key
API Key based mechanism, that can be used as a Header or Parameter for all requestes. The API Key must be requested via the Security Service.
When requested the login details will be permanently stored in an encrypted format, and invoked only when no previous session is available.

```
{
    "apiKey": "cfVECUL2A1mFQlzJw2unh098BjCyou"
}
```

<br/>

### Authorization
The authorization is used to grant access to the REST service endpoints. The permission table is built by using the fields of the logged in user. The following table indicates how the sciforma fields are related with each type of access.

| Permission | Sciforma Field | Type | Category | HTTP Method Allowed | Endpoint URL |
| --- | --- | --- | --- | --- | :---: |
| Read System Parameters | System | READ | SYSTEM INFO | GET | - *[^1]* |
| Read Projects | Projects | READ | PROJECT | GET | /projects/* |
| Write Projects | Write Projects | WRITE | PROJECT | POST, PUT | /projects/* |
| Read Dataviews | Global Data Access | READ | DATAVIEWS | GET | /dataviews/* |
| Write Dataviews | Global Data Access | WRITE | DATAVIEWS | POST, PUT | /dataviews/* |
| Read Resources | Resources | READ | RESOURCE | GET | /resources/* |
| Write Resources | Write Resources | WRITE | RESOURCE | POST, PUT | /resources/* |
| Read Tasks | Write Tasks | READ | TASK | GET | /projects/{projectId}/tasks/* |
| Write Tasks | Write Tasks | WRITE | TASK | POST, PUT | /projects/{projectId}/tasks/* |
| Read Timesheets | Write Timesheets and Resource Calenders | READ | TIMESHEET | GET | /resources/{resourceId}/timesheets |
| Write Timesheets | Write Timesheets and Resource Calenders | WRITE | TIMESHEET | POST, PUT | /resources/{resourceId}/timesheets |
| Read Users | Users | READ | USER | GET | /users/* |
| Write Users | Write Users | WRITE | USER | POST, PUT | /users/* |

*[^1]: System doesn't have an endpoint, it's a permission used to verify whether or not an user can read the system information like the field definitions.

<br/>

- ## Generating your request
All request requires a security header or parameter (Excluding Security endpoints). Samples below:

**Headers**:

At least one of this must be provided in order to authenticate with any of the 3 supported methods.

| Key | Value | Description |
| --- | --- | --- | 
| authorization | Basic QWxhZGRpbjpvcGVuIHNlc2FtZQ== | It is required if you want to use basic authentication |
| sessionID | 14eb4484-95fd-4344-8f5e-a79d30dabb85 | It is required if you want to use authentication based on SessionID |
| apiKey | cfVECUL2A1mFQlzJw2unh098BjCyou | It is required if you want to use ApiKey-based authentication | 


**Query parameters**: 
The following parameters only apply for **GET** requests:

| Code | Description | Required |
| --- | --- | :---: |
| maxResults | Limit of records when filters are not used. The default value is 200. | :x: |
| filters | Filters applied to obtain records ([Filters](filter.md)) | :x: | 
| fields | List of attributes separated by commas. If not sent, all available attributes are obtained | :x: |
| expand | Indicates if the child attributes that are objects, must be shown with their internal properties | :x: |
| includeDistributed | Indicates if distributed fields must be included in the get response. It's a boolean parameter. The default value is false, meaning that the distributed fields are not shown by default. | :x: |
| includeDistributed | Indicates if distributed fields must be included in the get response. It's a boolean parameter. The default value is false, meaning that the distributed fields are not shown by default. | :x: |
| timeIntervalDistributed | Indicates the distribution used to return the distributed field. The list of valid values are: NONE, HOUR, DAY, WEEK, MONTH, QUARTER, YEAR. The default value is DAY. | :x: |
| includeFormulas | Indicates if formula fields must be included in the get response. It's a boolean parameter. The default value is false, meaning that the formula fields are not shown by default. | :x: |
| apiKey | Value of the api key | :x: *[^1]* |

*[^1]: It is only required if you have not used any security header*

<br/>

**Sending single/multiple records**: 

The data endpoints allows the insertion and modification of one or more records, using POST method. If a record has the ID field, the REST-API will assume it will be modified, otherwise, when the ID is not present, it will be handled as an insert.

***General schema: SINGLE***

```
{
    "object": {
        "id": "JDOW15",
        "organization": "ABC Corporation",
        "firstName": "John 15",
        "middleName": "",
        "lastName": "Doe",
        "name": "Doe, John"
    }
}
```

***General schema: MULTIPLE***

```
{
	"records" : [
		{
			"object": {
				"id": "JDOW7",
				"organization": "ABC Corporation",
				"firstName": "John",
				"middleName": "",
				"lastName": "Doe",
				"name": "Doe, John"
			}
		},
		{
			"object": {
				"organization": "ABC Corporation",
				"firstName": "Max",
				"middleName": "",
				"lastName": "Powell",
				"name": "Powell, Max"
			}
		}
	]
}
```
*The first record will be an update, the second record will be an insert*

<br/>

- ## Processing your response

**Response codes**:
The following response codes are common to all requests:

| Code | Description |
| --- | --- |
| 200 | OK |
| 400 | No API key parameter or token header present in your request. Please check your data. |

<br/>

- ## Technical documentation
Please check each of the utilities classes that the project contains before adding your code lines.
  - [Product architecture](contrib/architecture.md)
  - [Customizing object definitions](contrib/custom_definitions.md)
  - [Configuration parameters](contrib/prop_configuration.md)
  - [API Documentation](sciforma-bom/doc/javadoc.zip?raw=true)
  - [How to configure the development environment](contrib/dev_environment.md)
  - [Server installation](contrib/server_installation.md)
  - [Wrapper service](contrib/wrapper_service.md)
 
<br/> 

- ## Services
  - [x] [Security and Login](security.md)
  - [x] [Dataviews](dataviews.md)
  - [x] [Dataviews V2](dataviewsV2.md)
  - [x] [Definitions](definitions.md)
  - [x] [Organizations](organizations.md)
  - [x] [Projects](projects.md)
  - [x] [Resources](resources.md)
  - [x] [Resource Assignments](resource_assignments.md)
  - [x] [Tasks](tasks.md)
  - [x] [Timesheets](timesheets.md)
  - [x] [Calendar](calendar.md)
  - [x] [Users](users.md)
  - [x] [Transactions](transactions.md)

<br/>

 
- ## Utilities

A sample postman collection containing all requests is available. To use follow the following steps:
   1. Download [POSTMAN collection](RestAPI_Sciforma.postman_collection.json) (Select 'Raw' option -> Save as...)
   
   2. In Postman App, Go to File -> Import...
   
   3. Select the collection 'RestAPI_Sciforma' -> Edit
   
   4. Go to the 'Variables' tab and modify them with the values of the URLs of your Sciforma-API environment (security_url and url). Then, set the value for 'sciforma_version' according to the Sciforma version you want to connect.

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/Postman%20VARs.PNG?raw=true" width="650" />
</p>
   
   5. Open the 'Generate Api key' request, go to 'Body' tab and then enter the authentication credentials and Sciforma URL. After you submit the request and the values are verified, you will receive the apikey code.
   
   6. Replace the apiKey code in the Postman collection Variables.
   
<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/update_apiKey_in_variables.png?raw=true" width="650" />
</p>
   
   7. Test if the configuration is valid sending the request 'Get related api keys'. By default, it uses the apiKey variable. You can modify it by any valid apiKey code.

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/get_related_api_keys.png?raw=true" width="650" />
</p>

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/get_related_api_keys_custom.png?raw=true" width="650" />
</p>
   
  
<br/>
