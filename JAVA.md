# Android Interview
![Android Interview - Java Questions](images/java.png)

## Java Programming Questions
1. #### Why is Java said to be platform-independent?

   - **WORA**: “write once, run anywhere”.
   - Java code compiles into _bytecode_ that can run on any device equipped with a _Java Virtual Machine (JVM)_ independent from the OS.

2. #### What are the differences between the Android `SparseArray` and Java `Hashmap`?

   * Sparse arrays can be used to replace hash maps when the key is an Integer or a Long (similar to HashMap <Integer, V>).
   * It Is made to be more memory efficient than using the regular HashMap.
   * It is generally slower than a traditional HashMap.

3. #### What are the differences between a `LinkedList` vs `ArrayList`?
   * two different implementations of the List interface
   * LinkedList implements it with a doubly-linked list.
   * ArrayList implements it with a dynamically re-sizing array.
   * LinkedList is better for working with stacks mostly, or when working with buffers.
   * ArrayList is best for working with indexes.

4. #### What is the difference between HashSet, HashMap, and Hashtable? How do they behave in a multi-threaded environment?

   - ##### Hashtable

   Hashtable is a data structure to retain values of key-value pairs.

   - It does not allow null for both key and value. It will throw NullPointerException.
   - Hashtable does not maintain insertion order. The order is defined by the Hash function. So only use this if you do not need data in order.
   - It is synchronized. It is slow. Only one thread can access in one time.
   - HashTable rea thread safe.
   - HashTable uses Enumerator to iterate through elements.

   ```java
   Hashtable<Integer,String>; myTable = new Hashtable<Integer,String>();
   
   myTable.put(1, "John");
   myTable.put(2, "Cena");
   myTable.put(3, null); /* NullPointerEcxeption at runtime*/
   
   System.out.println(myTable.get(1));
   System.out.println(myTable.get(2));
   System.out.println(myTable.get(3));
   ```

   - ##### HashMap

     Like Hashtable it also accepts key-value pairs.

     - It allows null for both key and value.
     - HashMap does not maintain insertion order. The order is defined by the Hash function.
     - It is not synchronized. It will have better performance.
     - HashMap are not thread safe, but you can use Collections.synchronizedMap(new HashMap<K,V>())

   ```java
     HashMap<Integer,String> myMap = new HashMap<Integer,String>();
     
     myMap.put(1, "First");
     myMap.put(2,"Second");
     myMap.put(3, null);
   ```

   - ##### HashSet

     HashSet does not allow duplicate values.

     - It provides add method rather put method.
     - You also use its contain method to check whether the object is already available in HashSet. HashSet can be used where you want to maintain a unique list.

   ```java
     HashSet<String> mySet = new HashSet<String>();
     
     mySet.add ("First");
     mySet.add ("Second");
     mySet.add ("Third");
     
     if(mySet.contains("First")){
     	System.out.println("The Set already contains First");
     }
   ```

5. #### What is a Deadlock In java?
   * Deadlock describes a situation where two or more threads are blocked forever, waiting for each other.

6. #### How we can avoid Deadlocks?
   * Breaking circular wait condition: In order to do that, you can make arrangements in the code to impose the ordering on acquisition and release of locks.
   * Avoid Nested Locks: This is the most common reason for deadlocks, avoid locking another resource if you already hold one. It’s almost impossible to get a deadlock situation if you are working with only one object lock.
   * Lock Only What is Required: You should acquire lock only on the resources you have to work on, if we are only interested in one of its fields, then we should lock only that specific field, not complete object.
   * Avoid waiting indefinitely: You can get a deadlock if two threads are waiting for each other to finish indefinitely using thread join. If your thread has to wait for another thread to finish, it’s always best to use join with the maximum time you want to wait for the thread to finish.

7. #### How do you manipulate strings in Java without creating String garbage?
   * Using StringBuilder and StringBuffer/StringBuilder

8. #### What is the basic difference between String and StringBuffer?
   * The string is an immutable object. StringBuffer is a mutable object.
   * StringBuffer is synchronized whereas StringBuilder is not synchronized.

9. #### What is a generic in java?
   * Stronger type checks at compile time. A Java compiler applies strong type checking to generic code and issues errors if the code violates type safety.

10. #### Why should the equals() and hashCode() methods often be overridden together?

11. #### In Java, does the finally block gets executed if we insert a return statement inside the try block of a try-catch-finally?
   * Yes!

12. #### Explain method overloading & overriding.

13. #### What is Java's Garbage Collection and how does it help you as a developer? Can two objects be garbage collected if they reference to each other?
   *  Cyclic dependencies without any live external reference are also eligible for GC.

14. #### Why are Array and ArrayList different? When would you use each?
   * Resizable: Array is static in size that is fixed length data structure, One can not change the length after creating the Array object. ArrayList is dynamic in size.
   * Multi-dimensional: Array can be multi dimensional , while ArrayList is always single-dimensional.
   * Primitives:  ArrayList can not contains primitive data types (like int , float , double) it can only contains Object while Array can contain both primitive data types as well as objects.

15. #### What is a `ThreadPool`? Is it better than using several "simple" `Thread`s?
   * ThreadPool: represents a group of worker threads that are waiting for the job and reuse many times.
   * Using ThreadPool minimizes the overhead due to thread creation. Thread objects use a significant amount of memory, and in a large-scale application, allocating and deallocating many thread objects creates a significant memory management overhead.

16. #### What are strong, soft, and weak references in Java?
   * Strong Reference: is the default Reference Object of a type/class
   * Weak Reference: When an object in memory is reachable only by Weak Reference Objects, it becomes automatically eligible for GC.
   * Soft Reference: Object is basically a weak Reference Object that remains in memory a bit more: normally, it resists the GC cycle until memory is available and there is no risk of OutOfMemoryError

17. #### What does the keyword synchronized mean?
   * synchronized: is one of the tools that make your code thread-safe.
   * synchronized methods can't be called in the same time from multiple threads.

18. #### What are `transient` and `volatile` modifiers?
   * transient: modifier tells the Java object serialization subsystem to exclude the field when serializing an instance of the class
   * volatile: modifier tells the JVM that writes to the field should always be synchronously flushed to memory, and that reads of the field should always read from memory.

19. #### How to implement thread-safe counter.
   * Use AtomicInteger.

20. #### What are the states of Thread in Java?
   * New, Runnable, Blocked, Waiting, TimedWaiting, Terminated.

21. #### How to make object thread-safe without synchronisation?
   * **Immutable Objects**: If an object doesn’t have any mutable state, it’s inherently thread-safe. Once created, its state cannot change, so there’s no need for synchronization.
   * **Thread-Local Storage**: Use ThreadLocal variables when you need to maintain state that is unique to a thread. This way, each thread has its own instance of a variable, and no synchronization is needed.
   * **Concurrent Collections**: Utilize the concurrent collections from the java.util.concurrent package, such as ConcurrentHashMap, which are designed to handle concurrent access without explicit synchronization.
   * **Atomic Variables**: Use atomic variables from the java.util.concurrent.atomic package, like AtomicInteger or AtomicReference, which provide methods that are thread-safe without synchronization.
   * **Volatile Fields**: Declare fields as volatile to ensure that every thread sees the most recent write to the field. However, note that volatile only guarantees visibility, not atomicity.
   * **Coroutines** (Kotlin Specific): In Kotlin, you can use coroutines with shared mutable state carefully, employing mechanisms like Mutex for mutual exclusion without traditional locking.
   * **UI Thread** (Android Specific): For Android, use methods like Activity.runOnUiThread(Runnable) or View.post(Runnable) to perform actions on the UI thread safely.

22. #### Explain how wait/notify mechanism works.

23. #### Describe the implementation of HashMap. What is collision? Difference between HashSet and TreeSet?

24. #### Whether static method can use nonstatic members?
- NO

25. #### Do objects get passed by reference or value in Java?
   * In Java all primitives and objects are passed by value, meaning that their copy will be manipulated in the receiving method. But there is a caveat - when you pass an object reference into a method, a copy of this reference is made, so it still points to the same object! This means, that any changes that you make inside this object are retained, when the method exits.

26. #### What is the difference between instantiation and initialization of an object?
   * Initialization: is the process of the memory allocation, when a new variable is created.
   * Instantiation: is the process of explicitly assigning definitive value to a declared variable.

27. #### What is GC (garbage collector)? How does it work?
   * All objects are allocated on the heap area managed by the JVM. As long as an object is being referenced, the JVM considers it alive. Once an object is no longer referenced and therefore is not reachable by the application code, the garbage collector removes it and reclaims the unused memory.

28. #### What is volatile modifier?
   * The Java volatile keyword is used to mark a Java variable as "being stored in main memory", and not from the CPU cache.

29. #### What is `transient` modifier?
   * keyword is used in serialization. If you define any data member as transient, it will not be serialized.
