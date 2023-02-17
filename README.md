# Burger Tracker
<!-- can have readme preview open as well to see how it will appear -->
<!-- - this is a bullet -->

<!-- ## this is a sub heading -->
### Create a Burger Tracker 
-  Create an app to track users' burger experiences
-  The project that will store the details for every burger and allow users to add new burgers from a form

1. Create a new Spring Project with packages for models, repositories, services and controllers.

2. Create a model called Burger with all the appropriate fields. Don't forget to add annotations and getters & setters!

3. Add all the appropriate dependencies and setup for adding JSP views and connecting to the database

4. Create a schema for the project and test the setup by running your project. Debug as necessary!

5. Create an index.jsp file with a table and a form (hard coded for now).

6. Create a route in your controller to render index.jsp and just test that it renders.

7. Set up your BurgerRepository (findAll is the only necessary query method to add at this time)

8. Set up your BurgerService with any necessary methods. Don't forget to inject your repository interface as a dependency.

9. Add @ModelAttribute annotation and associated syntax to your render route, to bind an empty Burger object to the JSP form to capture the user input.

10. In your JSP, change the form tags to form:form tags, add the modelAttribute, error tags and be sure to include the path attribute.

11. Add a POST route in your controller to process the form and add a new burger to the database, using the @ModelAttribute annotation to receive the filled Burger object.

12. Be sure the POST route redirects to the render route after creating the new burger.

13. Test successful creation by adding some new (valid) entries in the form. For now, use workbench to see the results in the database.

14. In your render route, retrieve all the records from the database and render them on the page and test.

15. Finally, be sure to handle validations in your POST method. If the user has any errors, you'll need to render the page again. But remember, you may need to send in some data here as well!




<!-- 
Test: Show how to add a web browser
[website](https://www.google.com) -->


 - ## Checklist
- [ ] update [application.properties](/src/main/resources/application.properties)
<!-- how to put in code blocks us ```-->
```
# Where are jsp files? HERE!
spring.mvc.view.prefix=/WEB-INF/
# Data Persistence
#<!-- after the '/' is <<WHATEVER_YOUR_SCHEMA_NAME>> that you created in MySQL Workbench -->
spring.datasource.url=jdbc:mysql://localhost:3306/burger_tracker
spring.datasource.username=root
spring.datasource.password=rootroot
spring.jpa.hibernate.ddl-auto=update
# For Update and Delete method hidden inputs
spring.mvc.hiddenmethod.filter.enabled=true
```


- ### After adding this to my pom fie it will ask if you want to update -> always say yes
- [ ] [pom.xml](pom.xml)
```
		<!-- 
		& add the two dependency files here 
		-> after save click yes so Maven can update the dependencies that we can use
		--> 

		<dependency>
			<groupId>org.apache.tomcat.embed</groupId>
			<artifactId>tomcat-embed-jasper</artifactId>
        </dependency>
		<dependency>
                <groupId>javax.servlet</groupId>
                <artifactId>jstl</artifactId>
        </dependency>

		<!-- & Bootstrap -->
	    <dependency>
        <groupId>org.webjars</groupId>
        <artifactId>webjars-locator</artifactId>
        <version>0.30</version>
		</dependency>
		
		<!-- BOOTSTRAP DEPENDENCIES -->
		<dependency>
			<groupId>org.webjars</groupId>
			<artifactId>bootstrap</artifactId>
			<version>5.0.1</version>
		</dependency>
		<dependency>
			<groupId>org.webjars</groupId>
			<artifactId>jquery</artifactId>
			<version>3.6.0</version>
		</dependency>

        <!-- & DEPENDENCIES FOR DISPLAYING JSPS AND USING JSTL TAGS -->
        <dependency>
            <groupId>org.apache.tomcat.embed</groupId>
            <artifactId>tomcat-embed-jasper</artifactId>
        </dependency>
        <dependency>
            <groupId>javax.servlet</groupId>
            <artifactId>jstl</artifactId>
        </dependency>

        <!-- & DEPENDENCY FOR USING VALIDATION ANNOTATIONS -->
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-validation</artifactId>
        </dependency>

        <!-- & Bootswatch -->
		<dependency>
			<groupId>org.webjars.npm</groupId>
			<artifactId>bootswatch</artifactId>
			<version>5.2.3</version>
		</dependency>
```


- [ ] add [index.jsp](src/main/webapp/WEB-INF/index.jsp)
<!-- 
when you make this 
    -> can click it and vs code will say the file is not there 
    -> can create file
-> make sure in the right place -->
```
<%@ page language="java" contentType="text/html; charset=UTF-8" pageEncoding="UTF-8"%>
<!-- c:out ; c:forEach etc. --> 
<%@ taglib prefix = "c" uri = "http://java.sun.com/jsp/jstl/core" %>
<!-- Formatting (dates) --> 
<%@ taglib uri="http://java.sun.com/jsp/jstl/fmt" prefix="fmt"  %>
<!-- form:form -->
<%@ taglib prefix="form" uri="http://www.springframework.org/tags/form"%>
<!-- for rendering errors on PUT routes -->
<%@ page isErrorPage="true" %>
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Tacos</title>
    <link rel="stylesheet" href="/webjars/bootstrap/css/bootstrap.min.css">
    <link rel="stylesheet" href="/css/main.css"> <!-- change to match your file/naming structure -->
    <script src="/webjars/jquery/jquery.min.js"></script>
    <script src="/webjars/bootstrap/js/bootstrap.min.js"></script>
    <script type="text/javascript" src="/js/app.js"></script><!-- change to match your file/naming structure -->
</head>
<body>
   
</body>
</html>

```
- [ ] add a schema in MySQL Workbench


<!-- 
-> Always generate the MainController by hand 
-> packages will differ for each directory 
-> this will make sure the file is in the right place
-->
- [ ] add controller [MainController.java](src/main/java/com/rochelle/burger_tracker/controllers/MainController.java)


- add this to the MainController.java
```
//MainController.java
    @Autowired BurgerService burgerService;
```

- To connect service with controller
- [ ] add `@Entity` and `@Table` `@Id` `@GeneratedValue` to the [model](src/main/java/com/rochelle/burger_tracker/models/Burger.java)

<!-- need to add a service folder and file with whatever name you want -->
- [ ] add a [WhateverService.java](src/main/java/com/rochelle/burger_tracker/services/BurgerService.java)

<!-- add service annotation -->
- add 
```
//BookService.java
@Autowired BurgerRepository burgerRepository;
```

<!-- need to add a repository folder and file with whatever name you want -->
- To connect service with repository
- [ ] add a [WhateverRepository.java](src/main/java/com/rochelle/burger_tracker/repositories/BurgerRepository.java)


# Burger_Tracker
