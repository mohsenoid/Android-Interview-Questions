# Android Interview Questions

This repository holds Technical interview questions for the Senior Android Developer position which has been was asked from me or I usually ask from candidates. Feel free to contribute and improve it.


## General questions

1. #### What were your last 3 applications? which was the best? and why?

2. #### What was the most challenging thing you have done in an application?

3. #### Which websites and blogs you use as Android references?
- developer.android
- StackOverflow
- Medium.com
- Android weekly newsletter
- Kotlin weekly newsletter
- Caster.io
- Droidcon.com

4. #### Why do you consider yourself a Senior Developer? Who is a senior developer? What is the definition of being a Senior Developer?
- Being senior is mostly about sharing, your knowledge, experience, time, ...

5. #### Do you do any Documentations?

6. #### What is your most proud Android development?

7. #### What’s your weakness and power in Android development?

8. #### Are you familiar with Agile, SCRUM, Sprint, Jira, Trello, ...?

9. #### What are the aspects of your job that you really enjoy?

10. #### What is GitFlow? do you follow it?


## Object Oriented Programming

1. #### Name some of the characteristics of OOP languages
- Abstraction
- Encapsulation
- Inheritance
- Polymorphism

2. #### Which Design Patterns you are familiar with?
- Singleton
- Builder
- Factory
- Adapter

3. #### Which design patterns are used in Android?
- `View Holder` uses Singleton
- `Intent` uses Factory
- `Broadcast Receiver` uses Observer
- `View` uses Composite
- Media FrameWork uses Façade
- `Toast.makeText()` uses Factory

4. #### What is the difference between Composition and Inheritance? How we should decide which one to use?
Using **is** vs **has** rule

5. #### Do you know SOLID (object-oriented design)?
- **S**ingle responsibility principle:
  - A class should have only a single responsibility (i.e. only one potential change in the software’s specification should be able to affect the specification of the class
  - a class should have only one single responsibility
  - One chef cannot run the whole restaurant
- **O**pen/closed principle:
  - A software module/class/method should be open for extension but closed for modification.
  - any software entity should be open for extension but closed for modification.
  - Trying new shoes doesn’t require you to saw your feet off.
- **L**iskov substitution principle:
  - Objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program
- **I**nterface segregation principle:
  - Clients should not be forced to depend upon the interfaces that they do not use.
  - many client-specific interfaces are better than one general-purpose interface.
- **D**ependency inversion principle:
  - Program to an interface, not to an implementation.
  - The high-level module must not depend on the low-level module, but they should depend on abstractions. one should “Depend upon Abstractions. Do not depend upon concretions.
  - You wouldn’t wire a lamp directly to your house.

6. #### Why we use the builder design pattern? How Kotlin improves this use case?
to avoid multiple implementations of the constructor for setting different fields in a class.

7. #### What is the difference between Abstract Class and Interface?


## Java

1. #### What are the differences between a `SparseArray` and `Hashmap`?
- Sparse arrays can be used to replace hash maps when the key is an Integer or a Long (HashMap <Integer, V>).
- is made to be memory efficient than using the regular HashMap
- It is generally slower than a traditional HashMap

2. #### What are the differences between a `LinkedList` vs `ArrayList`?
- two different implementations of the List interface
- LinkedList implements it with a doubly-linked list.
- ArrayList implements it with a dynamically re-sizing array.
- LinkedList is better for working with stacks mostly, or when working with buffers.
- ArrayList is best for working with indexes.

3. #### What is a Deadlock In java?
Deadlock describes a situation where two or more threads are blocked forever, waiting for each other.

4. #### How we can avoid Deadlocks?
- Breaking circular wait condition: In order to do that, you can make arrangements in the code to impose the ordering on acquisition and release of locks.
- Avoid Nested Locks: This is the most common reason for deadlocks, avoid locking another resource if you already hold one. It’s almost impossible to get a deadlock situation if you are working with only one object lock.
- Lock Only What is Required: You should acquire lock only on the resources you have to work on, if we are only interested in one of its fields, then we should lock only that specific field, not complete object.
- Avoid waiting indefinitely: You can get a deadlock if two threads are waiting for each other to finish indefinitely using thread join. If your thread has to wait for another thread to finish, it’s always best to use join with the maximum time you want to wait for the thread to finish.

5. #### What is the difference between a process and a thread in Java/Android?
- A program in execution is often referred to as Process. A thread is a part of the process.
- A process consists of multiple threads. A thread is the smallest part of the process that can execute concurrently with other threads of the process.
- A process is sometimes referred to as “Task”. A thread is often referred to as a “Lightweight” process.
- A process has its own address space. A thread uses the process’s address space and shares it with the other threads of that process.
- A thread can communicate with other threads (of the same process) directly by using methods like wait(), notify(), notifyAll(). A process can communicate with another process by using inter-process communication (IPC/AIDL).
- New threads are easily created. However, the creation of new processes requires duplication of the parent process.
- Threads have control over the other threads of the same process. A process does not have control over the sibling process, it has control over its child processes only.

6. #### What’s new in the Android 10 (Q) version?
- Foldables screens
- 5G networks
- Smart Reply in notifications
- Dark Theme
- Gesture navigation
- Settings Panels
- Sharing shortcuts
- Privacy for users -> more control over location permission
- Security
- Camera and media -> Dynamic depth for photos
- Connectivity
- ART optimizations

7. #### How do you manipulate strings in Java without creating String garbage?
Using StringBuilder and StringBuffer/StringBuilder

8. #### What is the basic difference between String and StringBuffer?
- The string is an immutable object. StringBuffer is a mutable object.
- StringBuffer is synchronized whereas StringBuilder is not synchronized.

9. #### What is a generic in java?


## َAndroid Foundation

1. #### What’s Android Runtime ( ART ) and Dalvik?
- Android runtime (ART) is the managed runtime used by applications and some system services on Android.
- Dalvik is the predecessor of ART
- ART as the runtime executes the Dalvik Executable format and Dex bytecode specification.

2. #### What is a 9patch image? does it tile or stretch?
9 Patch images are stretchable, repeatable images reduced to their smallest size

3. #### What is the difference between intent , sticky intent , and pending intent?
- intent - is a message-passing mechanism between components of android except for Content Provider
- Sticky Intent - Sticks with Android, for future broadcast listeners
- Pending Intent - Will be used when someone wants to fire an intent in the future and maybe at that time the app is not alive anymore.

4. #### How can we transfer objects between activities?
- Parcelable which is better for Android apps than Serialisable which uses reflection

5. #### What kind of modes of concurrency are in Android?
- Threads
- Async tasks
- Services
- Kotlin Coroutines

6. #### What is the difference between Service & IntentService?
- IntentService is used for short tasks and a Service is for long ones
- IntentService runs in the App process but Service runs in a separate process.

7. #### What are the Android launch modes?
- standard (default): The system always creates a new instance of the activity in the target task and routes the intent to it.
- singleTop: If an instance of the activity already exists at the top of the target task, the system routes the intent to that instance through a call to its onNewIntent() method, rather than creating a new instance of the activity.
- singleTask: The system creates the activity at the root of a new task and routes the intent to it. However, if an instance of the activity already exists, the system routes the intent to the existing instance through a call to its onNewIntent() method, rather than creating a new one.
- singleInstance: Same as "singleTask", except that the system doesn't launch any other activities into the task holding the instance. The activity is always the single and only member of its task.

8. #### Are you familiar with ProGuard?
used for obfuscation

9. #### What is a Broadcast Receiver? What kind of messages it can receive?
- simply respond to broadcast messages from other applications or from the system itself
- must be Created and Registered within manifest or programmatically

10. #### What are the essential building blocks of an Android application?
- Activities: They dictate the UI and handle the user interaction to the smartphone screen.
- Services: They handle background processing associated with an application.
- Broadcast Receivers: They handle communication between Android OS and applications.
- Content Providers: They handle data and database management issues.
- Intents: Communication between the above-mentioned components is through Intents.

11. #### What is the Intent?
- Intents define the intention of an Application. S simple message object which is used to transfer data between activities.
- explicit intent: used to launch a specific application component
- implicit intent: specifies an action that can invoke any app on the device able to perform that action

12. #### What is a Service?
- A Service is an application component that can perform long-running operations in the background and does not provide a user interface.
- a component can bind to a service to interact with it and even perform interprocess communication (IPC) if it is running in a separate process

13. #### How can Activity communicate with services?
- Binding services
- Using Callbacks interfaces

14. #### What is ContentProvider?
- They encapsulate data and provide it to applications through the single ContentResolver interface.
- Used for providing the content between applications
- A content provider is only required if you need to share data between multiple applications.

15. #### What is an Adapter?
- The adapter is an interface whose implementations provide data and the display of that data done by the ListView/RecyclerView.
- ListViews and RecyclerView do not actually contain any data themselves. They are just a UI without data in it.

16. #### What’s the difference between Activity Context and Application Context?
- They are both instances of Context , but the application instance is tied to the lifecycle of the application, while the Activity instance is tied to the lifecycle of the Activity.
- They have access to different information about the application environment.

17. #### Have you used Android annotations (e.g. IntegerRes, IntDef, ...)?

18. #### Like to work on Android app Backend (core) or UI (view)?

19. #### Explain the Activity lifecycle?

20. #### What is a Fragment?

21. #### Do you have any experience with NDK?

22. #### Do you have any experience with Bluetooth and BLE Android API?

23. #### Have you used Canvas in UI?

24. #### What are the ways we can store information in an Android app?


## َAndroid Libraries

1. #### Do you design new libraries for yourself or use others?

2. #### Which Android Libraries are you familiar with?
- Android Jetpack
- Retrofit2
- RxJava / RxAndroid
- Dagger2
- Timber
- Koin
- Picasso / Glide
- Gson

3. #### What is an **ORM**?
- Object-relational mapping is a technique (a.k.a. design pattern) of accessing a
  relational database from an object-oriented language

4. #### Which **ORMs** are you familiar with?
- Room
- DBFlow
- OrmLite
- Realm

5. #### What is RxJava / RxAndroid?
- A library for reactive programming
- Works like wireframe between different layers and creates pipelines of data

6. #### What is the difference between `FlatMap`, `SwitchMap`, `ConcatMap` in RxJava?

7. #### Have you used Mockito?


## Architecture

1. #### Why we should use MVP / MVVM architectures?
- to avoid too much logic code in the UI layer and god activities
- reusable code that's easier to test
- avoid duplicated code between common views
- Easier to maintain
- we can test logic without using instrumentation tests

2. #### Why the View should be implemented with an interface in MVP?
- Because we want to decouple the code from the implementation view.
- We want to abstract the framework used to write our presentation layer, regardless of any external dependency.
- We want to be able to easily change the implementation of view if needed.
- We want to follow the SOLID dependency rule to improve unit testability and in order to follow the dependency rule, high-level concepts (such as the presenter implementation) can't depend on low-level details (like the implementation view).

3. #### What’s the use of interfaces in a presenter?
- following SOLID Dependency inversion principle

4. #### Why do you use dependency injection (DI / Dagger)?
- useful for decoupling the whole system
- allow easier unit testing
- much easier moving things around and keeping classes small and simple
- help wiring different elements together


## Test

1. #### Are you familiar with Unit testing?

2. #### what does Unit Testing suppose to do?
- Unit testing involves breaking your program into pieces and subjecting each piece to a series of tests.
- These tests can run on a Continues Integration (CI) (namely GitHub actions, Circle Ci, or Travis Ci) and keep the code quality


## License

Copyright 2020 Mohsen Mirhoseini Argi

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
