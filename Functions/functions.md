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
