# :wrench: Configuration parameters
The configuration parameters are stored in a configuration file that can be edited with any text editor. It is tipically located at *SCIFORMA_API_HOME/SCIFORMA_**VERSION**/sciforma.properties*. 

> You can modify the SCIFORMA_API_HOME in the file /sciforma-commons.jar/com/rego/sciforma/commons/configuration/standalone_config.properties

Any changes you make requires a restart of the web application:

- **KEEP_ALIVE_TIMER:** The length of time to check the session status (In milliseconds)
- **TOKEN_TIMEOUT:** Time used to determine when a session has expired. You can define this time in seconds, minutes and hours, for example: 60s, 15m, 1h
- **USE_POST_TO_UPDATE:** Indicates with a Boolean value (true/false) if POST requests allows updates or are only accepted with PUT method
- **EXCLUDED_DATAVIEWS:** Indicates what dataviews must be excluded from processing
- **SESSION_POOL_INITIAL_SIZE:** It is the minimum number of sessions that must be openned once the service is deployed
- **SESSION_POOL_MAXIMUM_SIZE:** It is the maximum number of openned sessions allowed by the service. Once this number is reached no more session can be openned.

```properties
#The length of time to check the session status (In milliseconds)
KEEP_ALIVE_TIMER=3000

#Time used to determine when a session has expired. 
#You can define this time in seconds, minutes and hours, for example: 60s, 15m, 1h
TOKEN_TIMEOUT=40m

#Indicates with a Boolean value (true/false) if POST requests allows updates or are only accepted with PUT method
USE_POST_TO_UPDATE=true

#List of data view names forbidden/excluded to be processed (Comma separated)
EXCLUDED_DATAVIEWS=

#Initial size of the session pool for the apiKey
SESSION_POOL_INITIAL_SIZE=1

#Maximum size of the connection pool for the apiKey
SESSION_POOL_MAXIMUM_SIZE=5
```
