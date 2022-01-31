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
> available in version 1.4 and higher and is case senstive

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

## Logical Operators
### AND
binary operator and returns true if both operands equal to true and false otherwise
### NOT
unary operator and reverses the boolean value
### OR
similar to AND but only checks if one of the two operands is true and false otherwise
### XOR (exclusive OR)
returns true if the Boolean operands have different values and false otherwise
```js
val b1 = false xor false // false
val b2 = false xor true  // true
val b3 = true xor false  // true
val b4 = true xor true   // false
```

### Logical Operator Precedence
- ! for NOT
- xor for XOR
- && for AND
- || for OR
