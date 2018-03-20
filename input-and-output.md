# Input & Output

### Reading from Console

We are going to create a game where user is supposed to guess a number between 1 and 100.

```
package handbook.io

import java.util.*

fun main(args: Array<String>) {
    val number = Random().nextInt(100) + 1
    var input: String?
    var guess = -1
    while (guess != number) {
        print("Guess a number between 1 and 100: ")
        input = readLine()
        if (input != null && !input.isNullOrEmpty()) {
            guess = input.toInt()
        }

        if (guess < number) {
            println("Too low")
        } else if (guess > number) {
            println("Too high")
        } else {
            println("You won!")
        }
    }
}
```

Here is the program output with some user inputs. 

```
Guess a number between 1 and 100: 50
Too low
Guess a number between 1 and 100: 75
Too low
Guess a number between 1 and 100: 90
Too high
Guess a number between 1 and 100: 85
Too high
Guess a number between 1 and 100: 80
Too low
Guess a number between 1 and 100: 81
You won!
```

### Reading File

```
package handbook.io

import java.io.File

fun main(args: Array<String>) {
    File("src/main/resources/handbook/io/file.txt").forEachLine {
        println(it)
    }
}
```



