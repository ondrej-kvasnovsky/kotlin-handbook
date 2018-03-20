# Basics

This chapter describes basics about Kotlin programming language.

### Expressions

```
3+6
listOf(1, 2, 3)
"Kotlin" + " is " + "interesting"
```

### Statement have expressions in the right side

```
val a = 47 + 1
```

### Conditional Statements

```
fun main(args: Array<String>) {
    val age = 35
    if (age < 30) {
        println("You are too young, go back by two steps")
    } else {
        println("You are too old, go back by twenty steps")
    }

    when (age) {
        1 -> println("I gone one!")
        35 -> {
            println("Let me think...")
            println("I got 35, oh my god!")
        }
        else -> println("Not sure what is happening right now")
    }

    // conditional expressions
    val result = when (age) {
        35 -> "Hi old man"
        else -> "Whatever..."
    }
    println(result)

    val anotherOne = if (age == 35) {
        "Oh man!"
    } else {
        "Oh boy!"
    }
    println(anotherOne)

    val experiment = when (age) {
        1 * 10 -> "What?"
        in 1..50 -> "You are OK"
        !in 1..50 -> "You are NOT OK"
        else -> "Kind of bad"
    }
    println(experiment)
}
```

Here is what gets printed.

```
You are too old, go back by twenty steps
Let me think...
I got 35, oh my god!
Hi old man
Oh man!
You are OK
```

### For Loops

```
fun main(args: Array<String>) {
    var sum = 0
    for (i in 1..10) {
        sum += i
    }
    println(sum)

    val languages = listOf("Java", "Kotlin")
    for ((index, language) in languages.withIndex()) {
        println("$index $language")
    }
} sv
```

Here is the output.

```
55
0 Java
1 Kotlin
```

### While Loops

```
package handbook

fun main(args: Array<String>) {
    var x = 5
    while (x >= 0) {
        println(x)
        x--
    }
}
```

Here is the output:

```
5
4
3
2
1
0
```

### 



