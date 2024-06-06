# Android Interview

![Android Interview - Kotlin Questions](images/kotlin.png)

## Kotlin Programming Questions

1. #### How does Kotlin work on Android?

   Just like Java, the Kotlin code is also compiled into the Java bytecode and is executed at runtime by the Java Virtual Machine i.e. JVM.

2. #### Have you tried Kotlin? Why should we use Kotlin?

   - Kotlin is concise and boilerplate-free (in comparison to Java)
   - Kotlin is null-safe
   - Kotlin is interoperable

3. #### What is the difference between the variable declaration with **var** and **val**?

   If you want to declare some mutable(changeable) variable, then you can use `var`. For the immutable variable, use `val` i.e. `val` variables can't be changed once assigned.

4. #### What is the difference between the variable declaration with val and const?

   Both the variables that are declared with `val` and `const` are immutable in nature. But the value of the `const` variable must be known at the compile-time whereas the value of the `val` variable can be assigned at runtime also.

5. #### How to ensure null safety in Kotlin?

   One of the major advantages of using Kotlin is null safety. In Java, if you access some null variable then you will get a `NullPointerException`. So, the following code in Kotlin will produce a compile-time error:

   ```kotlin
   var name: String = "Some string"
   name = null // compile time error
  ` ``

   So, to assign null values to a variable, you need to declare the `name` variable as a nullable string and then during the access of this variable, you need to use a safe call operator i.e. `?.`

   ```kotlin
   var name: String? = "Some string"
   print(name?.length) // Okay
   name = null // Okay
   ```

6. #### What is the difference between safe calls(?.) and double-bang operator(!!)?

   Safe call operator i.e. `?.` is used to check if the value of the variable is null or not. If it is null then null will be returned otherwise it will return the desired value.

   ```kotlin
   var name: String? = "Some string"
   println(name?.length) // 11
   name = null
   println(name?.length) // null
   ```

   If you want to throw NullPointerException when the value of the variable is null, then you can use the null check or `!!` operator.

   ```kotlin
   var name: String? = "Some string"
   println(name?.length) // 11
   name = null
   println(name!!.length) // throws KotlinNullPointerException
   ```

7. #### Do we have a ternary operator in Kotlin just like Java?

   No, we don't have a ternary operator in Kotlin but you can use the functionality of ternary operator by using if-else or Elvis operator.

8. #### What is Elvis operator in Kotlin?

   In Kotlin, you can assign `null` values to a variable by using the null safety property. To check if a value is having null value then you can use if-else or can use the Elvis operator i.e. `?:` For example:

   ```kotlin
   var name:String? = "Some string"
   val nameLength = name?.length ?: -1
   println(nameLength)
   ```

   The Elvis operator( `?:` ) used above will return the length of name if the value is not null otherwise if the value is null, then it will return `-1`.

9. #### What is a data class in Kotlin?

   Data classes are those classes which are made just to store some data. In Kotlin, it is marked as data. The following is an example of the same:

   ```kotlin
   data class Employee(val name: String, val age: Int)
   ```

   When we mark a class as a *data* class, you don’t have to implement or create the following functions like we do in Java: `hashCode()`, `equals()` , `toString()` , `copy()`. The compiler automatically creates these internally, so it also leads to clean code. However, there are a few other requirements that data classes need to fulfill.

10. #### What is the use of `@JvmStatic`, `@JvmOverloads`, and` @JvmFiled` annotations in Kotlin?

   - `@JvmStatic`: This annotation is used to tell the compiler that the method is a static method and can be used in Java code.
   - `@JvmOverloads`: To use the default values passed as an argument in Kotlin code from the Java code, we need to use the `@JvmOverloads` annotation.
   - `@JvmField`: To access the fields of a Kotlin class from Java code without using any getters and setters, we need to use the `@JvmField` in the Kotlin code.

11. #### Can we use primitive types such as int, double, and float in Kotlin?

    In Kotlin, we can't use primitive types directly. We can use classes like Int, Double, etc. as an object wrapper for primitives. But the compiled bytecode has these primitive types.

12. #### What is String Interpolation in Kotlin?

    If you want to use some variable or perform some operation inside a string then String Interpolation can be used. You can use the `$` sign to use some variable in the string or can perform some operation in between the `{}` sign.

    ```kotlin
    var name = "Mohsen"
    print("Hello! My name is $name")
    ```

13. #### What do you mean by destructuring in Kotlin?

    **Destructuring** is a convenient way of extracting multiple values from data stored in(possibly nested) objects and Arrays. It can be used in locations that receive data (such as the left-hand side of an assignment). Sometimes it is convenient to *destructure* an object into several variables, for example:

    ```kotlin
    val (name, age) = employee
    ```

    Now, we can use name and age independently like below:

    ```kotlin
    println(name)
    println(age)
    ```

14. #### When to use the `lateinit` keyword in Kotlin?

    * `lateinit` is late initialization.
    * Normally, properties declared as having a non-null type must be initialized in the constructor. However, fairly often this is not convenient. Therefore by using `lateinit` developers promises the compiler that they will provide the value before using it for the first time.
    * For example, properties can be initialized through dependency injection, or in the setup method of a unit test. In this case, you cannot supply a non-null initializer in the constructor, but you still want to avoid null checks when referencing the property inside the body of a class. To handle this case, you can mark the property with the lateinit modifier.
    * You can check if the lateinit variable has been initialized or not before using it with the help of `isInitialized` method. This method will return true if the lateinit property has been initialized otherwise it will return false.

15. #### What is the difference between lateinit and lazy in Kotlin?

    - lazy can only be used for val properties, whereas lateinit can only be applied to var because it can’t be compiled to a final field, thus no immutability can be guaranteed.
    - If you want your property to be initialized from outside in a way probably unknown beforehand, use lateinit.

16. #### Is there any difference between == operator and === operator?

    Yes. The `==` operator is used to compare the values stored in variables and the `===` operator is used to check if the reference of the variables are equal or not. But in the case of primitive types, the `===` operator also checks for the value and not reference.

17. #### What is the forEach in Kotlin?

    In Kotlin, to use the functionality of a for-each loop just like in Java, we use a `forEach` function.

18. #### What are companion objects in Kotlin?

    In Kotlin, if you want to write a function or any member of the class that can be called without having the instance of the class then you can write the same as a member of a companion object inside the class.

19. #### What is the equivalent of Java static methods in Kotlin?

    To achieve the functionality similar to Java static methods in Kotlin, we can use:

    - companion object
    - package-level function
    - object

20. #### What is the difference between FlatMap and Map in Kotlin?

    - FlatMap is used to combine all the items of lists into one list.
    - Map is used to transform a list based on certain conditions.

21. #### What is the difference between List and Array types in Kotlin?

    - **Data Structure**: An Array in Kotlin is a class representing a fixed-size collection of elements that can be accessed by their indices. It’s compiled into a JVM array, which is a sequential fixed-size memory region1. A List, on the other hand, is an interface that can have various implementations like ArrayList or LinkedList, each with its own memory representation and operational logic1.
    - **Mutability**: Arrays are inherently mutable, meaning you can modify their elements. However, their size is fixed once initialized. Lists come in two flavors: List (immutable) and MutableList (mutable). The List interface provides read-only operations, while MutableList allows for adding, removing, and updating its elements12.
    - **Generic Variance**: Arrays are invariant, meaning an Array<Int> is not assignable to an Array<Number>. In contrast, List is covariant, so a List<Int> can be treated as a List<Number>1.
    - **Primitive Types Optimization**: Kotlin provides specialized classes for arrays of primitive types like IntArray, DoubleArray, etc., which avoid boxing overhead and are mapped to Java’s primitive arrays. Lists do not have such specialized implementations for primitives1.

22. #### What are visibility modifiers in Kotlin?

    A visibility modifier or access specifier or access modifier is a concept that is used to define the scope of something in a programming language. In Kotlin, we have four visibility modifiers:

    - **private**: visible inside that particular class or file containing the declaration.
    - **protected**: visible inside that particular class or file and also in the subclass of that particular class where it is declared.
    - **internal**: visible everywhere in that particular module.
    - **public** (default modifier in Kotlin): visible to everyone

23. #### What are init blocks in Kotlin?

    `init` blocks are initializer blocks that are executed just after the execution of the primary constructor. A class file can have one or more init blocks that will be executed in series. If you want to perform some operation in the primary constructor, then it is not possible in Kotlin, for that, you need to use the `init` block.

24. #### What are the types of constructors in Kotlin?

    - **Primary constructor:** These constructors are defined in the class header and you can't perform some operation in it, unlike Java's constructor.
    - **Secondary constructor:** These constructors are declared inside the class body by using the constructor keyword. You must call the primary constructor from the secondary constructor explicitly. Also, the property of the class can’t be declared inside the secondary constructor. There can be more than one secondary constructors in Kotlin.

25. #### What are Coroutines in Kotlin?

    A framework to manage concurrency in a more performant and simple way with its lightweight thread which is written on top of the actual threading framework to get the most out of it by taking the advantage of cooperative nature of functions.

26. #### What is suspend function in Kotlin Coroutines?

    The suspend function is the building block of the Coroutines in Kotlin. The suspend function is a function that can be started, paused, and resumed. To use a suspend function, we need to use the `suspend` keyword in our normal function definition.

27. #### What is the difference between Launch and Async in Kotlin Coroutines?

    The difference is that the `launch{}` does not return anything and the `async{}` returns an instance of `Deferred<T>`, which has an `await()` function that returns the result of the coroutine like we have future in Java in which we do `future.get()` to the get the result.

    In other words:

    - launch: fire and forget
    - async: perform a task and return a result

28. #### What are scopes in Kotlin Coroutines?

    - Scopes in Kotlin Coroutines are very useful because we need to cancel the background task as soon as the activity is destroyed. Here, we will learn how to use scopes to handle these types of situations.
    - In Android-specific projects, we should go with the custom scopes created by considering the LifeCycle of Activity, ViewModel, etc.
    - The scopes are present under the Kotlin extension libraries. Make sure to add the required dependencies to your project.

29. #### How Exception Handling is done in Kotlin Coroutines?

    - One way is to use a try-catch block

    - Another way is to use a CoroutineExceptionHandler

      ```kotlin
      val handler = CoroutineExceptionHandler { _, exception ->
          Log.d(TAG, "$exception handled!")
      }
      GlobalScope.launch(Dispatchers.Main + handler) {
          fetchUserAndSaveInDatabase() // do on IO thread and back to UI Thread
      }
      ```

    - While **NOT** using `async`, we can go ahead with the `try-catch` or the `CoroutineExceptionHandler` and achieve anything based on our use cases.

    - While using `async`, in addition to `try-catch`, we have two options: `coroutineScope` and `supervisorScope`.

    - With `async`, use `supervisorScope` with the individual `try-catch` for each task, when you want to continue with other tasks if one or some of them have failed.

    - With `async`, use `coroutineScope` with the top-level `try-catch`, when you do **NOT** want to continue with other tasks if any of them have failed.

30. #### What is the open keyword in Kotlin used for?

    By default, the classes and functions are final in Kotlin. So, you can't inherit the class or override the functions. To do so, you need to use the open keyword before the class and function.

31. #### What are lambdas expressions?

    Lambdas expressions are anonymous functions that can be treated as values i.e. we can pass the lambdas expressions as arguments to a function return them, or do any other thing we could do with a normal object.

32. #### What are Higher-Order functions in Kotlin?

    A higher-order function is a function that takes functions as parameters or returns a function. For example, A function can take functions as parameters.

    ```kotlin
    fun passMeFunction(abc: () -> Unit) {
     // I can take function
     // do something here
     // execute the function
     abc()
    }
    ```

    For example, A function can return another function.

    ```kotlin
    fun add(a: Int, b: Int): Int {
     return a + b
    }
    ```

    And, we have a function **returnMeAddFunction** which takes zero parameters and returns a function of the type **((Int, Int) -> Int)** .

    ```kotlin
    fun returnMeAddFunction(): ((Int, Int) -> Int) {
     // can do something and return function as well
     // returning function
     return ::add
    }
    ```

    And to call the above function, we can do:

    ```kotlin
    val add = returnMeAddFunction()
    val result = add(2, 2)
    ```

33. #### What are extension functions in Kotlin?

    Extension functions are like extensive properties attached to any class in Kotlin. By using extension functions, you can add some methods or functionalities to an existing class even without inheriting the class. For example: Let's say, we have views where we need to play with the visibility of the views. So, we can create an extension function for views like,

    ```kotlin
    fun View.show() {
     this.visibility = View.VISIBLE
    }
    
    fun View.hide() {
     this.visibility = View.GONE
    }
    ```

    and to use it we use, like,

    ```kotlin
    toolbar.hide()
    ```

34. #### What is an infix function in Kotlin?

    An infix function is used to call the function without using any bracket or parenthesis. You need to use the infix keyword to use the infix function.

    ```java
    class Operations {
     var x = 10; 
     infix fun minus(num: Int) {
     	this.x = this.x - num
     } 
    }
    fun main() {
     val opr = Operations()
     opr minus 8
     print(opr.x)
    }
    ```

35. #### What is an inline function in Kotlin?

    Inline function instruct compiler to insert complete body of the function wherever that function got used in the code. To use an Inline function, all you need to do is just add an inline keyword at the beginning of the function declaration.

36. #### What is noinline in Kotlin?

    While using an inline function and want to pass some lambda function and not all lambda function as inline, then you can explicitly tell the compiler which lambda it shouldn't inline.

    ```java
    inline fun doSomethingElse(abc: () -> Unit, noinline xyz: () -> Unit) {
     abc()
     xyz()
    }
    ```

37. #### What are Reified types in Kotlin?

    When you are using the concept of Generics to pass some class as a parameter to some function and you need to access the type of that class, then you need to use the reified keyword in Kotlin.

    For example:

    ```java
    inline fun <reified T> genericsExample(value: T) {
     println(value)
     println("Type of T: ${T::class.java}")
    }
    fun main() {
     genericsExample<String>("Learning Generics!")
     genericsExample<Int>(100)
    }
    ```

38. #### Explain the use-case of let, run, with, also, apply in Kotlin.

39. #### What are pair and triple in Kotlin?

    Pair and Triples are used to return two and three values respectively from a function and the returned values can be of the same data type or different.

    ```java
    val pair = Pair("My Age: ", 36)
    print(pair.first + pair.second)
    ```

40. #### What are labels in Kotlin?

    Any expression written in Kotlin is called a label. For example, if we have a *for-loop* in our Kotlin code then we can name that *for-loop* expression as a label and will use the label name for the *for-loop* .

    We can create a label by using an identifier followed by the `@ `sign. For example, `name@ `, `loop@ `, `xyz@ `, etc. The following is an example of a label:

    ```kotlin
    loop@ for (i in 1..10) {
     // some code goes here
    }
    ```

    The name of the above for-loop is `loop `

41. #### What are the benefits of using a Sealed Class over Enum?

    - Sealed Classes are also called power Enums
    - Sealed classes give us the flexibility of having **different** **types of subclasses and also containing the state**. The important point to be noted here is the subclasses that are extending the Sealed classes should be either nested classes of the Sealed class or should be declared in the same file as that of the Sealed class.

42. #### What are collections in Kotlin?
