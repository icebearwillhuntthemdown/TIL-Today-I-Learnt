## Android?
* OS based on Linux
* Application Framework to create a mobile app
* Phones, tablets, wearables, TVs, and IOT devices


## Activity Lifecycle Callbacks
* onCreate()
    - timing : the system first creates the activity 
    - state : Created => Started
    - task : basic application startup logic
    - parameter : savedInstanceState - contains the activity's previously saved state)
```Kotlin
    override fun onCreate(savedInstanceState: Bundle?) {
        // call the super class to complete the creation of activity 
        super.onCreate(savedInstanceState)

        // recovering the instance state
        gameState = savedInstanceState?.getString(GAME_STATE_KEY)

        // set the UI layout for this activity
        setContentView(R.layout.main_activity)

        textView = findViewById(R.id.text_view)
    }

    // called only when there's a saved instance saved by onSaveInstanceState()
    override fun onRestorInstanceSate(savedInstanceState: Bundle?) {
        textView.text = savedInstanceState?.getString(TEXT_VIEW_KEY)
    }

    // invoked when the activity may be temporarily destroyed, save the instance state here
    override fun onSaveInstanceState(outState: Bundle?) {
        outState?.run {
            putString(GAME_STATE_KEY, gameState)
            putString(TEXT_VIEW_KEY, textView.text.toString())
        }

        // call superclass to save any view hierarchy
        super.onSaveInstanceState(outState)
    }
```

* onStart()
    - timing : when the activity enters the Started state
    - state : `Started` => `Resumed`
    - task
        - makes the activity visible to the user
        - when in `Started` state, fires `ON_START` event

* onResume()
    - timing : when the activity enters the `Resumed` state
    - state : `Resumed`
    - task
        + the activity comes to the foreground
* onPause()
* onStop()
* onDestroy()








`R.layout.activity_name` : the activity file's resource ID

