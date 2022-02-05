### What is a String?
+ a sequence of zero or more characters enclosed by double quotes

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
