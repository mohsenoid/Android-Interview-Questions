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

   * `public` (by default in Kotlin): is widely used on classes, variables, constructors, and methods to grant access from any class and method anywhere.
   * `private` (by default in Java): variables, methods, constructors, or inner classes are only visible to its' containing class and its' methods.
   * `protected`: can be used on variables, methods, and constructors therefore allowing access only to subclasses and classes that are inside the same package as protected members' class.
   * `internal` (just Kotlin): means that any client inside this module who sees the declaring class sees its internal members.

3. #### What is the difference between overriding and overloading a method in Java?

   * Overload: is one method with different signatures and input parameters
   * @Override: occurs when a subclass (child class) has the same method or property as the parent class

4. #### Can an Interface/Class extend another/multiple Interfaces?

   * An interface can extend multiple interfaces.
   * A single class can implement multiple interfaces, but only one abstract class.

5. #### What does the static word mean in Java?

   * static members belong to the class instead of a specific instance.

6. #### Can a static method be overridden in Java?

   * Static methods cannot be overridden because they are not dispatched on the object instance at runtime.

7. #### Can a constructor be inherited?

   * Constructors are not members of classes and only members are inherited.

8. #### What are the types of GoF ([Gang of Four](https://en.wikipedia.org/wiki/Design_Patterns)) design patterns? Provide examples.

   * Creational
   * Structural
   * Behavioral

9. #### Which Design Patterns are you familiar with?

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
     * Observer
     * Strategy
   * More to read: https://refactoring.guru/design-patterns

10. #### Which design patterns are used in Android?

   * `View Holder` uses Singleton
   * `Intent` or `Toast.makeText()` uses Factory
   * `Broadcast Receiver` uses Observer
   * `View` uses Composite
   * Media FrameWork uses Façade
   * `Adapter` uses adapter

11. #### What is the difference between Composition and Inheritance? How should we decide which one to use?

   * **Composition** is a design principle where a class is composed of one or more objects of other classes, signifying a “has-a” relationship
   * **Inheritance** is a mechanism where a class extends another class, representing an “is-a” relationship
   * Using the **is-a** vs **has-a** rule, we can determine which one to use. For example: a cat is an animal, but a person has a job.

12. #### Do you know SOLID software programming design principles?

   * **S**ingle Responsibility Principle:
     * A class should have only a single responsibility (i.e. only one potential change in the software’s specification should be able to affect the specification of the class
     * One chef cannot run the whole restaurant!

<img src="assets\SOLID\S.jpg" alt="Single Responsibility Principle" style="width:400px;" />

   * **O**pen / Closed Principle:
     
     * Any software entity (module/class/method) should be open for extension but closed for modification.
     * Trying new shoes doesn’t require you to saw your feet off!

<img src="assets\SOLID\O.jpg" alt="Open / Closed Principle" style="width:400px;" />

   * **L**iskov Substitution Principle:
     * Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program

<img src="assets\SOLID\L.jpg" alt="Liskov Substitution Principle" style="width:400px;" />

   * **I**nterface Segregation Principle:
     * Clients should not be forced to depend upon the interfaces that they do not use.
     * Many client-specific interfaces are better than one general-purpose interface.

<img src="assets\SOLID\I.jpg" alt="Interface Segregation Principle" style="width:400px;" />

   * **D**ependency Inversion Principle:
     * The high-level module must not depend on the low-level module, but they should depend on abstractions. One should “Depend upon Abstractions. Do not depend upon concretions.
     * Program to an interface, not to an implementation.
     * You wouldn’t wire a lamp directly to your house!

<img src="assets\SOLID\D.jpg" alt="Dependency Inversion Principle" style="width:400px;" />

13. #### Why do we use the builder design pattern? How did Kotlin improve this use case?

   * To avoid the constructor's multiple implementations for setting different fields in a class having many properties.

14. #### What is the difference between Abstract Class and Interface?
