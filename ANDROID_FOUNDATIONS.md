# Android Interview
![Android Interview - Foundations](images/foundations.png)

## Android Foundations

From basic to advanced concepts, these Android questions will test your fundamental knowledge.

- [General](#General)
- [Activity](#Activity)
- [Fragment](#Fragment)
- [Service](#Service)
- [Intent](#Intent)
- [BroadcastReceiver](#BroadcastReceiver)
- [ContentProvider](#ContentProvider)

### General

1. #### What’s new in the latest Android version?

2. #### What is ADB (Android Debug Bridge)?

3. #### What is ANR (Application not responding)?

4. #### What are Android Runtime (ART) and Dalvik?

    Android Runtime (ART) and Dalvik are both execution environments for running Android applications, but they have some key differences:

    - **Dalvik**: It was the default runtime environment used by Android devices up until version 4.4 KitKat. Dalvik utilizes a Just-In-Time (JIT) compiler, which means it compiles the code at runtime, as needed. This approach is efficient in terms of memory usage because only the parts of the code that are needed are compiled.
    - **ART**: Introduced as an experimental feature in KitKat and later becoming the default runtime in Android 5.0 Lollipop, ART uses an Ahead-Of-Time (AOT) compiler. With AOT, the entire application code is compiled during installation, which improves app performance, especially startup times, because the code is already compiled to native instructions that the device’s CPU can execute directly.
      

    Here are some of the features and differences between ART and Dalvik:

    - **Compilation Approach**:
      - **Dalvik** compiles only the necessary parts of the code at runtime (JIT).
      - **ART** compiles the entire application code at install time (AOT).
      
    - **Performance**:
      - **Dalvik** may experience lag during execution as it compiles code on the fly.
      - **ART** provides faster execution of applications due to pre-compilation.
      
    - **Storage and Booting Time**:
      - **Dalvik** has a smaller memory footprint and boots faster compared to ART.
      - **ART** requires more storage space because it compiles the entire code during installation.
      
    - **Battery Performance and Garbage Collection**:
      - **ART** improves battery performance and has better garbage collection capabilities, leading to improved memory management

    Both ART and Dalvik are compatible with running DEX (Dalvik Executable) bytecode, which is the format Android apps are compiled into. This means apps developed for Dalvik should generally work when running with ART, although some techniques that work on Dalvik do not work on ART.

5. #### What is Context? What is the difference between Application Context and Activity Context?

    A **Context** is a handle to the system; it provides services like resolving resources, obtaining access to databases and preferences, and so on.

    - **Application Context**: This context is tied to the lifecycle of an application. The application context can be used where you need a context whose lifecycle is separate from the current context or when you are passing a context beyond the scope of an activity.
    - **Activity Context**: This context is available in an activity. This context is tied to the lifecycle of an activity. The activity context should be used when you are passing the context in the scope of an activity or you need the context whose lifecycle is attached to the current context.

6. #### What are Android App components?

    App components are the essential building blocks of an Android app. Each component is an entry point through which the system or a user can enter your app. Some components depend on others.
    
    There are different types of app components:
    
      - **Activities**: They dictate the UI and handle the user interaction with the smartphone screen.
      - **Services**: They handle background processing associated with an application.
      - **Broadcast Receivers**: They handle communication between Android OS and applications.
      - **Content Providers**: They handle data and database management issues.
      - **Intents**: Communication between the above-mentioned components is through Intents.

7. #### What are the Android launch modes?

   - **standard (default)**: The system always creates a new instance of the activity in the target task and routes the intent to it.
   - **singleTop**: If an instance of the activity already exists at the top of the target task, the system routes the intent to that instance through a call to its `onNewIntent()` method, rather than creating a new instance of the activity.
   - **singleTask**: The system creates the activity at the root of a new task and routes the intent to it. However, if an instance of the activity already exists, the system routes the intent to the existing instance through a call to its `onNewIntent()` method, rather than creating a new one.
   - **singleInstance**: Same as "singleTask", except that the system doesn't launch any other activities into the task holding the instance. The activity is always the single and only member of its task.

8. #### How to prevent the data from reloading and resetting when the screen is rotated?

    The most basic approach would be to use a combination of **ViewModels** and `onSaveInstanceState()`. (The potential next question is: How do we do that?)
    
    - Basics of `ViewModel`: A ViewModel is **LifeCycle-Aware.** In other words, a ViewModel will not be destroyed if its owner is destroyed for a configuration change (e.g. rotation). The new instance of the owner will just be re-connected to the existing ViewModel. So if you rotate an Activity three times, you have just created three different Activity instances, but you only have one ViewModel. So the common practice is to store data in the ViewModel class (since it persists data during configuration changes).
    - Using the `OnSaveInstanceState` to store small amounts of UI data. For instance, let’s say we have a search screen and the user has entered a query in the Edittext. This results in a list of items being displayed in the RecyclerView. Now if the screen is rotated, the ideal way to prevent resetting of data would be to store the list of search items in the ViewModel and the query text the user has entered in the OnSaveInstanceState method of the activity.

9. #### What is the difference between `Serializable` and `Parcelable`? Which is the best approach in Android?

   - **Serialization**
       - is the process of converting an object into a stream of bytes to store an object in memory, so that it can be recreated at a later time, while still keeping the object’s original state and data.
       - The problem with this approach is that reflection is used and it is a slow process and therefore is not efficient.
   - **Serializable**
       - is an Android-specific interface where you implement the serialization yourself.
       - It was created to be far more efficient than Serializable.

10. #### How to disallow serialization?
    We can declare the variable as `transient`.

11. #### What kind of modes of concurrency are in Android?
   - Threads
   - Async tasks
   - Services
   - Kotlin Coroutines

12. #### Are you familiar with ProGuard/DexGuard/R8 Minification?

    ProGuard, DexGuard, and R8 are tools used in Android development to optimize and protect the application code. Here’s a brief overview of each:

    - **ProGuard**: It is an open-source tool that shrinks, optimizes, and obfuscates Java code. It removes unused code and resources, making the APK smaller. ProGuard also makes the code more difficult to reverse-engineer by renaming classes, fields, and methods with non-descriptive names.
    - **DexGuard**: A commercial tool that offers more advanced protection features than ProGuard. It provides stronger encryption and obfuscation techniques, and it can also protect against static and dynamic analysis, making it harder for attackers to tamper with or reverse-engineer the application.
    - **R8**: The latest official code shrinker and minifier from Google, which is integrated into Android Studio. R8 combines shrinking, desugaring, dexing, and obfuscation into one step. It’s designed to be backward-compatible with ProGuard, meaning it can use ProGuard configuration files. R8 improves build times and results in smaller APK sizes compared to ProGuard.

13. #### What is the difference between a process and a thread?

    - **Process**:
        - Runs in its own instance of the virtual machine.
        - Contains components like activities, services, and broadcast receivers.
        - Can be specified to run certain components in separate processes via `AndroidManifest.xml`.
        - Managed by the Android system, which may shut down processes to conserve resources.
        - Each process is isolated from others, ensuring that one process does not interfere with another.

    - **Thread**:
        - The smallest unit of execution within a process.
        - The main thread handles UI and event dispatching.
        - Additional threads can be created for background work.
        - Threads within the same process share the same memory space

14. #### What is the difference between a process and a task?

    - A **process** is about the execution and management of resources at the system level.
    - A **task** is about the user’s journey through a sequence of activities within or across applications.

15. #### What is an Adapter?
   * The adapter is an interface whose implementations provide data and the display of that data done by the ListView/RecyclerView.
   * ListViews and RecyclerView do not actually contain any data themselves. They are just a UI without data in it.

16. #### Have you used Android annotations (e.g. IntegerRes, IntDef, ...)?

17. #### What is a Fragment?

18. #### Do you have any experience with NDK?

19. #### Do you have any experience with Bluetooth and BLE Android API?

20. #### What are the ways we can store information in an Android app?

21. #### Why should you avoid to run non-UI code on the main thread?

22. #### What do you use `SharedPreferences`/`database` for? Why? Do you encrypt anything you store? How?

23. #### What is memory leak. How to test app for memory leaks.

24. #### What is the difference or relation between Looper, Handler, and MessageQueue in Android?

    **Looper**, **Handler**, and **MessageQueue** work together to manage tasks in a thread.

    Here’s a brief overview of each and how they differ:

    - **Looper**: A Looper is responsible for keeping a thread alive, looping through a MessageQueue, and dispatching messages to the corresponding Handler to process. It transforms a normal thread into a message loop, allowing it to handle messages until the application is running.
    - **Handler**: This is a utility class that interacts with a Looper. It posts messages and Runnable objects to the MessageQueue associated with the Looper. Handlers are used to schedule messages and runnables to be executed at some point in the future; they can also enqueue an action to be performed on a different thread than your own.
    - **MessageQueue**: It’s a queue that holds tasks called messages which should be processed. Each Looper has its own MessageQueue that it polls, and when a task is available, it’s sent to the Handler for execution.

---

### Activity

1. #### Explain the Activity Lifecycle?

   ![Android Activity Lifecycle](images/activity_lifecycle.png)

2. #### Explain how two activity lifecycle triggers when switching

   ![Two Android Activity Lifecycle](images/two_activity_lifecycle.png)

3. Explain how two activity lifecycle trigger when config change happens

   ![Two Android Activity Config Change Lifecycle](images/two_activity_lifecycle_config_change.png)

4. #### We have 3 Activities (A, B, and C which is transparent) explain what is the sequence of lifecycle methods execution if we 1) go from A to B, 2) then B to C, 3) Rotate the phone, 4) press back to B, 5) press back to A!!?

5. #### `onSavedInstanceState()` and `onRestoreInstanceState()` in activity?**

   - `onSaveInstanceState()` - a callback method that is used to store data before stopping the activity.
   - `OnRestoreInstanceState()` - When an activity is recreated after it was previously destroyed, we can recover the saved state from the Bundle that the system passes to the activity. Both the `onCreate()` and `onRestoreInstanceState()` callback methods receive the same Bundle that contains the instance state information. But because the `onCreate()` method is called whether the system is creating a new instance of your activity or recreating a previous one, you must check whether the state Bundle is `null` before you attempt to read it. If it is null, then the system is creating a new instance of the activity, instead of restoring a previous one that was destroyed.

6. #### On which activity lifecycle step the activity is visible on the screen?

   - `onStart()`: Called when the activity is becoming visible to the user.
   - `onResume()`: Called when the activity will start interacting with the user. At this point, your activity is at the top of the activity stack, with user input going to it.

7. #### How does the activity respond when the user rotates the screen?

   - When the screen is rotated, the current instance of the activity is destroyed a new instance of the Activity is created in the new orientation. The `onRestart()` method is invoked first when a screen is rotated. The other lifecycle methods get invoked in the same flow as they were when the activity was first created.

8. #### How can we transfer objects between activities?

   * Parcelable which is better for Android apps than Serializable which uses reflection

9. #### What’s the difference between commit() and apply() in SharedPreferences?

   - `commit()`: writes the data synchronously and returns a boolean value of success or failure depending on the result immediately.
   - `apply()`: is asynchronous and it won’t return any boolean response. Also if there is an apply() outstanding and we perform another commit(). The commit() will be blocked until the apply() is not completed.

---

## Fragment

1. #### Explain the Fragment Lifecycle?

   ![Android Fragment Lifecycle](images/fragment_lifecycle.png)

2. #### Why is it recommended to use only the default constructor to create a `Fragment`?

   - When the system restores a fragment (e.g on config change), it will automatically restore your bundle. This way you are guaranteed to restore the state of the fragment correctly to the same state the fragment was initialised with.

3. #### Difference between adding/replacing fragment in backstack?

   - **replace** *removes the existing fragment and adds a new fragment. This means when you press back button the fragment that got replaced will be created with its onCreateView being invoked.*

   - **add** *retains the existing fragments and adds a new fragment that means existing fragment will be active and they wont be in ‘paused’ state hence when a back button is pressed onCreateView is not called for the existing fragment(the fragment which was there before new fragment was added).*

   - *In terms of fragment’s life cycle events `onPause`, `onResume`, `onCreateView` and other life cycle events will be invoked in case of replace but they wont be invoked in case of add.*


4. #### What are the differences between `FragmentPagerAdapter` vs `FragmentStatePagerAdapter`?
  - `FragmentPagerAdapter`: the fragment of each page the user visits will be stored in memory, although the view will be destroyed. So when the page is visible again, the view will be recreated but the fragment instance is not recreated. This can result in a significant amount of memory being used. FragmentPagerAdapter should be used when we need to store the whole fragment in memory. FragmentPagerAdapter calls detach(Fragment) on the transaction instead of remove(Fragment).
  - `FragmentStatePagerAdapter`: the fragment instance is destroyed when it is not visible to the User, except the saved state of the fragment. This results in using only a small amount of Memory and can be useful for handling larger data sets. Should be used when we have to use dynamic fragments, like fragments with widgets, as their data could be stored in the savedInstanceState.Also it won’t affect the performance even if there are large number of fragments.

5. #### What is the difference between Dialog & DialogFragment?

   - Dialogs are entirely dependent on Activities. If the screen is rotated, the dialog is dismissed. Dialog fragments take care of orientation, configuration changes as well.

---


### Service

1. #### What is a Service?
   * A Service is an application component that can perform long-running operations in the background and does not provide a user interface.
   * a component can bind to a service to interact with it and even perform interprocess communication (IPC) if it is running in a separate process

2. #### What is the difference between `Service` & `IntentService`?
   * **IntentService** is used for short tasks and a **Service** is for long ones
   * **IntentService** runs in the App process but **Service** can(!) run in a separate process.

3. #### How can Activity communicate with services?
   * Binding services
   * Using Callbacks interfaces

---


### Intent

1. #### What is Intent? What are two types of Intent?

   - Intents define the intention of an Application.
   - A simple message object which is used to transfer data between activities.
   
2. #### What are two types of Intent?
   
   - **explicit intent**: used to launch a specific application component

     ```kotlin
     val intent = Intent(getApplicationContext(), ActivityTwo::class.java)
     startActivity(intent)
     ```

   
   - **implicit intent**: specifies an action that can invoke any app on the device able to perform that action

     ```kotlin
     val intent = Intent(Intent.ACTION_VIEW)
     intent.setData(Uri.parse("https://google.com"))
     startActivity(intent)
     ```

3. #### What is the difference between `intent`, `sticky intent`, and `pending intent`?

   * **intent**: is a message-passing mechanism between components of Android except for Content Provider
   * **sticky intent**: Sticks with Android, for future broadcast listeners
   * **pending intent**: Will be used when someone wants to fire an intent in the future and maybe at that time the app is not alive anymore.

4. #### What is the size of the Bundle in Android? What can happen if a large amount of data is passed inside Intents?
   * ~500kb
   * TransactionTooLargeException may be thrown by the system.

---


### BroadcastReceiver

1. #### What is a Broadcast Receiver? What kind of messages it can receive?
   * simply respond to broadcast messages from other applications or from the system itself
   * must be Created and Registered within manifest or programmatically

---

### ContentProvider

1. #### What is ContentProvider?
   * They encapsulate data and provide it to applications through the single ContentResolver interface.
   * Used for providing the content between applications
   * A content provider is only required if you need to share data between multiple applications.
