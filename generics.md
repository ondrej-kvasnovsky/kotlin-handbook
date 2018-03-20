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

### 



