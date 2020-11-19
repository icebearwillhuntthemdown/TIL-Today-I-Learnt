# startActivity 

## startActivity()
- start
```Kotlin
fun startActivity (intent: Intent) 
```
- intent : the intent to start

## startActivityForResult()
- start an activity and expect something in return
- waits for callbacks when the started activity decided to finish
```Kotlin
fun startActivityForResult (intent: Intent, requestCode: Int)
```
- intent : the intent to start
- requestCode : if >= 0, this code will be returned in onActivityResult()

## onActivityResult()
- called when an activity you launched exists
- returns `requestCode`, `resultCode`, and additional `data` Intent.
- the result can be received on `onResume()`
```Kotlin
fun onActivityResult (requestCode: Int, resultCode: Int, data: Intent)
```
- requestCode : the request code originally supplied to `startActivityForResult()`
- resultCode : the result code returned from the child activity through its `setResult()`
- data : an intent, which can return result data to the caller (various data can be attached to intent "extras")

## setResult()
- used to set the result that your activity will return to its caller
```Kotlin
fun setResult(int resultCode)
```
- resultCode: the reulst code to propagate back to the original activity, often RESULT_CANCELLED or RESULT_OK




