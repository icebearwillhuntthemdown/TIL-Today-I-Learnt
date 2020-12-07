## build.gradle
1. for the project
2. for the module
    - each module has its own build.gradle

## Module
- Module: a container for your app's source code, resource files, build.gradle and app level settings and Android manifest file.
- Each module are independently built, tested, and debugged 
- a module for each device type 
    e.g.) Wear OS, Android TV

## UI
### Layouts
- `ViewGroup` Object 
- a container that control how their child views are positioned on the screen
- `ConstraintLayout`: a layout that defines the position for each view based on constraints to sibling views and the parent layout.
    + constraintHorizontal_bias
    + https://developer.android.com/reference/androidx/constraintlayout/widget/ConstraintLayout

### Widgets
- `View` Object
- UI components e.g.) buttons, text boxes
