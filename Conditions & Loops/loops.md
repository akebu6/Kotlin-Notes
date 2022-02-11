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
