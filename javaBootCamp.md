# Day 2 : 17/7/18 : tomcat, maven
____

# To create a new project

` mvn archetype:generate -DgroupId=com.vmware.ncgbootcamp2018 -DartifactId=contact-book -DarchetypeArtifactId=maven-archetype-quickstart

# To create a new web project

` mvn archetype:generate -DgroupId=com.vmware.ncgbootcamp2018 -DartifactId=contact-book-web -DarchetypeArtifactId=maven-archetype-webapp
# To build the source, by traversing in the newly created folder 
``` mvn clean install


# to find process id of tomcat(java) if running
ps -aef | grep -i java | grep -v grep

## never install tomcat with installer for windows, use .zip archive
## always clean the webapp folder of tomcat
____ 
## Process for using
 1. change webapp.war to ROOT.war
  + make sure no tomcat instance is active
  + if tomcat server is active, a folder with same name as file will be created
 2. copy it to webapp folder, after removing every thing
 3. localhost:8080 is general goto address of tomcat
 
# to start tomcat server
./catalina.sh run

# to shut it down 
./shutdown.sh 
