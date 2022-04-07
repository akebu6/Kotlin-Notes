# Functions without names
- To create a function that isn't bound to its name in Kotlin you can create an anonymous one or a lambda expression:
  + `fun(arguments): ReturnType { body }` – this one is commonly called an "anonymous function".
  + `{ arguments -> body }` – this one is commonly called a "lambda expression".
```js
fun(a: Int, b: Int): Int {
    return a * b
}

{ a: Int, b: Int -> a * b }
```
- types work just like they do for top-level functions discussed in previous topics.
- to add that if you want to declare a lambda without arguments, you do not need to write the "arrow symbols".
- hence a lambda without argument definition looks like this: { body }.
- using a function no known name; there are several ways to do this:
- for example, you can assign the function to a variable and then invoke it by invoking the variable:
```js
val mul1 = fun(a: Int, b: Int): Int {
    return a * b
}

val mul2 = { a: Int, b: Int -> a * b }

println(mul1(2, 3))  // prints "6"
println(mul2(2, 3))  // prints "6" too
```
- you can pass such a function as an argument or return such a function from another function.
- finally, you can place parentheses with desired arguments right after the function definition to invoke it in place.
- the process of creating these two functions is quite similar, but lambdas have a more concise and convenient syntax
- Therefore, almost always lambdas are used to create a function at runtime in real life.


## Lambdas and syntactic sugar
- There are ways to make the code more readable for human beings without changing the code logic. If there is such a way in a programming language and it relates to syntax, its name is syntactic sugar. 
- example
```js
fun isNotDot(c: Char): Boolean = c != '.'
val originalText = "I don't know... what to say..."
val textWithoutDots = originalText.filter(::isNotDot)
```
- rewritting it as a lambda
```js
val originalText = "I don't know... what to say..."
val textWithoutDots = originalText.filter({ c: Char -> c != '.' })
```
-  First of all, Kotlin infers types of many objects, and here specifying the c type isn't necessary:
```js
originalText.filter({ c -> c != '.' })
```
- Second, there are situations when the lambda is passed as the last argument. Kotlin provides a way to eliminate these bracket sequences ({ }), allowing to write the lambda outside the parentheses;
```js
originalText.filter() { c -> c != '.' }
```
- If the parentheses are left empty after this operation, you can remove them:
```js
originalText.filter { c -> c != '.' }
```
- Finally, when there is a single parameter in a lambda, there is an opportunity to skip it. The parameter is available under the `it` name. The final version of the code that removes dots is this:
```js
val originalText = "I don't know... what to say..."
val textWithoutDots = originalText.filter { it != '.' }
```

## Complex lambdas
- Sometimes, the code in a lambda isn't short enough to fit in one line, so you need to split the code into lines. In this case, the last line inside the lambda is treated as the lambda return value:
```js
val textWithoutSmallDigits = originalText.filter {
    val isNotDigit = !it.isDigit()
    val stringRepresentation = it.toString()

    isNotDigit || stringRepresentation.toInt() >= 5
}
```
- Also, a lambda can contain earlier returns. They must be written using the qualified return syntax.
- This means that after the return keyword the `@` symbol and the label name are written. The label name is usually the function name where the lambda was passed.
```js
val textWithoutSmallDigits = originalText.filter {
    if (!it.isDigit()) {
        return@filter true
    }
        
    it.toString().toInt() >= 5
}
```


## Capturing variables
