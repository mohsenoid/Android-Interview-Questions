# Android Interview
![Android Interview - OOP Questions](images/oop.png)

## Object-Oriented Programming

OOP serves as the basis of Android app development, and be prepared for interviewers to evaluate your expertise in this area.

1. #### Name some of the characteristics of OOP languages

   * Abstraction
   * Encapsulation
   * Inheritance
   * Polymorphism

2. #### What are the access modifiers you know? What does each one do?

   * `public`: modifier is widely used on classes, variables, constructors, and methods to grant access from any class and method anywhere.
   * `private` (by default): variables, methods, constructors, or inner classes are only visible to its' containing class and its' methods.
   * `protected`: can be used on variables, methods, and constructors therefore allowing access only to subclasses and classes that are inside the same package as protected members' class.

3. #### What is the difference between overriding and overloading a method in Java?

   * Overload (one method with different signatures)
   * @Override

4. #### Can an Interface extend another Interface?

   * An interface can extend multiple interfaces.
   * A single class can also implement multiple interfaces.

5. #### What does the static word mean in Java?

   * static members belong to the class instead of a specific instance.

6. #### Can a static method be overridden in Java?

   * Static methods cannot be overridden because they are not dispatched on the object instance at runtime.

7. #### Can a constructor be inherited?

   * Constructors are not members of classes and only members are inherited.

8. #### Which Design Patterns are you familiar with?

   * Creational patterns
     * Builder
     * Factory
     * Singleton
     * Monostate
     * Fluent Interface Pattern
   * Structural patterns
     * Adapter
     * Decorator
     * Facade
   * Behavioural patterns
     * Chain of responsibility
     * Iterator
     * Strategy

9. #### Which design patterns are used in Android?

   * `View Holder` uses Singleton
   * `Intent` uses Factory
   * `Broadcast Receiver` uses Observer
   * `View` uses Composite
   * Media FrameWork uses Façade
   * `Toast.makeText()` uses Factory

10. #### What is the difference between Composition and Inheritance? How we should decide which one to use?

   * Using **is** vs **has** rule (Cat is an Animal / Person has a Job)

11. #### Do you know SOLID (object-oriented design)?

   * **S**ingle responsibility principle:
     * A class should have only a single responsibility (i.e. only one potential change in the software’s specification should be able to affect the specification of the class
     * a class should have only one single responsibility
     * One chef cannot run the whole restaurant
   * **O**pen/closed principle:
     * A software module/class/method should be open for extension but closed for modification.
     * any software entity should be open for extension but closed for modification.
     * Trying new shoes doesn’t require you to cut your feet off with a saw.
   * **L**iskov substitution principle:
     * Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program
   * **I**nterface segregation principle:
     * Clients should not be forced to depend upon the interfaces that they do not use.
     * many client-specific interfaces are better than one general-purpose interface.
   * **D**ependency inversion principle:
     * Program to an interface, not to an implementation.
     * The high-level module must not depend on the low-level module, but they should depend on abstractions. One should “Depend upon Abstractions. Do not depend upon concretions.
     * You wouldn’t wire a lamp directly to your house.

12. #### Why do we use the builder design pattern? How did Kotlin improve this use case?

   * to avoid multiple implementations of the constructor for setting different fields in a class.

13. #### What is the difference between Abstract Class and Interface?

14. #### What are the types of GoF ([Gang of Four](https://en.wikipedia.org/wiki/Design_Patterns)) design patterns? Provide examples.

   * Creational
   * Structural
   * Behavioral.
