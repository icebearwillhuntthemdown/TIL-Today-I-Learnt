1. onCreate()
2. onStart()
3. onResume()
4. onPause()
5. onStop()
6. onDestroy()


## onCreate()
- must and called only once for the entire life of the activity
- when: the system first creates the activity
- activity state: `created` -> `started`
- what: basic application startup logic
    + bind data to lists
    + associate the activity with a `ViewModel` e.g.)setContentView
    + instantiate class-scope variables
    + on completion, 
        + the activity enters the `started` state
        + the system calls the `onStart()` and `onResume()` methods 
```Kotlin
override fun onCreate(savedInstanceState: Bundle?) {
    super.onCreate(savedInstanceState)
    setContentView(R.layout.main_activity)
    init()
}
```

## onStart()
- when: the activity enters `started` state
- activity state: `started` -> `resumed`
- what: makes the activity visible to the user
    + initializes the code maintains the UI
    + calls `ON_START` lifecycle event
    + on completion,
        * the activity enters the `resumed` state
        * the system invokes the `onResume()` method

## onResume()
- when: the activity enters the `resumed` state
- activty state: `resumed` -> `paused`
- what: the activity comes to the foreground and interacts with the user
    + the app stays in this state until some interruption happens to take focus away
        + receiving a phone call
        + the user navigating to another activity
        + the device turning off the screen
    + calls `ON_RESUME` lifecycle event
    + when an interruption occurs,
        * the activity enters the `paused` state
        * the system invokes the `onPause()` method
    + when returning to the `resumed` state,
        * the system calls `onResume` again

## onPause()
- when: when the activity lost focus 
    + the activity is no longer in the foreground or is partially visible
    + some interruption event occured
    + the activity is partially visible but not in focus, it remains paused
        + multi-window mode and the activity doesn't have focus
        + a new, semi-transparent activity such as a dialog opens
- activity state: `paused` until `onResume()` or `onStop` is called
- what: pause or adjust operations that is not necessary when the activity is paused
    + release system resources
    + calls `ON_PAUSE` lifecycle event
    + on completion,
        * the activity remains `paused` state
        * if the activity resumes, the system invokes `onResume` callback
        * if the activity becomes completely invisible, the system calls `onStop`
- in `paused` sate the activity object is kept resident in memory
    + no need to re-initialize components when resumed

## onStop()
- when: the activity is no longer visible to the user
    + a newly launched activity covers the entire screen
    + the activity has finished running and is about to be terminated
- activity state: `stopped` until `onRestart()` or `onDestroy()` is called
    + +)onRestart
        - called when the user has navigated back to it.
        - followed by `onStart()` and then `onResume()`
- what: release or adjust resources that are not needed while the component is not visible on the screen
    + perform relatively CPU-intensive shutdown operations
        * save information to a database   
    + calls `ON_STOP` lifecycle event
- In `stopped` state the activity object is kept resident in memory
    + no need to re-initialize components when resumed
    + the system also keeps track of the current state for each `View` object
        * e.g.) The user input in EditText Widget is retained without having to save it


## onDestroy()
- when: before the activity is destroyed
    + the activity is finishing
    + the system is temporarily destroying the activity due to a configuration change(e.g.) device rotation or multi-window mode
- activity state: `destroyed`
- what: release all resources that have not yet been released by earlier callbacks such as `onStop()`
    + if the activity is finishing, this is the **final** lifecycle callback the activity receives
    + if it's called for a configuration change, the system immdeiately creates a new activity instance and then calls `onCreate()`
    + calls `ON_DESTROY` lifecycle event when the activity moves to the `destroyed` state


## Process
1. Activity launched
2. `onCreate()` => `onStart()` => `onResume()`
3. Activity Running
4. interrupted => `onPause()`
5. activity is no longer visible => `onStop()`
6-1. activity finished 
    => `onDestroy`
6-2. user navigates back to the activity
    => `onRestart()` => `onStart()` => `onResume()`
6-3. process killed && user navigates to the activity 
    => `onCreate()` => `onStart()` => `onResume()`

### Examples
          | 액티비티 A ==========> 액티비티 B ==========> 액티비티 A
  Events  | 액티비티 A ==========> 화면 꺼짐  ==========> 화면 켜짐
          | 액티비티 A ==========>  바탕화면  ==========> 액티비티 A
______________________________________________________________            
  Status  |  Resumed ==========> Stopped ==========> Resumed 
______________________________________________________________  
          |           onPause()          onRestart()
Lifecycle |           onStop()           onStart()
          |                              onResume()  


## References
- https://developer.android.com/guide/components/activities/activity-lifecycle#onresume
