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
