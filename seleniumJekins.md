# Inception
Create the java program

## Selenium
 + https://www.guru99.com/installing-selenium-webdriver.html
 + gecko driver location, 
 + https://www.guru99.com/first-webdriver-script.html

## TestNG
  + https://www.guru99.com/install-testng-in-eclipse.html
  + http://testingfreak.com/create-a-simple-java-project-and-install-testng-in-eclipse/
  + change the main() function to some other name and remove static field from it's declaration
  + Add @Test to this function to test

	```
	TestNG code structure -

	package <packageName>;
	import org.testng.annotations.Test;

	public class Sample {

	@Test
	    public void TestCaseName() {

	      /*
	      Put all your running code here

	      */
	    }
	}
	```

* Add testng dependency instead of JUnit

* Make project a maven project 
   + make changes in pom file
   + add dependencies of testng, maven-surefire-plugin : https://howtodoinjava.com/testng/how-to-execute-testng-tests-with-maven-build/
   + change version for maven-surefire to 3.13.0
   + maven clean and install

* create a testng.xml, remove the source tag
  + change from submit to test inside a tag

* try executing program from pom.xml using console
  ` mvn clean test -DsuiteXmlfile=pom.xml : this is not correct `
  
----
# Jenkin 

* Install it, remember password for user
* install maven packages (all)
* configure jenkin for jdk path, maven path, and pom file's absolute path
* create a new task, configure pom file again
* add jdk and mvn to environment variable
  + Jenkins look from its folder, so root is not / but /Jenkins/....
  + For unix system use //User/sauravk/....
  + notice // at begining
  + don't use online installer
  + add M2, JAVA_HOME environment vars on OS : https://vmware.slack.com/archives/CBTLAHX09/p1532501658000071



