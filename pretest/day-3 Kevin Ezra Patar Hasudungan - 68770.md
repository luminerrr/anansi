#### **Optional (Choose the correct answer):**

1. Which of the following creates an immutable list in Kotlin?
   - a) `arrayOf(1, 2, 3)`
   - b) `listOf(1, 2, 3)`
   - c) `mutableListOf(1, 2, 3)`
   - d) `setOf(1, 2, 3)`
   Answer: B

2. What is the purpose of a coroutine in Kotlin?
   - a) To manage multiple threads
   - b) To handle asynchronous programming efficiently
   - c) To suspend functions indefinitely
   - d) To manage Android lifecycle events
   Answer: B

3. Which activity lifecycle method is called when the activity is visible but not yet interactive?
   - a) `onCreate()`
   - b) `onResume()`
   - c) `onStart()`
   - d) `onPause()`
   Answer: C

4. In Android UI, which ViewGroup arranges its children in a single direction (either horizontal or vertical)?
   - a) `RelativeLayout`
   - b) `ConstraintLayout`
   - c) `LinearLayout`
   - d) `FrameLayout`
   Answer: C

5. What keyword is used to define a suspending function in Kotlin?
   - a) `async`
   - b) `launch`
   - c) `suspend`
   - d) `defer`
   Answer: C

---

#### **Short Answer:**

6. What is the difference between `listOf()` and `mutableListOf()` in Kotlin?
Answer:  `listOf()` creates an immutable list, while `mutableListOf()` creates a mutable list.


7. How does `onDestroy()` differ from `onStop()` in the Android activity lifecycle?
Answer: `onDestroy()` is called when the activity is destroyed, while `onStop()` is called when the activity is stopped but still visible.


8. What is the advantage of using coroutines over threads in Kotlin?
Answer: Coroutines are more efficient and easier to use than threads for handling asynchronous programming, because they can suspend and resume execution without the need for explicit thread management.


9. How can you prevent memory leaks in Android when handling configuration changes like screen rotation?
Answer: 


10. Explain the difference between `View` and `ViewGroup` in Android.
Answer: View is a base class for all GUI component classes, while ViewGroup is a base class for all container classes that can hold other views.


11. How does a `RecyclerView` differ from a `ListView` in Android UI components?
Answer: `RecyclerView` is a more efficient and flexible alternative to `ListView`, offering better performance and customization options.


12. What is the role of `onResume()` in the Android lifecycle?
Answer: `onResume()` is called when the activity is resumed, and is used to restore the activity's state and prepare it for user interaction.


13. What is the purpose of `launch` in Kotlin coroutines?
Answer: `launch` is used to start a coroutine in a new coroutine scope, allowing it to run concurrently with other coroutines.


14. What is `LiveData` in Android, and why is it useful?
Answer: `LiveData` is a data holder that allows data to be observed and updated in response to changes, making it useful for managing data in Android applications.


15. What is the `ViewModel` class used for in Android?
Answer: The `ViewModel` class is used to store and manage UI-related data in an Android application, making it easier to maintain a consistent UI state across configuration changes.


---

#### **Yes/No Questions:**

16. Can `setOf()` store duplicate elements in Kotlin?
Answer: No

17. Is it possible to use coroutines with Android’s lifecycle-aware components like `LiveData`?
Answer: Yes

18. Does the Android `onCreate()` method get called every time an activity becomes visible?
Answer: No

19. Can a `ConstraintLayout` position elements relative to each other in Android?
Answer: Yes

20. Are `RecyclerView` and `SwipeRefreshLayout` both advanced Android UI components?
Answer: Yes

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
    fun myCoroutine() {
        delay(1000L)
        println("Coroutine executed")
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
    override fun onCreate() {
        super.onCreate()
        setContentView(R.layout.activity_main)
    }
    ```

---

24. **Incorrect code:**
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

25. **Incorrect code:**
    ```kotlin
    val view = findViewById<Button>(R.id.button)
    view.setOnClickListener {
        Log.d("Click", "Button clicked")
    }
    ```

---

### **Story-based Question (with Failed Code)**

#### **Story:**
You are developing an Android app for managing tasks. Each task has a title and a description. The app should allow users to add tasks and display the list of tasks in a `RecyclerView`. However, the app crashes when you try to display the list of tasks.

Here’s the failed code:

```kotlin
class TaskAdapter(private val taskList: List<Task>) : RecyclerView.Adapter<TaskAdapter.TaskViewHolder>() {
    
    class TaskViewHolder(itemView: View) : RecyclerView.ViewHolder(itemView)

    override fun onCreateViewHolder(parent: ViewGroup, viewType: Int): TaskViewHolder {
        val view = LayoutInflater.from(parent.context).inflate(R.layout.task_item, parent, false)
        return TaskViewHolder(view)
    }

    override fun onBindViewHolder(holder: TaskViewHolder, position: Int) {
        val task = taskList[position]
        holder.itemView.findViewById<TextView>(R.id.taskTitle).text = task.title
        holder.itemView.findViewById<TextView>(R.id.taskDescription).text = task.description
    }

    override fun getItemCount() = taskList.size
}

data class Task(val title: String, val description: String)
```


---

