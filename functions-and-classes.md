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



