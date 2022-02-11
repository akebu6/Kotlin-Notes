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
