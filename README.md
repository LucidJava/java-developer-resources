# Reources for a Senior Java Developer
A repository that helps you become a better senior Java developer.
If you have something useful to add, please create a pull request.



## Core Java Interview Questions  

Note: These questions serve as a quick reference or a refresher of whatever existing knowledge you have. 
This is not a place for learning exhaustively.  


### Java Platform
____
* **What's the difference between JDK, JRE and the JVM?**

	`JDK is a superset of JRE. JRE is a superset of JVM.`
	
	JDK is the complete development environment that includes Java Compiler, Interpreter and other tools
	JRE is the runtime environment you need to run your Java program. This includes JVM in itself.
	JVM is the interpeter for your byte code. It comes along with a JIT compiler it uses to optimize the interpretation.

  `JDK = javac + jar + debugging tools + javap + JRE`

  `JRE = java + javaw + libraries + rt.jar + JVM`

  `JVM = Interpreter + JIT compiler`

* **What's the purpose of ClassLoaders?**
 
  A ClassLoader is a part of the JRE that dynamically loads classes on to the JVM.

  It's also something that searches classes for us.

  `System class loader -  Looks in the CLASSPATH`

  `Extension class loader - Looks in jre, ext, lib folders`

  `Bootstrap class loader - Loads all Java core files`  
  

### Advanced OOP
____

* **Define polymorphism?**  
    > **Polymorphism is same code giving different behaviour.**  
		
    * Compile-time polymorphism aka Method overloadling is with methods in the same class sharing same name, but a varying number/type/order of arguments.
		
    * Run-time polymorphism aka Method overriding is with methods in the parent vs child class sharing the same name and signature.
		
* **What are the rules for method overloading?**  
    * Overloading is only possible by creating two methods with same name and different signature. Signature includes the number, type and order of arguments.
    * Two methods with same name and signature, and a different return type - are NOT overloaded
    * Two methods with same name and signature, and a different access modifier - are NOT overloaded

* **What are the rules for method overriding?**  
    * A method of a class can only be overloaded in its sub-class.
    * An overriding method should have same name, signature annd return type as the overriden method.
    * An overriding method cannot reduce or increase the access of the overriden method.
    * An overriding method cannot throw a higher exception than that of the overriden one. You can throw something lower or you can skip throwing.
		
* **What's the philosophy behind Encapsulation?**  
		Even if the internal implementation changes, the external classes will not be affected.
	
* **What's the use of `instanceof` operator?**  
		Checks if an object is of a particular type.
		
* **What is coupling?**  
		Coupling is a measure of how much a class is dependent on other classes.
		We should keep the classes as loosely coupled as possible.
		We can use POJOs with private member variables and public methods which act on the variables.
	
* **What is cohesion?**  
		Cohesion is a measure of how related the responsibilities of a class are.
		Good classes are desiged to be highly cohessive.
		
* **Why do we need nested classes?**  
    * It's a logical way of grouping classes that should be at one place.
    * We get better Encapsulation
    * It can improve code readability and maintainability
    
* **What are the types of nested classes?**  
		Nested classes are divided into two categories: static and non-static. 
		Nested classes that are declared static are simply called static nested classes. Non-static nested classes are called inner classes.

    > NON STATIC NESTED CLASS: To access the class name of an inner class, we need the class name of the outer class; to create an object of an inner class, we need the object of the outer class.
    > STATIC NESTED CLASS: If the inner class is a static class, we can use the outer class name both for accessing the inner class and its object.		
	
	There can be two special types of Non-static nested classes:
    - Local Classes
    - Anonymous classes
    
* **Why do we need an interface? What is something that an interface do and an abstract class can't?**
		An interface is a contract that an implementation class should honour.
		An interface defines a certain kind of behaviour that has to be supported by the implementation class. 
		Unlike an abstract class, an interface contains no state and doesn't participate in inheritence.
		
    * What does an interface do that an abstract class can't?
    	An interface can attribute multiple types of behaviour to a single implementation class.
    	In other words, an implementation class can implement multiple interfaces but not multiple abstract classes.
    	
* **Interface variables are static and final by default in Java, Why?**
		An interface cannot be instantiated on its own, and it doesn't have a state.
		Hence it should not have instance variables, thus all the variables are static by default.
		They are also final to avoid data inconsistencies as multiple classes may implement the interface and try to modify the variables.
		

### String & Immutability
____	 

- **Are all Strings immutable?**

    Yes. Even the String's `concat()` method returns a new instance with the concatenated result.

    The case is same for `toLowerCase()` and `toUpperCase()`

- **Where exactly are String values stored in memory?**

    In **String Constant Pool**, an area inside the Heap memory. 

    If the compiler finds a string literal, it checks in the pool. If exists, it is reused.

- **Why should you be careful when using String concatenation inside loops?**

    Each time you do a concat, you create a new object. Inside the loop, it may create a hell of objects.

    Use **StringBuilder** or **StringBuffer** (thread-safe).

- **Difference between String and StringBuffer?**

    Objects of String type are immutable. StringBuffer is a mutable type.

    Both String and StringBuffer are thread-safe.

- **Difference between StringBuilder and StringBuffer?**

    StringBuffer is synchronised and so is threadsafe, and slow.

    StringBuilder is not synchronised and is faster.

    Both StringBuffer and StringBuilder are mutable alternatives to String.

    When your code has to do a lot of concatenations, you should use StringBuilder by default, unless you are sure you need thread-safety.

- **Why String is immutable in Java?**    
    > Classes which are key to Java's security commitment are final, so that no can change their behaviour and game with Java platform - James Goslig
 
- **What design pattern does String follow?**
    > String's Constant Pool follows Flyweight design pattern.
    Flyweight design pattern is about reducing the number of objects created and reducing the memory footprint. 
    String achieves this by resuing objects with the Constant pool.
    

### Exception Handling
____

- **What's the difference between `ClassNotFoundException` and `NoClassDefFoundError?`**   
	Both of these occure when JVM couldn't load a class.
	But `ClassNotFoundException` occurs when you can't find a class definition at runtime, for instance when you try to load a class using Class.forName()
	And `NoClassDefFoundError` occurs when a specific class is present at compile time and missing at run time. 
	For instance you java file generates two class files when compiled, and you delete on of the class files, and when you try to run the app you face this error.
	
	Also, the former is of type `Exception`, the later is a child of `Error`.


## Spring Boot Interview Questions  	

- **Advantages of Springboot?**
    -Spring Boot provides us _*starter*_ dependencies, which simplifies our build configuration
    -The @EnableAutoConfiguration feature does magical detection and configuration of beans we need
    -Comes with an embedded container for Jetty, Tomcat, Undertow, Netty - we don't have to deploy WAR files
    -Production ready features like health checks, centralized configurations, metrics
    -Springboot makes it very easy to work with Spring Profiles. Enter *Profile-specific property files*.
    -We have a Spring Initializer tool to boot our projects from projects hassle-free.

- **What's the advantage of `@EnableAutoConfiguration` ?**    
    This annotation intelligently figures out and configures the beans you will likely need based on your classpath.
    If you have a hibernate/jpa dependency in the build file and a configuration file/class in the source for hibernate, 
    it automatically detects and gives us a SessionFactory / EntityManager bean which we can autowire and use in our applications.

- **How do you configure JPA for Couchbase?**
    *We should first include the dependency for Spring Data Couchbase `spring-boot-starter-data-couchbase` in our build file. 
    *Create an `@configuration` class for couchbase. This class should extend `AbstractCouchbaseCofiguration` and override `getBooststrapHosts()`, `getBucketName()` and `getBucketPassword()` methods
    *Create an entity class (called Documents in couchbase) that will have fields including an  `@Id` field.
    *Create an `@Respository` interface that extends `CrudRepository` and declare methods you need. This can be autowired and used in your DAO classes.
    *Alternatively, you can create a `@Bean` definition for `Bucket` in you configuration class, and can autowire it in your DAO classes to directly operate on the documents.

      
## SQL Interview Questions 

- **What is an inner join?**
	Inner join fetches only the matching records from two tables.
	
- **Query to get the nth highest salary of an employee?**
	`SELECT DISTINCT salary from employee ORDER BY salary DESC LIMIT 1 OFFSET (n-1)`
	
## System Design Interview Questions 

- **Difference between a Queue and a Topic?**
	Topics are for the publisher-subscriber model, while queues are for point-to-point.
	
- **Difference between a XA and non-XA datasources?**
	An XA datasource deals with global transactions, which often handle multiple resources.
	A non-XA transaction often involves a single resource.
	
	XA gets involved when you want to work with multiple resources - 2 or more databases, a database and a JMS connection, all of those plus maybe a JCA resource - all in a single transaction. 
	In this scenario, you'll have an app server like Websphere or Weblogic or JBoss acting as the Transaction Manager, and your various resources (Oracle, Sybase, IBM MQ JMS, SAP, whatever) acting as transaction resources. 
	Your code can then update/delete/publish/whatever across the many resources. When you say "commit", the results are commited across all of the resources. 

- **Why do we use ramp up period in Jmeter?**	
	Ramp up period tells the tool how long it should take to create the total number of threads.
	If you have 100 users with a ramp up of 10 seconds, then JMeter creates 10 theads per each second.
	

## Agile Interview Questions 

- **What's your role in a Scrum team?**
	[subjective] I am part of the development team, and I work directly with the client.
	
- **What's a User Story?**
	A high level definition of the requirement, containing just enough information so that the developers can produce a reasonable estimate of the effort to implement it.	
	
- **What's Sprint velocity?**
	A metric that tells the amount of work a team can handle in a single Sprint.
	
- **What's Sprint burndown chart?**
	A burndown chart is a graphical representation of work left to vs time.
	

## Microservices Interview Questions 

- **What are microservices?**	
	Microservices is an architecture style where small, autonomous services work together.
	
- **What are the principles of microservices?**	
    *Single responsibility
    *Built around business
    *You build it, you own it
    *Infrastructure automation
    *Desin for failure
    
- **What are the benefits of microservices?**	
    *We can choose *fit for purpose architecture* with microservices
    *Microservices enable selective scalability
    *It is possible to change and update technology for each microservice individually
    *Enable smaller, focused agile teams for development
    *We have smaller, comprehensive codebases
    
- **What are the challenges of microservices?**	
    *As the application grows bigger, we'll need to manage a lot of microservices.
    *Each microservices may need its own deployment environment and resources
    *We need more skilled developers to handle distributed application complexities

- **How do you configure microservices in your application?**	   
 
    
