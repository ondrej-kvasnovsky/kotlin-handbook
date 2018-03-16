# Basics

This chapter describes basics about Kotlin programming language. 

### Variables & Constants

```
package handbook

fun main(args: Array<String>) {
    var variable = "Hi"
    variable = "I can change val variable"
    println(variable)

    val constant = "Constant"
    // constant = "I can't change val, it is constant"
    println(constant)
}
```

### Primitive Types & Strings

```
package handbook

fun main(args: Array<String>) {
    val string = "Crazy people" + " might be everywhere"
    println(string)

    val char: Char = 'c'
    println(char)

    val boolean = true && 1 < 2
    println(boolean)

    val byte: Byte = 127 // we need to specify type, because the default is integer
    println(byte)

    val short: Short = 32767
    println(short)

    val integer = 2147483647 // integer
    println(integer)

    val long: Long = 9223372036854775807
    println(long)

    val double: Double = 3.14 // default is double
    println(double)

    val float: Float = 3.14f // default is double
    println(float)

    // type transformation
    println(double.toShort())
    println(double.toString())
}
```

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

### Nullable Variables

Kotlin tries to avoid null pointer exceptions that were invented by [this guy](https://en.wikipedia.org/wiki/Tony_Hoare).

```
// this is not compalible
fun main(args: Array<String>) {
    var nullable:String = null
    println(nullable)
}
```

Here is what is possible. 

```
package handbook

fun main(args: Array<String>) {
    // we can assign null to non type variable
    var n = null
    println(n)

    // or to typed variable but with ? after type declaration
    var nullable:String? = null
    println(nullable?.length)

    println(nullable!!.length)
}
```

Prints out: 

```
null
null
Exception in thread "main" kotlin.KotlinNullPointerException
	at handbook.NullableVariablesKt.main(NullableVariables.kt:12)
```

### Conditional Statements

```
package handbook

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

### Arrays

```
package handbook

fun main(args: Array<String>) {
    val array = arrayOf("1", "2", "3")
    println(array[0])
    array[0] = "100"
    println(array.joinToString { it })

    val mixedValues = arrayOf("string", 1, true)
    println(mixedValues.joinToString { it.toString() })

    val intArray = intArrayOf(1, 2, 3)
    println(intArray.joinToString { it.toString() })

    val string = "some string"
    println(string[0])

    val toBeConnected = intArrayOf(4, 5)
    val connected = intArray + toBeConnected
    println(connected.isEmpty())
    println(connected.size)
    println(connected.contains(1))
    println(connected.joinToString { it.toString() })
}
```

Here is the output: 

```
1
100, 2, 3
string, 1, true
1, 2, 3
s
false
5
true
1, 2, 3, 4, 5
```

### Lists

```

```



