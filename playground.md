# Playground

### Binary

```
package handbook.playground

fun main(args: Array<String>) {
    println(0b1110) // 14
    println(0b11111111 == 0xFF) // true
    println(0b11111111_00000000_00000000 == 0xFF0000) // true

    val containsRed = 0x110000 and 0xFF0000 != 0
    println(containsRed) // false

    println(0x00FFFF and 0xFF0000 != 0) // false
    println(0x00FFFF or 0xFF0000 != 0) // true
    println(0x00FFFF xor 0xFF0000 != 0) // true
    
    println(0b1011) // 1
    println(0b1011.inv() and 0x000001F) // 20
}
```

### Hexadecimal

```
package handbook.playground

fun main(args: Array<String>) {
    println(0xFF) // 31
    // R  G  B
    // FF FF FF
    println(0xFF0000) // red
    println(0x00FF00) // green
    println(0x0000FF) // blue

    println(0xFFFFFF) // white
    println(0x000000) // black
}
```



