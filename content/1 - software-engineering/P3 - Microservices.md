---
tags:
  - software-engineer
---


## Theory

### Basics Theory

What does SOA mean?
![[Pasted image 20250215172004.png]]
?x
Soa: Service Oriented Architecture

What is Microservice?
?x
Microservices is an approach to developing a single application as a suite of small services, each running in its won process and communicating with light weight mechanism, built around business capabilities and independently deployable by fully automated deployment machinery


Why Spring Boot for Microservices vs Core Java Tools?
![[Pasted image 20250215171934.png]]
?x
In the traditional approach, applications are typically packaged as WARs and rely on the presence of a server in the execution environment for running, However in the micro services paradigm, applications are packaged as self-contained JARS also called fat-JAR or uber-JARs, since htye contain the application itself, the dependencies, and the embedded server.


Data Transfer Object - Pattern
What is DTO used for?
![[Pasted image 20250216221750.png]]
?x
- **Reduces Network Traffix**: DTOs can be used to batch up multiple pieces of data into a single object, which can reduce the number of network request that need to be made. This canimprove performance and reduce the load on your servers
- **Encapsulates Serialization**: DTOs can be used to encapsulate the serialization for transferring data over the wire. This makes it easier to change the serialization format in the future, without having to make changes to the rest of your application.
- **Decouples layers**: DTOs can be used to decouple the presentation layer form the data access layer. This makes it easier to change the presentation layer without having to change the data access layer
- Look this up: https://martinfowler.com/eaaCatalog/dataTransferObject.html



## Building using Spring Boot


Build the project using:
https://start.spring.io/
Dependencies:

- **Spring Web Web**Build web, including RESTful, applications using Spring MVC. Uses Apache Tomcat as the default embedded container.[](https://start.spring.io/)
    
- **H2 Database SQL**Provides a fast in-memory database that supports JDBC API and R2DBC access, with a small (2mb) footprint. Supports embedded and server modes as well as a browser based console application.[](https://start.spring.io/)
    
- **Spring Data JPA SQL**Persist data in SQL stores with Java Persistence API using Spring Data and Hibernate.[](https://start.spring.io/)
    
- **Spring Boot Actuator Ops**Supports built in (or custom) endpoints that let you monitor and manage your application - such as application health, metrics, sessions, etc.[](https://start.spring.io/)
    
- **Spring Boot DevTools Developer Tools**Provides fast application restarts, LiveReload, and configurations for enhanced development experience.[](https://start.spring.io/)
    
- **Lombok Developer Tools**Java annotation library which helps to reduce boilerplate code.[](https://start.spring.io/)
    
- **Validation I/O**Bean Validation with Hibernate validator.




## Projects


### Capstone Project


#### Finance Tools Infrastructure
- Build a microservice Structure for the Finance Cloud
	- This should integrate multiple tecnologies involving Python Interpreters
		- Java Services for other tasks
		- Contain a Lua/Python interpreter for simulating financial algorithms
		- Create alars and different micro

#### Gaming and Betting Infrastruture

*Idea, an all encompasing game with multiple games on them where you improve the overall *



## Readings


Catalog of Patterns of Enterprise Application Architecture https://martinfowler.com/eaaCatalog/


