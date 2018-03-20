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



