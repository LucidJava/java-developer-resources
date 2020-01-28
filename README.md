# Reources for a Senior Java Developer
A repository that helps you become a better senior Java developer.
If you have something useful to add, please create a pull request.



## Core Java Interview Questions  


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
    * An overriding method cannot throw a higher exception than that of the overriden one.
		
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

- **Where are String values stored in memory?**

    In String Constant Pool, an area inside the Heap memory. 

    If the compiler finds a string literal, it checks in the pool. If exists, it is reused.

- **Why should you be careful when using String concatenation inside loops?**

    Each time you do a concat, you create a new object. Inside the loop, it may create a hell of objects.

    Use **StringBuilder** or **StringBuffer** (thread-safe).

- **Difference between String and StringBuffer?**

    Objects of String type are immutable. 

    Both String and StringBuffer are thread-safe.

- **Difference between StringBuilder and StringBuffer?**

    StringBuffer is synchronised and so is threadsafe, and slow.

    StringBuilder is not synchronised and is faster.

    Both StringBuffer and StringBuilder are mutable alternatives to String.

    When your code has to do a lot of concatenations, you should use StringBuilder by default, unless you are sure you need thread-safety.