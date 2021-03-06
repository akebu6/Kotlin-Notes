## for loop
> used when you want to loop through a fixed range or items in an array

```js
// loops through from 10 all the way to 100
for (x in 10..100) println(x)
```
## in operator
> checks if the item is in the given list

**downTo**
> reverses the order of how items are printed, from to to bottom
```js
// will print from 100 all the way to 10
for (x in 100 downTo 10) println(x)
```

**.. operator**
> specifies a range
```js
for (x in 10..100) println(x)
```

**until**
> specifies a range to be printed but excludes the last value
```js
// will print from 10 all the way to 99
for (x in 10 until 100) println(x)
```

**step**
> steps through the list by a given value
```js
// will print x by 2
for (x in 10..100 step 2) println(x)
```

**Extra Notes**
- you can also use a for loop to return items in an array as shown below
```js
// iterates through the items in an array
for (items in myArray)
```
- you can also use a for loop to return the item and its index in an array
```js
// returning an item and its index 
for ((itemm index) in myArray)
```
- you can also loop through characters
```js
for (ch in 'a'..'c') {
    println(ch)
}
```
- iterating through strings
```js
val str = "Hello!"
for (ch in str) {
    println(ch)    
}
```
- nesting for loops
```js
fun main() {
    for (i in 2..10 step 2) {
        for (j in 2..10 step 2) {
            print(i * j)
            print('\t')  // print the product of i and j followed by one tab
        }
        println()
    }
}
```
- iterating through a MutableList
```js
for (element in mutList) {
    // body of loop
}
```
- iterating by indexes
> it is possible to access elements by their index directly from the loop. To do that, you must use the mutList.indices property, which represents a range of valid mutList indexes.
```js
fun main() {
    val daysOfWeek = mutableListOf("Sun", "Mon", "Tues", "Wed", "Thur", "Fri", "Sat")

    for (index in daysOfWeek.indices){
        println("$index: ${daysOfWeek[index]}")
    }
}
```
- iterating by range indexes
```js
fun main() {
    val daysOfWeek = mutableListOf("Sun", "Mon", "Tues", "Wed", "Thur", "Fri", "Sat")

    for (index in 1..5) {
        println("$index: ${daysOfWeek[index]}")
    }
}
```
**Note:**
> To use the last index of a mutable list in ranges, you need to access mutList.lastIndex. So, we can modify the code this way:
```js
for (index in 1 until daysOfWeek.lastIndex) {
    println("$index: ${daysOfWeek[index]}")
}
```
- using `step` and `downTo`
```js
fun main() {
    val daysOfWeek = mutableListOf("Sun", "Mon", "Tues", "Wed", "Thur", "Fri", "Sat")

    for (index in daysOfWeek.lastIndex downTo 0 step 2) {
        println("$index: ${daysOfWeek[index]}")
    }
}
```

### Reading MutableList elements
```js
fun main() {
    val size = readLine()!!.toInt()
    val mutList: MutableList<Int> = mutableListOf()
    for (i in 0 until size) {
        mutList.add(readLine()!!.toInt())
    }

    for (i in mutList.lastIndex downTo 0) {
        print("${mutList[i]} ")
    }
}
```

## Repeat Function
> used when you want to repeat a statement multiple times
```js
repeat(n) {
    // statements
}
```
`n` represents the number of times the loop will execute. if it is a neagtive number, the statements will be ignored

### Reading and processing data in a loop
you can read data from the standard input, declare variables and even perform calculations inside the repeat statement.
```js
fun main() {    
    val n = readLine()!!.toInt()
    var sum = 0
    
    repeat(n) {
        val next = readLine()!!.toInt()
        sum += next
    }
    
    println(sum)
}
```

## while loop
> is a pre-test loop
If the condition is true, the loop initiates the statements. They are repeated until the condition becomes false
```js
while (condition) {
    // body: do something repetitive
}
```

### Scanner
```js
import java.util.*

fun main() {
    val scanner = Scanner(System.`in`)
    while (scanner.hasNext()) {
        val next = scanner.next()
        println(next)
    }
}
```

### infinity loop
> loops that run forever until memory finishes
```js
while (true) {
    // body: do something indefinitely
}
```

## do..while loop
> post-test loop
If the condition is true, it repeats the loop until the condition becomes false
```js
do {
    // body: do something
} while (condition)
```
