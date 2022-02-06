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
