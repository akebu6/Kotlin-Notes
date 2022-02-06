### String Template
> used when you want to incoporate variable values in a string for easy readability
```js
val name = "akebu"
val greeting + "Hello,"
println("$greeting $name") // prints Hello, akebu
```

## Templates for expressions
You can use string templates to put the result of an arbitrary expression in a string. To do that, include the entire expression in curly braces {...} after the dollar sign $. 
For example:
```js
// prints Kotlin has 6 letters in the name
val language = "Kotlin"
println("$language has ${language.length} letters in the name")
```
