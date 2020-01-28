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
    > Polymorphism is same code giving different behaviour.  
		
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
		
* **Why do we use inner classes?**  
		Cohession is a measure of how related the responsibilities of a class are.
		Good classes are desiged to be highly cohessive.
		
		
