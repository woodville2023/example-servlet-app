JDK 17

###TOMCAT setup

- Download tomcat from https://tomcat.apache.org/download-10.cgi

-   Download the apache-tomcat-10.1.33.zip version to a preferred folder

-   go to the downloaded location

-   extract apache-tomcat-10.1.33.zip using your favorite tool

-   Go inside apache-tomcat-10.1.33 to access managment console
  - go to conf directory and modify tomcat-user.xml with following
  - Add the tomcat user with  password and role 
```
<?xml version="1.0" encoding="UTF-8"?>
<tomcat-users xmlns="http://tomcat.apache.org/xml"
              xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
              xsi:schemaLocation="http://tomcat.apache.org/xml tomcat-users.xsd"
              version="1.0">

  <role rolename="tomcat"/>
  <role rolename="manager-gui"/>
  <role rolename="manager-script"/>
  <role rolename="role1"/>
  <user username="tomcat" password="5159" roles="tomcat,role1,manager-gui,manager-script"/>
  <user username="both" password="tomcat" roles="tomcat,role1,manager-gui,manager-script"/>
  <user username="role1" password="tomcat" roles="role1"/>

</tomcat-users>

```
- Got to http://localhost:8080/management to see installed applicaitons
  
### Apache Maven
- Got to https://maven.apache.org/download.cgi
- Download this file 	apache-maven-3.9.9-bin.zip or the first zip file to a preferred location
- go inside the downloaded directory 
- unzip apache-maven-3.9.9-bin.zip
- change directory to apache-maven-3.9.9-bin
- remember the full path of where you have the apache-maven-3.9.9-bin
- My full path where the maven is in this directory /private/tmp/apache-maven-3.9.9

- set path variable
  - in Mac add path variable in one of the profile files ~/.zshrc,~/.bashrc


      ```
      export PATH="/private/tmp/apache-maven-3.9.9/bin:$PATH" 
      
      ```
  - in Windows using system environment to point to MAVEN_DIR/bin for PATH  

##BUILD and DEPLOY
- Go to test-app directory
- run ```mvn clean install```
- go to target directory
- copy the test-app.war to TOMCAT_DIR/webapps/
- go the browser , go to http://localhost:8080/test-app/first
- 
