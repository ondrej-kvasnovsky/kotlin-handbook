# Basics

This chapter describes basics about Kotlin programming language.

### Variables & Constants

```
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
fun main(args: Array<String>) {
    val list = listOf("hi", "there")
    // list.add("stranger") // not possible
    println(list)

    val arrayList = arrayListOf("well", "that", "is")
    arrayList.add("awesome")
    println(arrayList)

    // connect two lists
    println(list + arrayList)
    println(list + arrayList[0])
}
```

Here is the output:

```
[hi, there]
[well, that, is, awesome]
[hi, there, well, that, is, awesome]
[hi, there, well]
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

### Functions

```
fun main(args: Array<String>) {
    println(enhance("kotlin"))
}

fun enhance(text: String) : String {
    var result = ""
    for (letter in text) {
        result += letter.toUpperCase() + " "
    }
    return result
}
```

Here is the output.

```
K O T L I N
```

### Classes & Methods

```
class Car(val color: String) {
    private val otherColor: String

    init {
        println("object is being created")
        otherColor = color
    }

    var name = ""
    var running = false

    fun startEngine(remote: Boolean) {
        println("Starting (remote $remote): $name, $color vrum vruuum")
        running = true
    }

    fun isRunning() = running
}

fun main(args: Array<String>) {
    val car = Car("Metalic Gray")
    car.name = "Mustang"
    println(car.color)
    println(car.name)

    car.startEngine(remote = true)
    println(car.isRunning())
}
```

Here is the output.

```
object is being created
Metalic Gray
Mustang
Starting (remote true): Mustang, Metalic Gray vrum vruuum
true
```

### Inheritance & Interfaces

```
interface EarthCompatible {
    var fromInterface: String
    fun someMethod()
    fun defaultMethod() {
        println("Default method called")
    }
}

abstract class Creature : EarthCompatible {
    override var fromInterface: String = "Lets set value in abstract class"
    abstract fun isLiving()
}

open class Animal(open var name: String) : Creature() {
    override fun someMethod() {
        println("Some method called")
    }

    override fun isLiving() {
        println("checking life functions")
    }

    fun doIt() = "$name is doing it"

    open fun ableToOverride() = "I can be overridden"
}

open class Cat(override var name: String) : Animal(name) {
    override final fun ableToOverride(): String {
        return "And I was overridden"
    }
}

fun main(args: Array<String>) {
    val cat: Animal = Cat("Jimmy")
    println(cat.doIt())
    cat.isLiving()
    cat.someMethod()
    println(cat.fromInterface)
    println(cat.ableToOverride())
    cat.defaultMethod()
}
```

Here is the output.

```
Jimmy is doing it
checking life functions
Some method called
Lets set value in abstract class
And I was overridden
Default method called
```

### Getters and Setters

```
open class Person {
    private var reallyInternalVariable = 0 // only class
    protected var onlySubClassesCanAccessThis = 0 // only class and its sub classes
    internal val isInternal = true // can be accessed inside a module
    public val isPublic = true // this one is the default visiblity

    var age: Int = 0
        get() = field
        set(value) {
            if (value > 0) {
                field = value
            }
        }
}

fun main(args: Array<String>) {
    val p1 = Person()
    p1.age = 66
    p1.age = -100
    // p1.reallyInternalVariable = 1000 // not possible
    println(p1.age) // prints 66
    println(p1.isPublic)
}
```

### Data Classes

```
data class Human(val name: String, val age: Int)

fun main(args: Array<String>) {
    val h1 = Human("Jimmy", 24)
    val h2 = Human("Jimmy", 24)
    println(h1)
    println(h1.equals(h2))
    println(h1.hashCode())
    println(h2.hashCode())

    val h3 = h1.copy()
    println(h3)

    val (name, age) = h3
    println(name)
    println(age)

    val set = hashSetOf(h1, h2, h3)
    println(set)
}
```

Here is the output.

```
Human(name=Jimmy, age=24)
true
-2076084674
-2076084674
Human(name=Jimmy, age=24)
Jimmy
24
[Human(name=Jimmy, age=24)]
```

### Singleton

```
object Cache {
    val values = HashMap<String, String>()
    fun put(key: String, value: String): String {
        // do it here
        values.put(key, value)
    }

    fun get(key: String): String? {
        return values.get(key)
    }

    fun clear() {
        values.clear()
    }
}

fun main(args: Array<String>) {
    val cache = Cache
    cache.put("item1", "value1")
    println(cache.get("item1"))
}
```

### Enums

```
enum class Type {
    positive, negative
}

fun main(args: Array<String>) {
    println(Type.positive)
    println(Type.negative)
}
```

### Packages & Imports

We can import classes and also functions. We can create a function `someFunction` in a package.

```
package handbook.package1

fun someFunction(): String {
    return "some string..."
}
```

Then we can use that function in other class which is other package.

```
package handbook.package2

import handbook.package1.someFunction

fun main(args: Array<String>) {
    val someString = someFunction()
    println(someString)
}
```

### Generics

```
class Stack<T>(vararg items: T) {
    private val values = items.toMutableList()
    fun push(item: T) {
        values.add(item)
    }

    fun pop(): T? {
        if (values.isNotEmpty()) {
            val size = values.size
            return values.removeAt(size - 1)
        }
        return null
    }
}

fun <T> stackOf(vararg items: T): Stack<T> {
    return Stack(*items) // * is spread operator
}

fun main(args: Array<String>) {
    val stack = Stack(1, 2)
    stack.push(3)
    println(stack.pop())
    println(stack.pop())
    println(stack.pop())
    println(stack.pop())

    val stack2 = stackOf(1, 2, 3)
    println(stack2.pop())
    println(stack2.pop())
    println(stack2.pop())
}
```

Here is the output: 

```
3
2
1
null
3
2
1
```

### Input & Output





