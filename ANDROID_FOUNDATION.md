# Android Interview Questions
![Android Interview Questions](icon.png)

## Android Foundation
1. #### What is ADB (Android Debug Bridge)?

2. #### What is ANR (Application not responding)?

3. #### What’s Android Runtime (ART) and Dalvik?
   * Android runtime (ART) is the managed runtime used by applications and some system services on Android.
   * Dalvik is the predecessor of ART
   * ART as the runtime executes the Dalvik Executable format and Dex bytecode specification.

4. #### What is the difference between `intent` , `sticky intent` , and `pending intent`?
   * intent: is a message-passing mechanism between components of android except for Content Provider
   * Sticky Intent: Sticks with Android, for future broadcast listeners
   * Pending Intent: Will be used when someone wants to fire an intent in the future and maybe at that time the app is not alive anymore.

5. #### How can we transfer objects between activities?
   * Parcelable which is better for Android apps than Serializable which uses reflection

6. #### What is the difference between `Serializable` and `Parcelable`? Which is the best approach in Android?

7. #### What kind of modes of concurrency are in Android?
   * Threads
   * Async tasks
   * Services
   * Kotlin Coroutines

8. #### What is the difference between `Service` & `IntentService`?
   * IntentService is used for short tasks and a Service is for long ones
   * IntentService runs in the App process but Service runs in a separate process.

9. #### What are the Android launch modes?
   * standard (default): The system always creates a new instance of the activity in the target task and routes the intent to it.
   * singleTop: If an instance of the activity already exists at the top of the target task, the system routes the intent to that instance through a call to its onNewIntent() method, rather than creating a new instance of the activity.
   * singleTask: The system creates the activity at the root of a new task and routes the intent to it. However, if an instance of the activity already exists, the system routes the intent to the existing instance through a call to its onNewIntent() method, rather than creating a new one.
   * singleInstance: Same as "singleTask", except that the system doesn't launch any other activities into the task holding the instance. The activity is always the single and only member of its task.

10. #### Are you familiar with ProGuard?
   * ProgGuard is a free obfuscation tool and DexGuard is the enterprise version of ProGuard.

11. #### What is a Broadcast Receiver? What kind of messages it can receive?
   * simply respond to broadcast messages from other applications or from the system itself
   * must be Created and Registered within manifest or programmatically

12. #### What are the essential building blocks of an Android application?
   * Activities: They dictate the UI and handle the user interaction to the smartphone screen.
   * Services: They handle background processing associated with an application.
   * Broadcast Receivers: They handle communication between Android OS and applications.
   * Content Providers: They handle data and database management issues.
   * Intents: Communication between the above-mentioned components is through Intents.

13. #### What is the Intent?
   * Intents define the intention of an Application. S simple message object which is used to transfer data between activities.
   * explicit intent: used to launch a specific application component
   * implicit intent: specifies an action that can invoke any app on the device able to perform that action

14. #### What is a Service?
   * A Service is an application component that can perform long-running operations in the background and does not provide a user interface.
   * a component can bind to a service to interact with it and even perform interprocess communication (IPC) if it is running in a separate process

15. #### How can Activity communicate with services?
   * Binding services
   * Using Callbacks interfaces

16. #### What is ContentProvider?
   * They encapsulate data and provide it to applications through the single ContentResolver interface.
   * Used for providing the content between applications
   * A content provider is only required if you need to share data between multiple applications.

17. #### What is an Adapter?
   * The adapter is an interface whose implementations provide data and the display of that data done by the ListView/RecyclerView.
   * ListViews and RecyclerView do not actually contain any data themselves. They are just a UI without data in it.

18. #### What’s the difference between Activity Context and Application Context?
   * They are both instances of Context , but the application instance is tied to the lifecycle of the application, while the Activity instance is tied to the lifecycle of the Activity.
   * They have access to different information about the application environment.

19. #### Have you used Android annotations (e.g. IntegerRes, IntDef, ...)?

20. #### Like to work on Android app Backend (core) or UI (view)?

21. #### Explain the Activity lifecycle?

22. #### We have 3 Activities (A, B, and C which is transparent) explain what is the sequence of lifecycle methods execution if we 1) go from A to B, 2) then B to C, 3) Rotate the phone, 4) press back to B, 5) press back to A!!?

23. #### What is a Fragment?

24. #### Do you have any experience with NDK?

25. #### Do you have any experience with Bluetooth and BLE Android API?

26. #### What are the ways we can store information in an Android app?

27. #### Why should you avoid to run non-UI code on the main thread?

28. #### What do you use `SharedPreferences`/`database` for? Why? Do you encrypt anything you store? How?

29. #### What is the size of the Bundle in Android. What can happen if pass large amount of data inside Intents?
   * ~500kb
   * TransactionTooLargeException may be thrown by the system.
30. #### What is memory leak. How to test app for memory leaks.
