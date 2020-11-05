## Adapter
The `Adapter` provides access to the data items. It acts as a bridge between an `AdapterView` and the underlying data for the view. 

### ArrayAdapter
Returns a view for each object in a collection of data objects you provide and can be used with list-based UI widgets like `ListView` or `Spinner`.
By default the arrayAdapter calls toString() on each data in the collection and places the result in a TextView.

#### Example
When you want to use ListView to display a String array.
```Kotlin
val adpter = ArrayAdapter<String>(this, android.R.layout.simple_list_item_1, myStringArray)
```
#### Params
1. `Context`
2. The layout where the `TextView` is
3. Array

```Kotlin
val listView: ListView = findViewById(R.id.listview)
listView.adapter = adpaer
```

## AdapterView
- a view whose children are determined by an `Adapter`
- Subclasses        
    + ListView
    + GridView
    + Spinner
    + Gallery

## References
- https://developer.android.com/guide/topics/ui/declaring-layout.html#AdapterViews

