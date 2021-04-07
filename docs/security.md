# :lock: Security Endpoint
Relative URL: */sciforma-rest/service/security*

## Available services
  - [Login](#login)  
  - [Logout](#logout)
  - [Generate Api key](#generate-api-key)
  - [Get related Api keys](#get-related-api-keys)
  - [Update Api key](#update-api-key)
  - [Remove Api key](#remove-api-key)

---  

- ### LOGIN

**Method**: POST

**Path**: */login*

**Description**: Action to get the session ID	

**Headers**:

| Key | Value | Required |
| --- | --- | :---: |
| Content-Type | application/json | :white_check_mark: |

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

```json
{
	"username" : "psnextadmin", 
	"password" : "changeit", 
	"url": "https://192.168.42.128/sciforma"
}	
```

**Response codes**:

| Code | Description |
| --- | --- |
| 200 | OK |
| 401 | Something went wrong with your log in request. Check your sciforma credentials |
| 400 | There is a problem parsing the json content, check your json payload. |

**Sample response**:

```json
{
    "sessionId": "a7e83861-6e2c-4001-99d0-fa1e1f0aa4xx"
}	
```
---
- ### LOGOUT

**Method**: POST

**Path**: */logout*

**Description**: Action to close and remove a session

**Headers**:

| Key | Value | Required |
| --- | --- | :---: |
| Content-Type | application/json | :white_check_mark: |

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

```json
{
    "sessionId": "a7e83861-6e2c-4001-99d0-fa1e1f0aa4xx"
}
```

**Response codes**:

| Code | Description |
| --- | --- |
| 200 | OK |

**Sample response**: NONE

---
- ### GENERATE API KEY

**Method**: POST

**Path**: */generateApiKey*

**Description**: Action to generate a new apiKey

**Headers**:

| Key | Value | Required |
| --- | --- | :---: |
| Content-Type | application/json | :white_check_mark: |

**Path parameters**: NONE

**Query parameters**: NONE

**Request body**:

```json
{ 
	"username" : "psnextadmin", 
	"password" : "changeit", 
	"url": "https://192.168.42.128/sciforma",
	"description" : "New api KEY 01 for testing purposes"
}
```

**Response codes**:

| Code | Description |
| --- | --- |
| 200 | OK |
| 401 | Something went wrong with your log in request. Check your sciforma credentials |
| 400 | There is a problem parsing the json content, check your json payload. |

**Sample response**:
```json
{
    "apiKey": "cfVECUL2A1mFQlzJw2unh098BjCyou"
}
```

---
- ### GET RELATED API KEYS

**Method**: GET

**Path**: */apikey/{apikeycode}*

**Description**: Action to obtain the api keys related to the user and URL of the code that is being sent as a parameter.

**Headers**: NONE
> Note: Check the common headers for [requests](README.md#generating-your-request)

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| apikeycode | Api key identifier | :white_check_mark: |

**Query parameters**: NONE

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 200 | OK |
| 401 | The api key is not valid or does not exist |

**Sample response**:
```json
[
  {
    "code": "bq5vl1QXFKf4nqKpIFzvtyquislCSE",
    "username": "****xtadmin",
    "url": "https://192.168.42.128/sciforma",
    "description": "New api KEY 01 for testing purposes "
  },
  {
    "code": "Op9j2deq1HX0Iljd2zLGR8NEyZ6APE",
    "username": "****xtadmin",
    "url": "https://192.168.42.128/sciforma",
    "description": "New api KEY 02 for testing purposes "
  }
]
```

---
- ### UPDATE API KEY

**Method**: POST

**Path**: */apikey/{apikeycode}*

**Description**: Action to updates an existing apiKey

**Headers**:

| Key | Value | Required |
| --- | --- | :---: |
| Content-Type | application/json | :white_check_mark: |

**Path parameters**:

| Code | Description | Required |
| --- | --- | :---: |
| apikeycode | Api key identifier | :white_check_mark: |

**Query parameters**: NONE

**Request body**:

Sample request

```json
{ 
	"username" : "psnextadmin", 
	"password" : "changeit", 
	"description" : "New api KEY 01 for testing purposes"
}
```
All fields are optional, you must send at least one of those


**Response codes**:

| Code | Description |
| --- | --- |
| 200 | OK |
| 401 | The api key is not valid or does not exist |
| 400 | There is a problem parsing the json content, check your json payload. |

**Sample response**: NONE

---
- ### REMOVE API KEY

**Method**: DELETE

**Path**: */removeApikey*

**Description**: Action to remove an existing apiKey

**Headers**:

| Key | Value | Required |
| --- | --- | :---: |
| Content-Type | application/json | :white_check_mark: |

**Path parameters**: NONE

**Query parameters**:

| Key | Description | Required |
| --- | --- | :---: |
| url | Sciforma's url of the configured API key that will be removed | :white_check_mark: |
| username | Sciforma's username of the configured API key that will be removed | :white_check_mark: |
| apiKeyCode | API key code that will be removed | :white_check_mark: |

**Request body**: NONE

**Response codes**:

| Code | Description |
| --- | --- |
| 200 | OK |
| 400 | There is no coincidence among all the parameters |
| 404 | The api key is not valid or does not exist. |

**Sample response**: NONE
