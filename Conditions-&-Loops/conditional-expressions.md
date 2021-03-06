## If Expressions
> in Kotlin if is an expression, not a statement. It checks the program and performs an action depending on the boolean
```js
// working with if statemnts
if (expression) {
    // body: do something
}
```

the single if statement's code block only executes provided that the expression evaluates to true and nothing happen if it evaluates to false

### if-else-cases
> includes an extension of the `else` clause
```js
if (expression) {    
    // do something
} else {
    // do something else
}
```
the `if` clause is evaluated first and if the condition is true then the code inside is executed, otherwise the code inside the else clause will be executed

### The if-else-if-cases
> contains many if-else-if cases and an else clause at the end
```js
if (expression0) {
    // do something
} else if (expression1) {
    // do something else 1
// ...
} else if (expressionN) {
    // do something else N
}
```

### Nested If's
> you can nest one if expression into the body of another one
```js
if (n % 2 == 0) {
    if (n % 3 == 0) {
        println("The number can be divided by 6")
    } else {
        println("The number can be divided by 2")
    }
} else {
    println("The number cannot be divided by 2")
}
```

### Condition is an expression
> As a regular expression, it can return a value (result) of computations. The result must be the last expression in a body.
```js
val max = if (a > b) {
    println("Choose a")
    a
} else {
    println("Choose b")
    b
}

// if all the bodies contain a single statement then you can ommit the curly brackets
val max = if (a > b) a else b
```

## When Expression
> can be used in place of if statements
```js
fun main(){
    val (var1, op, var2) = readLine()!!.split(" ")

    val a = var1.toInt()
    val b = var2.toInt()

    when (op) {
        "+" -> println(a + b)
        "-" -> println(a - b)
        "*" -> println(a * b)
        else -> println("Unknown operator")
    }
}
```
+ it can also be used with complex blocks
```js
when (op) {
    "+", "plus" -> {
        val sum = a + b
        println(sum)
    }
    "-", "minus" -> {
        val diff = a - b
        println(diff)
    }
    "*", "times" -> {
        val product = a * b
        println(product)
    }
    else -> println("Unknown operator")
}
```

### When as an expression
> when can also be used to return a result and in such a case, the else clause is required
```js
val result = when (op) {
    "+" -> a + b
    "-" -> a - b
    "*" -> a * b
    else -> "Unknown operator"
}
println(result)
```
+ without a declared variable
```js'println(when(op) {
    "+" -> a + b
    // ...
    else -> "Unknown operator"
})
```

### Branch conditions and ranges
```js
fun main(){
    val (var1, var2, var3) = readLine()!!.split(" ")

    val a = var1.toInt()
    val b = var2.toInt()
    val c = var3.toInt()

    println(when (c) {
        a + b -> "$c equals $a plus $b"
        a - b -> "$c equals $a minus $b"
        a * b -> "$c equals $a times $b"
        else -> "We do not know how to calculate $c"
    })
}
```

+ in ranges
```js
when (n) {
    0 -> println("n is zero")
    in 1..10 -> println("n is between 1 and 10 (inclusive)")
    in 25..30 -> println("n is between 25 and 30 (inclusive)")
    else -> println("n is outside a range")
}
```
+ rangs can also be combines
```js
in a..b, in c..d -> println("n belongs to a range")
```

### When without arguments
```js
fun main(){
    val n = readLine()!!.toInt()
    
    when {
        n == 0 -> println("n is zero")
        n in 100..200 -> println("n is between 100 and 200")
        n > 300 -> println("n is greater than 300")
        n < 0 -> println("n is negative")
        // else-branch is optional here
    }
}
```
