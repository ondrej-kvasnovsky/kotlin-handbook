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



