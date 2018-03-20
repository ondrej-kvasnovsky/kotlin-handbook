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



