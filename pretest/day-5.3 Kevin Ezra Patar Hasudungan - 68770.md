#### **Optional Questions:**

1. What is the purpose of Shared Preferences in Android?
   - a) To store large amounts of data in a relational format.
   - b) To store small key-value pairs for user preferences or settings.
   - c) To store large media files like images and videos.
   - d) To interact with external databases.
   - e) None of the above.
   Answer: B

2. Which method is used to save data in Shared Preferences?
   - a) `apply()`
   - b) `savePreferences()`
   - c) `writePreferences()`
   - d) `store()`
   - e) `commit()`
   Answer: A

3. How can you remove a specific key from Shared Preferences?
   - a) `clearKey()`
   - b) `remove()`
   - c) `deleteKey()`
   - d) `deletePreference()`
   - e) `removeKey()`
   Answer: B

4. Where is data stored when using Shared Preferences?
   - a) External storage
   - b) Internal storage in XML format
   - c) SQLite database
   - d) In-memory cache
   - e) Cloud storage
    Answer: B

5. What data types can be stored in Shared Preferences?
   - a) `String`, `int`, `boolean`
   - b) `String`, `int`, `ArrayList`
   - c) `String`, `int`, `boolean`, `ArrayList`
   - d) `String`, `int`, `float`, `boolean`, `Set<String>`
   - e) `String`, `float`, `JSONArray`
   Answer: D

---

#### **True/False Questions:**

1. Shared Preferences can be used to store complex objects like lists or JSON data. 
Answer: False
2. Data saved in Shared Preferences is lost when the app is closed.
Answer: False
3. `apply()` saves data asynchronously, while `commit()` saves it synchronously. 
Answer: True
4. Shared Preferences can store large amounts of data such as images or videos.
Answer: False
5. You can access Shared Preferences from multiple activities in an Android app. 
Answer: True

---

#### **Short Answer Questions:**

1. What is the difference between `apply()` and `commit()` in Shared Preferences?
Answer: `apply()` saves data asynchronously, while `commit()` saves it synchronously.

2. How would you store a user's login status (true/false) using Shared Preferences in Android?
Answer: `putBoolean()` method is used to store the user's login status, like this:  `prefs.putBoolean("logged_in", true);`

3. How can you read data from Shared Preferences in Android?
Answer: To read data from Shared Preferences, use `get()` method.

4. What are the advantages of using Shared Preferences over other storage options for small amounts of data?
Answer: Shared Preferences is easy to use, and data is stored in a simple key-value format, making it easy to read and write data.

5. Can you modify Shared Preferences from multiple threads? Explain your answer.
Answer: No, you should not modify Shared Preferences from multiple threads. Android does not guarantee thread safety for Shared Preferences, and modifying it from multiple threads can lead to unexpected behavior or crashes.


---

#### **Code Fix Questions:**

1. **Incorrect code:**
   ```kotlin
   val sharedPref = getSharedPreferences("UserPrefs", Context.MODE_PRIVATE)
   val editor = sharedPref.edit()
   editor.putValue("username", "JohnDoe")
   editor.apply()
   ```
   **Fix the code to store the correct data.**
   **Correct code:**
   ```kotlin
   val sharedPref = getSharedPreferences("UserPrefs", Context.MODE_PRIVATE)
   val editor = sharedPref.edit()
   editor.putString("username", "JohnDoe")
   editor.apply()
   ```

2. **Incorrect code:**
   ```kotlin
   val sharedPref = getSharedPreferences("MyPrefs", Context.MODE_PRIVATE)
   val username = sharedPref.getValue("username", "defaultName")
   ```
   **Fix the code and explain the correct method to read from Shared Preferences.**
   Explanation:  To retrieve values from a shared preferences file, call methods such as `getInt()` and `getString()`
   **Correct code:**
   ```kotlin
   val sharedPref = getSharedPreferences("MyPrefs", Context.MODE_PRIVATE)
   val username = sharedPref.getString("username", "defaultName")
   ```

3. **Incorrect code:**
   ```kotlin
   val editor = sharedPref.edit()
   editor.clear("key")
   editor.commit()
   ```
   **Fix the code to properly remove a key from Shared Preferences.**
   **Correct code:**
   ```kotlin
   val editor = sharedPref.edit()
   editor.remove("key")
   editor.commit()
   ```

---

### Project Using Shared Preferences

#### **Project: Save and Retrieve User Settings Using Shared Preferences**

**Task:**
- Create an app that allows the user to save and retrieve preferences, such as a username and theme preference (light/dark mode).

**Instructions:**

1. **Create a simple UI with the following:**
   - An `EditText` for entering the username.
   - A `Switch` to toggle between light and dark mode.
   - A `Button` to save the preferences.
   - A `TextView` to display the saved username and theme status.

2. **Write the Shared Preferences logic:**
   - When the user clicks the save button, save the username and the state of the theme toggle in Shared Preferences.
   - Use `apply()` to save the data asynchronously.

3. **Load the saved preferences:**
   - When the app starts, load the saved username and theme preference from Shared Preferences and display them in the `TextView`.
   - Set the toggle switch to match the saved theme preference.

4. **Implement light and dark mode:**
   - Apply the light or dark theme based on the saved preference when the user reopens the app.
   - Use `setTheme()` to apply the selected theme before setting the content view.

5. **Bonus:**
   - Add a reset button that clears the stored preferences and resets the UI.

**Expected Outcome:**
- The user should be able to enter a username, choose a theme, and save these settings.
- Upon reopening the app, the username and theme should persist, and the UI should reflect the saved theme (light or dark).

