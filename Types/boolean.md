## Reading a boolean value

> only available in Kotlin 1.4 and later

```js
// returns true if input is "true" and false otherwise
 val b: Boolean =  readLine().toBoolean()

```

> when using Kotlin 1.3 or older

```js
val b: Boolean = readLine()!!.toBoolean()

```

#### toBooleanStrict()
> available in version 1.4 and higher
> case senstive

this is used to convert a string to a boolean value. It returns true if the string is equal to "true" and false if the string is "false" but will crash with the  `java.lang.IllegalArgumentException` error

```js
println("true".toBooleanStrict()) // returns true
println("True".toBooleanStrict()) // program crashes
println("false".toBooleanStrict()) // returns false
println("False".toBooleanStrict()) // program crashes
```

### toBooleanStrictOrNull()
> similar to toBooleanStrict() but returns a null value if the string is not equal to "true" or "false"

```js
println("true".toBooleanStrictOrNull()) // returns true  
println("True".toBooleanStrictOrNull()) // returns null  
println("false".toBooleanStrictOrNull()) // returns false 
println("False".toBooleanStrictOrNull()) // returns null
```
