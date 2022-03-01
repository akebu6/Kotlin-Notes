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

### Getting a part of a string
> `substring` function id used to get a part of a string
+ it accepts startIndex (inclusive) and lastIndex (exclusive) as arguments and returns a string that starts at the startIndex and ends right before the lastIndex.
```js
val greeting = "Hello"
println(greeting.substring(0, 3)) // "Hel"
println(greeting.substring(1, 3)) // "el"
println(greeting.substring(2))    // "llo"
println(greeting.substring(4, 5)) // "o"
```
+ The parameter lastIndex can be omitted; then you will get a substring from the startIndex element to the end of the original string.
+ The substring method is not the only way to get part of a string. You can also use the substringAfter and substringBefore functions:
```js
println(greeting.substringAfter('l'))  // "lo"
println(greeting.substringBefore('o')) // "Hell"
println(greeting.substringBefore('z')) // "Hello"
```
+ These functions accept delimiter as an argument and return a string before/after the first occurrence of a specified delimiter. If the string does not contain any occurrences of the delimiter argument, the function returns the whole string.
+ The functions substringBeforeLast and substringAfterLast have a logic similar to substringBefore and substringAfter but return a string before or after the last occurrence of the delimiter.
```js
println(greeting.substringAfterLast('l'))  // "o"
println(greeting.substringBeforeLast('l')) // "Hel"
```

### Replacing parts of a string
> The replace function replaces all occurrences of the first argument in the string with the second argument.
```js
val example = "Good morning..."
println(example.replace("morning", "bye")) // "Good bye..."
println(example.replace('.', '!'))         // "Good morning!!!"
```
+ the replace function returns a new string without changing the original string
+ if you only want to replace the first occurrence of a string use the `replaceFirst()`
```js
val example = "one one two three"
println(example.replaceFirst("one", "two")) // "two one two three"
```

### Changing the case
+ changing to lowercase
```js
val example = "UPPERCASE String"
println(example.lowercase()) // uppercase string
```
+ changing to uppercase
```js
val example = "Lowercase String"
println(example.uppercase()) // LOWERCASE STRING
```

## Processing Strings
### 1. Splitting the string
+ A string can be separated by delimiters to a list of strings.
+ To perform this, call the method split() , it divides a string into substrings by a separator
+ The method returns a List of all the substrings. 
+ The List is similar to MutableList, but you cannot reassign elements in the List and you cannot resize the List.
+ You can easily convert List to MutableList and vice versa with `toMutableList()` and `toList()` functions.
```js
val sentence = "a long text"
val wordsList: List<String> = sentence.split(" ") // ["a", "long", "text"]

val mutableWordList = sentence.split(" ").toMutableList() // MutableList ["a", "long", "text"]
```
OR
```js
val number = "+1-213-345-6789"
val parts = number.split("-") // ["+1", "213", "345", "6789"]
```
+ Choose your delimiter wisely, otherwise, you can receive some sentences that start with a space
+ You can choose any delimiter you prefer, even the combination of spaces and words:
```js
val text = "I'm gonna be a programmer"
val parts = text.split(" gonna be ") // ["I'm", "a programmer"]
```

### 2. Iterating over a string
```jsval scientistName = "Isaac Newton"

for (i in 0 until scientistName.length) {
    print("${scientistName[i]} ") // print the current character
}
```
+ you can iterate through a string:
```js
val str = "strings are not primitive types!"

var count = 0
for (ch in str) {
    if (Character.isWhitespace(ch))
        count++
}

println(count) // 4
```
+ Example of iterating through an array by indices:
```js
val rainbow = "ROYGCBV"

for (index in rainbow.indices){
    println("${index+1}: ${rainbow[index]}")
}
```
















