# Server installation
SciForma REST API is a Java solution, based on Java EE 7.

## Table of contents
- [Pre-requisites](#1-pre-requisites)
- [Configuring the Apache Tomcat Server](#2-configuring-the-apache-tomcat-server)
- [Sciforma REST installation](#3-sciforma-rest-installation)
- [Extra configuration](#4-extra-configuration)

<br/>

### 1. Pre-requisites
* Java Development Kit - JDK 8 (Set the installation directory as **JAVA_HOME**)
* Any compression utility (7-Zip)
* Any file editor (Notepad++, Atom)

<br/>

### 2. Configuring the Apache Tomcat Server
* Download [Apache Tomcat 8.5.x](https://tomcat.apache.org/download-80.cgi), select the latest version

* Unzip downloaded file (Referenced as **TOMCAT_HOME**). Go to TOMCAT_HOME/bin folder, add new file and name it as ‘setenv.bat’ and add the content below:

```
set CATALINA_OPTS=-Xms1024m -Xmx1536m
```

* Go to TOMCAT_HOME/conf folder:
  - **server.xml:** Configure the Tomcat ports, e.g: Java HTTP Connector, Java AJP Connector, APR (HTTP/AJP) Connector, and define a non-SSL HTTP/1.1.
  
  Below an example of how to the HTTP port is changed to 80
  
  ```xml
  <Connector connectionTimeout="20000" port="80" protocol="HTTP/1.1" redirectPort="8443" />
  ```

> NOTE: Additional configurations can be found in official [Apache Tomcat](https://tomcat.apache.org/tomcat-8.5-doc/index.html) documentation

<br/>

### 3. Sciforma REST installation

* Copy the sciforma-rest#*VERSION*.war file to TOMCAT_HOME/webapps.

* A configuration folder is required in order to make work the Sciforma REST API, by default this folder is located at USER_HOME/SCIFORMA_**VERSION**, being '**VERSION**' the desired Sciforma version, (e.g. SCIFORMA_**7.1j**). 

Download the configuration content [here](../packages/sciforma_conf.zip?raw=true) and unzip it in USER_HOME/SCIFORMA_**VERSION**.

> If the user wants to change the default folder's location, must edit the standalone_config.properties file located inside the sciforma-rest#*VERSION*.war at */WEB-INF/lib/sciforma-commons-1.0.0.jar/com/rego/sciforma/commons/configuration/standalone_config.properties*

* Start the server, execute TOMCAT_HOME/bin/startup.bat. 

* Open the application by accessing the url with format SERVER_URL/sciforma-rest/**VERSION**/v1, being SERVER_URL the url/port of the server (Ex. http://localhost:8090), and '**VERSION**' the Sciforma installation's version (e.g. 7.1j).

* Application logs can be found at TOMCAT_HOME/logs/Sciforma_**VERSION**.log


<br/>

### 4. Extra configuration

> The sciforma-services.war is an optional module, you should only use it when it is necessary to support several Sciforma versions.

* Once deployed the war files, the user can change the urls that were set up in the sciforma-services.war to redirect to each Sciforma version. User can do it by editing the file TOMCAT_HOME/webapps/sciforma-services/WEB-INF/classes/com/rego/sciforma/services/util/services_config.properties

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/serviceRedirects.gif?raw=true" />
</p>
