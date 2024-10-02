#### **Optional (Choose the correct answer):**

1. What type of collection ensures no duplicate elements in Kotlin?

   - a) `List`
   - b) `Set`
   - c) `Map`
   - d) `Array`
     Answer: B

2. What method is used to start a coroutine in Kotlin?

   - a) `run()`
   - b) `launch()`
   - c) `start()`
   - d) `async()`
     Answer: B

3. Which lifecycle method is called right before an activity becomes visible to the user?

   - a) `onCreate()`
   - b) `onStart()`
   - c) `onResume()`
   - d) `onPause()`
     Answer: B

4. What Android storage option is best suited for storing small amounts of user settings or preferences?

   - a) External storage
   - b) SQLite
   - c) SharedPreferences
   - d) Network storage
     Answer: C

5. What permission must be added to access the internet in an Android app?
   - a) `<uses-permission android:name="android.permission.NETWORK_ACCESS" />`
   - b) `<uses-permission android:name="android.permission.INTERNET" />`
   - c) `<uses-permission android:name="android.permission.ACCESS_WIFI" />`
   - d) `<uses-permission android:name="android.permission.DATA" />`
     Answer: B

---

#### **Short Answer:**

6. What is the difference between `listOf()` and `mutableListOf()` in Kotlin?
   Answer: `listOf()` returns an immutable list, while `mutableListOf()` returns a mutable list.

7. How can you suspend a coroutine in Kotlin?
   Answer: You can suspend a coroutine using the `suspend` keyword or by calling a suspend function from within the coroutine.

8. What does `onPause()` do in the Android activity lifecycle?
   Answer: `onPause()` is called when the activity is no longer visible to the user, and it is used to release any system resources that the activity is using.

9. Why is `RecyclerView` preferred over `ListView` for displaying large datasets in Android?
   Answer: `RecyclerView` is preferred because it only loads the visible items, and it is more flexible because it allows for more customization and animation options.

10. What is the purpose of `Room` in Android database management?
    Answer: Room is a persistence library that provides an abstraction layer over SQLite, allowing for more efficient and easier database management in Android apps.

11. How does Retrofit simplify network requests in Android?
    Answer: Retrofit simplifies network requests by providing a simple and intuitive API for making HTTP requests, and it also handles tasks such as JSON parsing and caching.

12. What is the `onCreate()` method used for in the Android lifecycle?
    Answer: The `onCreate()` method is used to initialize the activity and its components, such as the layout and any necessary resources.

13. Explain what `LiveData` does in Android development.
    Answer: `LiveData` is a data holder that allows data to be observed and updated in response to changes, making it useful for managing data in Android applications.

14. How do you handle screen rotations in Android without losing data?
    Answer: You can use the `onSaveInstanceState()` method to save the current state of the activity, and then restore it in the `onCreate()` method after the screen rotation.

15. What are the advantages of using coroutines over traditional threads in Kotlin?
    Answer: Coroutines are more efficient, easier to use, and provide better performance than traditional threads.

---

#### **Yes/No Questions:**

16. Can a `Map` in Kotlin contain duplicate keys?
    Answer: No

17. Is `onStop()` called before `onDestroy()` in the Android activity lifecycle?
    Answer: Yes

18. Do you need explicit permissions to access external storage in Android?
    Answer: Yes

19. Does `HttpURLConnection` support both GET and POST requests?
    Answer: Yes

20. Is it possible to perform synchronous network requests using Retrofit in Android?
    Answer: No

---

#### **Correct the Code (with Reasons for Correction):**

21. **Incorrect code:**
    ```kotlin
    val myList = listOf(1, 2, 3)
    myList.add(4)
    ```
    **Correct code:**
    ```kotlin
    val myList = mutableListOf(1, 2, 3)
    myList.add(4)
    ```

---

22. **Incorrect code:**
    ```kotlin
    suspend fun myFunction() {
        delay(1000L)
        println("Completed")
    }
    ```
    **Correct code:**
    ```kotlin
    suspend fun myCoroutine() {
        delay(1000L)
        println("Coroutine executed")

    }
    ```

---

23. **Incorrect code:**

    ```kotlin
    val map = mapOf(1 to "One", 2 to "Two")
    map[3] = "Three"
    ```

    **Correct code:**

    ```kotlin
    val map = mutableMapOf(1 to "One", 2 to "Two")
    map[3] = "Three"
    ```

---

24. **Incorrect code:**
    ```kotlin
    val intent = Intent(this, SecondActivity)
    startActivity(intent)
    ```

---

25. **Incorrect code:**
    ```kotlin
    val view = findViewById<Button>(R.id.myButton)
    view.setOnClickListener {
        toast("Button clicked")
    }
    ```
    **Correct code:**
    ```kotlin
    val view = findViewById<Button>(R.id.myButton)
    view.setOnClickListener {
        toast(this,  "Button clicked",  Toast.LENGTH_SHORT).show()
    }
    ```

---

26. **Incorrect code:**

    ```kotlin
    fun add(a: Int, b: Int): Int {
        return a + b
    }

    val result = add(5, "10")
    ```

    **Incorrect code:**

    ```kotlin
    fun add(a: Int, b: Int): Int {
        return a + b
    }

    val result = add(5, 10)
    ```

---

27. **Incorrect code:**

    ```kotlin
    override fun onSaveInstanceState(outState: Bundle) {
        outState.putInt("KEY", 1)
    }

    override fun onRestoreInstanceState(savedInstanceState: Bundle) {
        val key = savedInstanceState.getString("KEY")
    }
    ```

---

28. **Incorrect code:**
    ```kotlin
    val textView = findViewById<TextView>(R.id.textView)
    textView.text = R.string.app_name
    ```
    **Correct code:**
    ```kotlin
    val textView = findViewById<TextView>(R.id.textView)
    textView.text = R.string.app_name.toString()
    ```

---

29. **Incorrect code:**

    ```kotlin
    val job = GlobalScope.async {
        delay(1000L)
        "Hello"
    }

    val result = job.get()
    ```

    ```kotlin
    val job = GlobalScope.async {
        delay(1000L)
        "Hello"
    }

    val result = job.getComplete()
    ```

---

30. **Incorrect code:**
    ```kotlin
        fun networkRequest() {
            val url = URL("https://example.com")
            val connection = url.openConnection() as HttpURLConnection
            connection.setRequestMethod("POST")
        }
    ```

---

31. #### **Story-based Question:**

#### **Story:**

You are building an Android app that fetches data from a server using Retrofit. The app fetches user data and displays it in a `RecyclerView`. However, the app crashes when the data is fetched and loaded into the `RecyclerView`.

Here is the code causing the crash:

```kotlin
class UserAdapter(private val userList: List<User>) : RecyclerView.Adapter<UserAdapter.UserViewHolder>() {

    class UserViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView)

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): UserViewHolder {
        val view = LayoutInflater.from(parent.context).inflate(R.layout.user_item, parent, false)
        return UserViewHolder(view)
    }

    override fun onBindViewHolder(holder: UserViewHolder, position: Int) {
        val user = userList[position]
        holder.itemView.findViewById<TextView>(R.id.userName).text = user.name
    }

    override fun getItemCount() = userList.size
}
```
