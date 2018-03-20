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

### Maps

```
fun main(args: Array<String>) {
    val values1 = mapOf(Pair("John", 35), Pair("Jimmy", 25))
    println(values1)

    val values2 = mapOf(
            "John" to 35,
            "Jimmy" to 25
    )
    println(values2)

    println(values2.keys)
    println(values2.values)
    println(values2.entries)

    println(values1 == values2)

    val values3 = mutableMapOf("Josh" to 36)
    values3.putIfAbsent("Peter", 29)
    println(values3)
    
    println(values3.containsKey("Peter"))
    println(values3.getOrDefault("DoesNotExist", 0))
    
    values3.entries.forEach {
        println(it)
    }
}
```

Here is the output. 

```
{John=35, Jimmy=25}
{John=35, Jimmy=25}
[John, Jimmy]
[35, 25]
[John=35, Jimmy=25]
true
{Josh=36, Peter=29}
true
0
Josh=36
Peter=29
```



