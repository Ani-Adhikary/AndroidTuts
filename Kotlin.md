<h1>🌱 Kotlin Basics for Android </h1>
<h2>1. Variables </h2>

```kotlin
var name = "Buddy"   // mutable (can change)
val age = 25         // immutable (like const in Swift)

```

<h2>2. Data Types </h2>

```kotlin
val isLoggedIn: Boolean = true
val score: Int = 100
val pi: Double = 3.14
val letter: Char = 'A'
val message: String = "Hello Kotlin"

```

In Android XML → Kotlin:

```kotlin
<TextView android:text="Hello"/>
```

```kotlin
val textView: TextView = findViewById(R.id.myText)
textView.text = "Hello Kotlin"

```

<h2>3. Functions </h2>

```kotlin
fun greet(user: String): String {
    return "Hello, $user!"
}

val msg = greet("Buddy")
println(msg)  // Hello, Buddy!

```

```kotlin

fun add(a: Int, b: Int) = a + b

```


<h2>4. Conditions </h2>

```kotlin
val age = 18
if (age >= 18) {
    println("Adult")
} else {
    println("Minor")
}

// like Swift switch
val day = 2
when(day) {
    1 -> println("Monday")
    2 -> println("Tuesday")
    else -> println("Other Day")
}

```

<h2>5. Loops </h2>

```kotlin
for (i in 1..5) {
    println(i) // 1 2 3 4 5
}

var x = 3
while (x > 0) {
    println(x)
    x--
}

```


<h2>6. Classes & Objects </h2>

```kotlin

class User(val name: String, var age: Int) {
    fun display() {
        println("Name: $name, Age: $age")
    }
}

val u = User("Buddy", 25)
u.display()   // Name: Buddy, Age: 25

```

<h2>7. Null Safety (important in Android!) </h2>

```kotlin

var name: String? = null   // ? means nullable
println(name?.length)      // Safe call → won’t crash


```

<h2>👉 With just these, you can already: </h2>

Handle button clicks

Display text/images

Pass data between screens
