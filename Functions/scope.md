# Scope
- The scope of a variable is the syntactically-delimited area of code in which this variable or identifier, once declared, can be used in one way or another.
```js
var outer = 5
while (outer < 10) {
    var inner = 10
    inner *= 2
    print(inner)
    outer++
}  // prints 2020202020

// outside the while loop
print(inner)  // Unresolved reference: inner
```
- In general, program scopes are often layered. Some scopes are included in others, and all this forms a hierarchy.
- If scope B is nested in scope A, then identifiers from scope A can be used in scope B without additional declarations.
- If any identifiers are defined in such nested scope B, they are not visible in scope A.
- The called identifier is first searched in the current scope and then in scopes up the hierarchy.
- The top level of a Kotlin file is also a scope – it contains all the scopes within a file
- Top-level variables are declared outside the body of any class or function, and their scope is the whole file, while local variables are created when you define them, for example, in the body of a function.
- 
