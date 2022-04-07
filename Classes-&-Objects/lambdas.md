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
