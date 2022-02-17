# Development environment setup
SciForma REST API is a Java solution, based on Java EE 7. It uses Maven to compile and package the final artifact.

## Table of contents
- [Pre-requisites](#1-pre-requisites)
- [Configuring the Apache TomEE Server](#2-configuring-the-apache-tomee-server)
- [Configuring the Eclipse IDE](#3-configuring-the-eclipse-ide)
- [Configuring Maven](#4-configuring-maven)
- [Compiling and running](#5-compiling-and-running)

<br/>

### 1. Pre-requisites
* Java Development Kit - JDK 8 (Set the installation directory as **JAVA_HOME**)
* Any compression utility (7-Zip)
* Any file editor (Notepad++, Atom)

<br/>

### 2. Configuring the Apache TomEE Server
* Download [Apache TomEE 7.1.x](http://tomee.apache.org/download-ng.html), select **PLUS** version

* Unzip downloaded file (Referenced as **TOMEE_HOME**). Go to TOMEE_HOME/bin folder, add new file and name it as ‘setenv.bat’ and add the content below:

```
set CATALINA_OPTS=-Xms1024m -Xmx1536m
```

* Go to TOMEE_HOME/conf folder:
  - **server.xml:** Configure the TomEE ports, e.g: Java HTTP Connector, Java AJP Connector, APR (HTTP/AJP) Connector, and define a non-SSL HTTP/1.1.
  
  Below an example of how to the HTTP port is changed to 80
  
  ```xml
  <Connector connectionTimeout="20000" port="80" protocol="HTTP/1.1" redirectPort="8443" server="Apache TomEE" xpoweredBy="false"/>
  ```
 
* Start the server, execute TOMEE_HOME/bin/startup.bat. 

<br/>

### 3. Configuring the Eclipse IDE
* Download [Eclipse](https://www.eclipse.org/downloads/packages/). Select IDE for Enterprise Java Developers
* Unzip downloaded file (Referenced as **ECLIPSE_HOME**). Go to ECLIPSE_HOME and open ‘eclipse.ini’ file, adjust memory settings:
```
-Xms512m
-Xmx1024m
```
* Run eclipse.exe and select your workspace.
* Go to _Windows -> Preferences -> Java -> Installed JREs_. Verify that the installed JDK is selected or add it.
* Now make the association of Apache TomEE server. Go to the ‘Servers’ tab. (If it is not visible, press CTRL + 3 and search ‘servers’ tab)

<p align="center">
<img src="https://relevus.github.io/sciforma-rest-services-docs/img/addingServer.gif?raw=true" />
</p>

<br/>

### 4. Configuring Maven
* Download [Apache Maven](https://maven.apache.org/download.cgi), select 3.6.x version
* Unzip downloaded file (Referenced as **MAVEN_HOME**)
* Edit the file at MAVEN_HOME/conf/settings.xml. Add a new profile
```xml
<profiles>
  ...  
	<profile>
		<id>rego</id>
		<activation>
			<activeByDefault>true</activeByDefault>
		</activation>
		
		<repositories>
			<repository>
				<id>rego-repo</id>
				<name>Rego Repository</name>
				<url>http://tools.dev.regoconsulting.net:8084/repository/rego</url>
				<layout>default</layout>
				<releases>
					<enabled>true</enabled>
				</releases>
				<snapshots>
					<enabled>true</enabled>
				</snapshots>
			</repository>
		</repositories>		
	</profile>
	...
</profiles>
```
* Configure Maven in Eclipse. Go to _Window -> Preferences -> Maven -> Installations. Add new installation_
* Go to _Maven -> User settings_. Change the settings file, choose MAVEN_HOME\conf\settings.xml
* Click in ‘Apply and Close’.

<br/>

### 5. Compiling and running
* Once the GIT Repository has been cloned, follow the steps below.
* Enter the URI: https://github.com/regoconsulting/sciforma-rest-services.git
* The new repository should appear in the ‘Git repositories’ tab. Do right click, Import projects. Select ‘Import Maven projects...’, CLick on _Next_ and then on _Finish_
* Open the file sciforma-bom/pom.xml. Set the values for <tomee.home/> (Use TOMEE_HOME path) and <version.sciforma/>
```
<properties>
  ...
  <!-- Environment configuration-->
  <tomee.home>D:\Servers\apache-tomee-plus-7.1.1</tomee.home>
  <version.sciforma>7.1j</version.sciforma>
  ...
</properties>
```
* Execute ‘Run as -> Maven’ build or install in the sciforma-bom.
* Start Apache TomEE
