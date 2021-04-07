# Product architecture
The SciForma REST API is a lightweight web project that uses the Java API for RESTful Web Services. Its main purpose is to simplify and standardize the connection with SciForma through REST requests in JSON format.

It consists of a single WAR file, which contains the required libraries:

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/Deployment%20model.png?raw=true" />
</p>

<br/>

- ## Requirements
  * Java 8
  * Apache TomEE 7.1.x

<br/>

- ## Main components
Below is a model of the main components of the application:

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/Main%20components.png?raw=true" />
</p>

### Session handling

All session management is done in the **SciformaSessionManager** component, regardless of the chosen authentication method.  Here we have a map with the list of active sessions, its associated ID and the Api Key (When applicable).

There is a single instance that is created when the application is deployed and starts the thread called **KeepAliveThread**. This process runs constantly, verifying every N seconds if the open SciForma sessions have already expired to close and remove them.

N seconds are defined in [Configuration parameters](prop_configuration.md)

Each session is kept alive in cache by the **SessionConnectionPool** so it can be reused whenever request comes to connect with Sciforma. Connection Pooling reduces Sciforma hits and improves application performance significantly. Each connection pool has a limited number of connection slots available and it is defined by a minimum number and a maximum number (SESSION_POOL_INITIAL_SIZE and SESSION_POOL_MAXIMUM_SIZE respectively), once that maximum number of connection to the pool is reached, no more connections are allowed by the REST API.

<br/>

- ## Components interaction in a GET request

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/Get%20request.png?raw=true" />
</p>

<br/>

- ## Components interaction in a POST request

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/Post%20request.png?raw=true" />
</p>

<br/>
