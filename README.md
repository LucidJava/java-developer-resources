# Reources for a Senior Java Developer
A repository that helps you become a better senior Java developer.
If you have something useful to add, please create a pull request.



## Core Java Interview Questions
* What's the difference between JDK, JRE and the JVM?
`JDK = javac + jar + debugging tools + javap + JRE`

`JRE = java + javaw + libraries + rt.jar + JVM`

`JVM = Interpreter + JIT compiler`

* What's the purpose of ClassLoaders?
A ClassLoader is a part of the JRE that dynamically loads classes on to the JVM.

It's also something that searches classes for us.

System class loader -  Looks in the CLASSPATH

Extension class loader - Looks in jre, ext, lib folders

Bootstrap class loader - Loads all Java core files
