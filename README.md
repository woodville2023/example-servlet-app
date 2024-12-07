JDK 17
Download tomcat from https://tomcat.apache.org/download-10.cgi
Download the zip version to a preferred folder

go to the downloaded location
extract apache-tomcat-10.1.33.zip using your favorite tool

Go inside apache-tomcat-10.1.33 
```
cd apache-tomcat-10.1.33 
modify conf/tomcat-user.xml
replace this file content with  following
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

Download apache maven to a preferred location
Download this file 	apache-maven-3.9.9-bin.zip or the first zip file to a preferred location
go inside the downloaded directory 
unzip apache-maven-3.9.9-bin.zip
change directory to apache-maven-3.9.9-bin
remember the full path of where you have the apache-maven-3.9.9-bin
My full path where the maven is in this directory
/private/tmp/apache-maven-3.9.9

set path variable


export PATH="/private/tmp/apache-maven-3.9.9/bin:$PATH" in one of the profile files
in windows this will be different
