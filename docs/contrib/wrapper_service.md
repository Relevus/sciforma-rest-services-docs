# Wrapper service

The SciForma REST API has an optional web module that you can install in front, when you want to support multiple versions of Sciforma.

It is a utilitarian service that facilitates the resolution of the specific URLs of each version; redirects all requests based on request header where the desired Sciforma version is set.

You configure a list of URLs of the REST services, the system verifies the version and determines where the request is redirected.

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/context_wrapper_service.png?raw=true" />
</p>

<br/>

## How does it work?

The component has a configuration file where the Sciforma versions and the respective URLs of the REST service are registered.

```properties
#Sciform instances available
defaultVersion=7.1j
7.1j=http://server01/sciforma-rest/7.1j
7.1p=http://server02/sciforma-rest/7.1p
7.1s=http://server03/sciforma-rest/7.1s
7.1t=http://server03/sciforma-rest/7.1t
```

When a request arrives, it is analyzed if there is a header called 'Sciforma-Version'; if it was not sent, the default version is assumed (Taking the value of 'defaultVersion' property)

Finally, the URL that matches the version is taken. If the header contains an unknown version, an error BAD_REQUEST (400) is thrown.

```
The <<sciformaVersion>> version is not supported
```

<br/>

## What happens to the apiKey when the Sciforma version is updated?

The wrapper service makes sure to copy an existing apiKey from a previous version to the new one. Password data is encrypted in the transmission, never transformed to plain text.

<p align="center">
<img src="https://regoconsulting.github.io/sciforma-rest-services/img/apiKeyCompatibility.png?raw=true" />
</p>

<br/>


> No additional processing is applied to the request or response
