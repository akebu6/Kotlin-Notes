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
> 
