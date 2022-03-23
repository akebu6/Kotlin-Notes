# Functions
> help in decomposing a program into smaller manageable units
- it is a sequence of instructions put together to operate
- functions can divide a program into small reusable pieces. It is called decomposition
```js
// basic structure of a function
fun functionName(p1: Type1, p2: Type2, ...): ReturnType {
    // body
    return result
}
```

A function has the following components:
- a name that follows the same rules and recommendations as a variable name;
- a list of parameters in parentheses. Each parameter has a name and a type separated by a colon :. All the parameters are separated by commas ,;
- the type of the return value (optional);
- a body that contains statements and expressions;
- the keyword return followed by the result (also optional).

```js
/**
 * The function returns its argument
 */
fun identity(a: Int): Int {
    return a
}

/**
 * The function returns the sum of two Ints
 */
fun sum(a: Int, b: Int): Int {
    return a + b
}

/**
 * The function just returns 3
 */
fun get3(): Int {
    return 3
}

fun main() {
    println(identity(1000)) // 1000
    println(sum(200, 300)) // 500    
    println(get3()) // 3
}
```

## Note
Since Kotlin 1.4, you can put a comma at the end of the parameters list. It can be very useful if you have a lot of arguments or use multi-line syntax, 
because you may easily copy-paste variables:
```js
fun sum(a: Int, b: Int, ): Int { // you can easily add some arguments
    // 
}

fun max(
    a: Int,
    b: Int,
): Int { // you can swap arguments without worrying about commas
    // 
}
```

### Return Type
there are two ways to declare a function that does not return anything
1. omit the return type part:
```js
/**
 * The function prints the values of a and b
 */
fun printAB(a: Int, b: Int) {
    println(a)
    println(b)
}
```

2. specify the special `Unit` type as the return type:
```js
/**
 * The function prints the sum of a and b
 */
fun printSum(a: Int, b: Int): Unit {
    println(a + b)
}
```

### Single-expression functions
> If a function returns a single expression, you can write it without curly braces:
```js
fun sum(a: Int, b: Int): Int = a + b

fun sayHello(): Unit = println("Hello")

fun isPositive(number: Int): Boolean = number > 0
```

### Functions with default arguments
- Kotlin can assign default values to function parameters in the function declaration. To invoke this function, you can omit the arguments with the default values, or you can invoke it in a usual way.
```js
fun printLine(line: String = "", end: String = "\n") = print("$line$end")
```
- We cannot pass the second argument without the first one. Kotlin cannot understand that we want to assign a value to the second parameter only.

### Named Arguments
- make code readable and clear in function calls
```js
// function
fun calcEndDayAmount(startAmount: Int, ticketPrice: Int, soldTickets: Int) =
        startAmount + ticketPrice * soldTickets
        
// function call
val amount = calcEndDayAmount(
    startAmount = 1000,
    ticketPrice = 10,
    soldTickets = 500
)
```
- You can change the order of arguments in a function call with the help of named arguments. All you need to do is to specify the names in any order you want
```js
val amount = calcEndDayAmount(
    ticketPrice = 10,
    soldTickets = 500,
    startAmount = 1000
)
```
- You can also call a function with named and regular (positional) arguments, as long as named arguments are placed after positional ones
```js
calcEndDayAmount(1000, ticketPrice = 10, soldTickets = 500)  // 6000
```
