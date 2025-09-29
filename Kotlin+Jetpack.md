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
