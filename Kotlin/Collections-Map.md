# Map
```Kotlin
// Syntax
val numbersMap = mapOf("key1" to 1, "key2" to 2, "key3" to 3)

// Retrieving all keys and values
println("All keys: ${numbersMap.keys}")
println("All values: ${numbersMap.values}")

// Accessing to a value
if("key2" in numbersMap) println("Value by key \"key2\": ${numbersMap["key2"]}")
if(1 in numbersMap.values) println("The value 1 is in the map")
if(numbersMap.containsValue(1)) println("The value 1 is in the map")

// MutableMap : Map with map write operations
val numbersMap = mutableMapOf("one" to 1, "two" to 2)
numbersMap.put("three" to 3)        // adding a new pair
numbersMap["one"] = 11              // reassigning a new value

```
