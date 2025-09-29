<h1> 🚀 Kotlin + Jetpack Compose Crash Start</h1>

<h2>1. Hello World</h2>

```kotlin

@Composable
fun Greeting() {
    Text(text = "Hello, Buddy!")  // Simple text
}

```

<h2> 2. Variables & State </h2>

In Compose we use remember + mutableStateOf to make things reactive.

```kotlin

@Composable
fun CounterApp() {
    var count by remember { mutableStateOf(0) }

    Column {
        Text(text = "Count: $count")
        Button(onClick = { count++ }) {
            Text("Increase")
        }
    }
}

```

💡 count behaves like a live variable → UI updates automatically.

<h2> 3. Conditionals </h2>

```kotlin

@Composable
fun AgeCheck(age: Int) {
    if (age >= 18) {
        Text("You are an Adult")
    } else {
        Text("You are a Minor")
    }
}

```

<h2>4. Loops</h2>

```kotlin

@Composable
fun NumberList() {
    Column {
        for (i in 1..5) {
            Text("Item $i")
        }
    }
}

```

<h2> 5. Functions </h2>

```kotlin

fun add(a: Int, b: Int) = a + b

@Composable
fun ShowSum() {
    val result = add(5, 7)
    Text("Sum = $result")
}

```

<h2> 6. Classes & Objects </h2>

 ```kotlin

data class User(val name: String, val age: Int)

@Composable
fun UserCard(user: User) {
    Text("Name: ${user.name}, Age: ${user.age}")
}

```

Usage:

```kotlin

UserCard(User("Buddy", 25))

```

<h2> 7. Null Safety in Compose </h2>

```kotlin

@Composable
fun ShowName(name: String?) {
    Text(text = name ?: "No Name")  // Elvis operator → default value
}

```

<h2> 👉 With just these, you can already build small apps like: </h2>

Counter ✔️

To-do list ✔️

Simple login screen ✔️

<h2>Demo</h2>

Perfect Buddy 🙌 Let’s build your first mini Jetpack Compose app step by step.
We’ll do a Counter + List + Button Clicks all in one → this will give you Kotlin + Compose confidence.


```kotlin
import android.os.Bundle
import androidx.activity.ComponentActivity
import androidx.activity.compose.setContent
import androidx.compose.foundation.layout.*
import androidx.compose.foundation.lazy.LazyColumn
import androidx.compose.foundation.lazy.items
import androidx.compose.material3.*
import androidx.compose.runtime.*
import androidx.compose.ui.Alignment
import androidx.compose.ui.Modifier
import androidx.compose.ui.unit.dp

class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        setContent {
            MaterialTheme {
                MiniApp()
            }
        }
    }
}

@Composable
fun MiniApp() {
    var count by remember { mutableStateOf(0) }
    var items = remember { mutableStateListOf<String>() }

    Column(
        modifier = Modifier.fillMaxSize().padding(16.dp),
        horizontalAlignment = Alignment.CenterHorizontally
    ) {
        // Counter
        Text("Count: $count", style = MaterialTheme.typography.headlineMedium)

        Spacer(Modifier.height(8.dp))

        Button(onClick = { count++ }) {
            Text("Increase Count")
        }

        Spacer(Modifier.height(16.dp))

        // Add item to list
        Button(onClick = { items.add("Item #${items.size + 1}") }) {
            Text("Add Item")
        }

        Spacer(Modifier.height(16.dp))

        // Show list
        LazyColumn {
            items(items) { item ->
                Text(text = item, style = MaterialTheme.typography.bodyLarge)
            }
        }
    }
}

```


<h2>🔥 What This App Does </h2>

Shows a counter (count) → updates when button clicked.

Maintains a list (items) → each button press adds a new item.

Uses LazyColumn for scrolling list.

Demonstrates Kotlin basics (variables, loops, null safety) inside Compose.

<h2>👉 If you run this in Android Studio, you’ll see: </h2>

A number that increases each time you press "Increase Count".

A growing list of items each time you press "Add Item".

