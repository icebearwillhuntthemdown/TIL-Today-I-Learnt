# startActivity 

## `startActivity(intent: Intent)`
- 액티비티에서 다른 액티비티로 이동할 때 호출한다.
- Intent 객체에 데이터를 담아서 이동할 액티비티에 전달할 수 있다.
```Kotlin
class MainActivity : AppCompatActivity() {
	override fun onCreate(savedInstanceState: Bundle?) {
		super.onCreate(savedInstanceState)
		setContentView(R.layout.activity_main)
	}

	fun sendMesaage(view: View) {
		val editText = findViewById<EditText>(R.id.editText)
		val message = editText.text.toString()
		val intent = Intent(this, RecipientActivity::class.java).apply {
			putExtra(EXTRA_MESSAGE, message)
		}
		startActivity(intent)
	}
}
```
<br/><br/>

## startActivityForResult()
- start an activity and expect something in return
- waits for callbacks when the started activity decided to finish
```Kotlin
fun startActivityForResult (intent: Intent, requestCode: Int)
```
- intent : the intent to start
- requestCode : if >= 0, this code will be returned in onActivityResult()
<br/><br/>

## setResult()
- used to set the result that your activity will return to its caller
```Kotlin
fun setResult(int resultCode)
```
- resultCode: the reulst code to propagate back to the original activity, often RESULT_CANCELLED or RESULT_OK
<br/><br/>

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

+) Fragment에서 startActivityForResult()를 호출한 경우 그 결과를 받는 onActivityResult()는 해당 Fragment를 호출하는 Activity에서 수신한다.





