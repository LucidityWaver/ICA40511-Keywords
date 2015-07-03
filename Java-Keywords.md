#Keywords for Java (Intermediate)

Beginning Semester 2, 2015.
 
**Instance:** An occurance of something. An instance of a class is called an object.

**Instantiate:** To create an instance of something. e.g: Create an object of a class.

**Dynamic (late) Method Binding:** Program determines correct method based on type of argument passed.
- operates slower than static (fixed) method binding
- used in java instance methods
*When the application executes, the correct method is attached (or bound) to the application based on the current, changing (dynamic) context - ch11-2: Using Dynamic Method Binding*


**Static (fixed) Method Binding:** Method selection occurs at when program is compiles, not while it is running.
- Operates faster than dynamic method binding.
- Used in java class methods
*ch11-2: Advanced Inheritance Concepts*

**Ad-hoc polymorphism:** describes polymorphism with a single method name, but multiple implementations.
- Another name for method overloading
- [See example here](http://beginnersbook.com/2013/05/method-overloading/)

**Pure / Inclusive Polymorphism:** describes polymorphism in which a superclass is used as a method parameter.
- One method implementation which can be used across a variety of related objects.
- The argument provided is a subclass of the parameter type. See example below.

```
printEmployee(Employee e) {
	System.out.println(e.getName());
}
Supervisor supervisor = new Supervisor();
printEmployee(supervisor);
```

**:**
