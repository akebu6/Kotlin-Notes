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
