# Context

## Definition
- Interface to global information about an application environment for components
- the access to the Context enables to access application-wide resources
- The context of current state of the applicaition/object. It lets newly-created objects understand what has been going on. 
- Context is what enables access to system resources and it's what hook components into the "greater app"


## What context does
- Loading a resource
- Launching a new activity
- Creating views
- Obtaining system service

## How to get context
- `getApplicationContext()`
- `getContext()`
- `getBaseContext()`
- `this` in an activity class
    refers to the context of the current activity. `this` is the activity because the `Activity` class inherits from `Context`





## References
- https://stackoverflow.com/questions/3572463/what-is-context-on-android
