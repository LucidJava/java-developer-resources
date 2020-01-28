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
		Polymorphism is same code giving different behaviour.
	
* **What's the use of `instanceof` operator?**
		Checks if an object is of a particular type.
	