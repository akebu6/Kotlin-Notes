### Characters
> Each character is just a symbol enclosed in single quotes. 
The Char type represents letters (both uppercase and lowercase), digits, and other symbols.
```js
val lowerCaseLetter: Char = 'a'
val upperCaseLetter: Char = 'Q'
val number: Char = '1'
val space: Char = ' '
val dollar: Char = '$'
```

<p> characters can also be represented using their Unicode value as shown below</p>

```js
// the code starts with a \u
val ch = '\u0040' // it represents '@'
println(ch) // @
```

### Converting Char to Numbers & Vice Versa
```js
val ch = 'a'
println(ch.toInt())   // 97
val num = 97
println(num.toChar()) // a
```

### Reading Characters
> use the `.first()` function to read characters from the standard input
```js
val ch: Char = readLine()!!.first()
```

#### Note:
> some things you cannot do with characters
+ you cannot add a number to a symbol
+ you cannot multiply or divide characters
+ you cannot add two characters together
```js
// adding a number to a char
val ch = 'a'
val ch1 = 1 + ch // Error

// adding two characters together
val charsSum = 'a' + 'b' // Error
```

however, you can find the next or previous character using the `+` and `-` operators as shown below:
  
```js
val ch1 = 'b'
val ch2 = ch1 + 1 // 'c'
val ch3 = ch2 - 2 // 'a'
```
you can also use the `++` and `--` in their postfix and prefix to work with characters as well as the `=` combined with `+` or `-`
```js
var ch = 'A'

ch += 10
println(ch)   // 'K'
println(++ch) // 'L'
println(++ch) // 'M'
println(--ch) // 'L'
```

**note:** you can also use escape sequences by enclosing them in single quotes and a backslash.

### Processing Characters
+ `isDigit()` returns true if the given character represents a digit ('1', '2', etc); otherwise, false;
+ `isLetter()` returns true if the given character represents a letter ('a', 'B', 'm', etc); otherwise, false;
+ `isLetterOrDigit()` returns true if the given character represents a letter or a digit; otherwise, false;
+ `isWhitespace()` returns true if the given character represents a whitespace (' ', or '\t', or '\n'); otherwise, false;
+ `isUpperCase()` returns true if the given character is an uppercase character; otherwise, false;
+ `isLowerCase()` returns true if the given character is a lowercase character; otherwise, false;
+ `toUpperCase()` returns the uppercase form of the given character (before Kotlin 1.5; you shouldn't use it nowadays);
+ `uppercaseChar()` returns the uppercase form of the given character (since Kotlin 1.5);
+ `uppercase()` returns a String with the uppercase form of the given character (since Kotlin 1.5);
+ `toLowerCase()` returns the lowercase form of the given character (before Kotlin 1.5; you shouldn't use it nowadays);
+ `lowercaseChar()` returns the lowercase form of the given character (since Kotlin 1.5);
+ `lowercase()` returns a String with the lowercase form of the given character (since Kotlin 1.5).

