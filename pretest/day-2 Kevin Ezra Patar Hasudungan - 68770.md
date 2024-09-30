1. Answer: A

2. Answer: D

3. Answer: C

4. Answer: B

5. Answer: C

---

#### **Short Answer:**

6. What is the difference between `var` and `val` in Kotlin?
Answer:  `var` is used for mutable variables, while `val` is used for immutable variables. Mutable means it could be re-assigned again, while immutables can't.


7. How do you create a list in Kotlin?
Answer:  You can create a list in Kotlin using the `listOf()` function or `mutableListOf()`. The differences are  that `listOf()` creates an immutable list, while `mutableListOf()` creates a mutable list.

8. Write a simple `if-else` statement in Kotlin.
```kotlin
var x = 5
if(x > 4) {
    println("x is greater than 4")
} else {
    println("x is less than 4")
}
```

9. How do you handle nullability in Kotlin?
Answer:  Kotlin has a null safety feature that prevents you from point a null reference. You can  use the `?.` operator to safely call a method on a nullable object, and the `!!` operator to assert that an object is not null.


10. What is a lambda function in Kotlin?
Answer:  A lambda function is a small anonymous function that can be defined inline within a higher-order function. It is the same as Lambda Function in python. 

11. How do you define a class in Kotlin?
Answer:  You can define a class in Kotlin using the `class` keyword. If you want to make the class to be inherited to another class, use `open` syntax before class declaration.

12. How do you use a `for` loop to iterate through a list in Kotlin?
Answer:
```kotlin
var iterables = listOf(1,2,3,4,5)
for (i in iterables) {
    println(i);
}
```

13. What does the `when` statement do in Kotlin?
Answer: `when` statement is used when you want to assert a value and use it to make conditional statements. It is the same as `switch` statement in another programming language.


14. How do you check if a number is even in Kotlin?
Answer: You could use `%` (modulo) operator and checks if the value is 0 if it's calculated using modulo. Example:
```kotlin
var x = 5
if (x % 2 == 0) {
    println("x is even")
} else {
    println("x is odd")
}
```


15. How do you declare an array in Kotlin?
Answer: You could use `arrayOf()` function. For example
```kotlin
var array = arrayOf(1,2,3,4,5)
```

---

#### **Yes/No Questions:**

16. Can `val` be reassigned to a new value after its initial assignment?
Answer: No

17. Does Kotlin support operator overloading?
Answer: Yes

18. Is Kotlin fully interoperable with Java?
Answer: Yes

19. Can a function in Kotlin return a value using `return` keyword?
Answer: Yes

20. Can Kotlin's `when` statement be used as an expression to return values?
Answer: Yes

---

#### **Correct the Code (with Answers):**

21. **Incorrect code:**

    ```kotlin
    val x = "Hello"
    x = "World"
    ```

    **Correct Code:**
    ```kotlin
    var x = "Hello"
    x = "World"
    ```

22. **Incorrect code:**

    ```kotlin
    fun sum(a: Int, b: Int): Int {
        return a + b
    sum(5, 10)
    ```

    **Correct Code:**

    ```kotlin
    fun sum(a: Int, b: Int): Int {
        return a + b
    }
    sum(5, 10)
    ```

23. **Incorrect code:**

    ```kotlin
    val myList = listOf(1, 2, 3)
    myList.add(4)
    ```

    **Correct Code:**
    ```kotlin
    var myList = mutableListOf(1, 2, 3)
    myList.add(4)
    ```

24. **Incorrect code:**

    ```kotlin
    val name: String = null
    ```
    Note: Theres actually 2 ways to fix this one, either by making the variable nullable or by remove the null.


    **1st Correct Code:**
    ```kotlin
    val name: String? = null
    ```
    **2nd Correct Code:**
    ```kotlin
    val name: String
    ```

25. **Incorrect code:**

    ```kotlin
    if x > 5 {
        println("x is greater than 5")
    }
    ```

    **Correct Code:**
    ```kotlin
    if (x > 5) {
        println("x is greater than 5")
    }

    ```

26. **Incorrect code:**

    ```kotlin
    when (x) {
        1 -> println("One")
        2 -> println("Two")
        else println("Other")
    }
    ```

    **Correct Code:**
    ```kotlin
    when (x) {
        1 -> println("One")
        2 -> println("Two")
        else -> println("Other")
    }
    ```

27. **Incorrect code:**

    ```kotlin
    fun greet() {
        println("Hello, $name)
    }
    ```

    **Correct Code:**
    ```kotlin
    fun greet(name: String) {
        println("Hello, $name")
    }
    ```

28. **Incorrect code:**

    ```kotlin
    val myVar = "10"
    val result = myVar + 5
    ```

    **Correct code:**
    ```kotlin
    val myVar = 10
    val result = myVar + 5
    ```

29. **Incorrect code:**

    ```kotlin
    val numbers = arrayOf(1, 2, 3)
    println(numbers[3])
    ```

    Note: The correct code is to change the array selector, to anyting less than the arr length - 1, because indexes starts from 0.
    **Correct code:**
    ```kotlin
    val numbers = arrayOf(1, 2, 3)
    println(numbers[2])
    ```

30. **Incorrect code:**
    ```kotlin
    class Person(val name: String, val age: Int) {
        fun greet() {
            print("Hello, my name is " + name + " and I'm " + age)
        }
    }
    ```

    Note: Technically, it is not incorrect, because the `age` is automatically converted to string, but it could use `.toString()` method.
    **Correct code:**
    ```kotlin
    class Person(val name: String, val age: Int) {
        fun greet() {
            print("Hello, my name is " + name + " and I'm " + age.toString())
        }
    }
    ```

---

### **Story-based Question (with Failed Code)**

#### **Story:**

Imagine you are building a ticket booking system for a movie theater. Each customer can reserve a seat by providing their name and the seat number. The seat numbers are stored in an array, and the program should check if the seat is available. If available, the seat will be reserved, and if not, a message will be displayed to the user that the seat is taken.

Here’s the failed code:

```kotlin
fun reserveSeat(name: String, seatNumber: Int) {
    val availableSeats = arrayOf(1, 2, 3, 4, 5)

    if (availableSeats.contains(seatNumber)) {
        availableSeats[seatNumber] = 0  // Mark the seat as reserved by setting it to 0
        println("$name reserved seat $seatNumber.")
    } else {
        println("Seat $seatNumber is already reserved.")
    }
}

fun main() {
    reserveSeat("John", 2)
    reserveSeat("Sarah", 2)
}
```

Answer: Theres 2 problem in this code. First of all, the availableSeats Array is stored inside function's local variable, so it'll be recreated every time the function is called. Second, the seatNumber is used as an index to mark the seat as reserved, which is incorrect because the seatNumber is not the index of the array.

Here's the correct code:
```kotlin
fun reserveSeat(name: String, seatNumber: Int, seats: Array<Int>) {
    if (seats.contains(seatNumber)) {
        val seatIndex = seats.indexOf(seatNumber)
        seats[seatIndex] = 0  // Mark the seat as reserved by setting it to 0
        println("$name reserved seat $seatNumber.")
    } else {
        println("Seat $seatNumber is already reserved.")
    }
}

fun main() {
    val availableSeats = arrayOf(1,2,3,4,5)
    reserveSeat("John", 2, availableSeats)
    reserveSeat("Sarah", 2, availableSeats)
}
```