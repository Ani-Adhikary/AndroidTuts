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
