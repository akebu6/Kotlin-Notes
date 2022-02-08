### What is a String?
+ a sequence of zero or more characters enclosed by double quotes
+ it is immutable but the variable can be reassigned

### Length of a String
> use the .length to get the length of a string
```js 
val language = "Kotlin"
println(language.length) // returns 6
```
<p>
  <strong>Note:</strong> an empty string will return 0
</p>

### String Concatenation
> joining two or more strings together use the `+` operator

**Note:** `str1 + str2` does not produce the same result as `str2 + str1`
<p>order of how you join strings is important</p>

**Appending A Number to a String**
+ can be achieved only if the first variable or value is a string
+ the following code will not work
```js
// compiler will not complie this code
val stringPlusNum = 11 + "string"

// compiler will compile code
val stringPlusNum = "string" + 11 // returns string11
```
+ the number is first converted into a string before it is appended
+ you can also append a character to a string in the same manner as the character will be first converted into a string

### Repeating a String
> use the `repeat()` function instead of a loop. just state the number in the parameter
```js
println("Hello, World!".repeat(3))
```

#### Raw Strings
> can contain newlines and any other characters. You just need to wrap the text in triple quotes (""")
```js
"""
 This is us dealing with raw strings.
      
    Raw strings are pretty fun to work with.
       
    Use them when you want to add a long string
    with special characters.
       
    Now leaving raw strings
    Hope it now makes sense
    Triple the quotes and you're all done.
""".trimIndent() // removes the first and the last lines and trim indents
print(largeString)
```

### Accessing Characters
there are several ways of accessing single characters of a string:
+ using the array notation 
+ using the `first()` function (returns the first character)
+ using the `last()` function (returns the last character)
+ using the `lastIndez()` function (returns the last character's index)
```js
val greeting = "Hello"

println(greeting[1])
println(greeting.length - 3)
```

### Empty String
> use the `isEmpty()` function to check if a string is empty
```js
val emptyString = ""
println(emptyString.length == 0) //true
println(emptyString.isEmpty()) //true
```

### Comparing Strings
> use the `==` and the `!=` 
```js
val first = "first"
val second = "second"
var str = "first"

println(first == str)    // true
println(first == second) // false
println(first != second) // true
```
