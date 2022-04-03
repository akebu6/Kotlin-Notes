## List of shorthands
+ `\d` is any digit, short for [0-9];
+ `\s` is a whitespace character (including tab and newline), short for [ \t\n\x0B\f\r];
+ `\w` is an alphanumeric character (letter or numeral), short for [a-zA-Z_0-9];
+ `\b` is a word boundary. his one is a bit trickier: it doesn't match any specific character but rather matches the boundary between an alphanumeric character and a non-alphanumeric character
  - (for example, a whitespace character) or a boundary of a string (its end or start). 
  - This way, "\ba" matches all words (sequences of alphanumeric characters) starting with "a", "a\b" matches all words ending with "a", and "\ba\b" matches all separate "a" characters preceded and followed by non-alphanumeric characters.

- There are also negative counterparts of these shorthands that are equivalent to the restrictive sets and match everything except for the characters mentioned above:
 + `\D` is a non-digit, short for `[^0-9]`;
 + `\S` is a non-whitespace character, short for `[^ \t\n\x0B\f\r]`;
 + `\W` is a non-alphanumeric character, short for `[^a-zA-Z_0-9]`.
 + `\B` is a non-word boundary. It matches the case opposite to that of the \b shorthand: it finds its match every time whenever there is no "gap" between alphanumeric characters. For example, "a\B" matches all words that start with "a".


#### Example
- Remember that in Kotlin we use an additional backslash \ character for escaping.
```js
val regex = "\\s\\w\\d\\s".toRegex()

" A5 ".matches(regex)   // true
" 33 ".matches(regex)   // true
"\tA4\t".matches(regex) // true because tabs are whitespace as well

"q18q".matches(regex) // false, 'q' is not a space
" AB ".matches(regex) // false, 'B' is not a digit
" -1 ".matches(regex) // false, '-' is not an alphanumeric character, but '1' is OK.
```
- another way to write shorthand is to use raw strings. You don't need to escape \ in this case:
```js
val regex = """\W\S\D\S\W""".toRegex()
" 9o9 ".matches(regex)   // true
"\nA 1 ".matches(regex)   // true
"\tAl4\t".matches(regex) // true

" \taa ".matches(regex) // false, '\t' is a space
"_BBB ".matches(regex) // false, '_' is an alphanumeric character
```
- Here's how boundary shorthands will work in Kotlin code:
```js
val startRegex = "\\bcat".toRegex() // matches the part of the word that starts with "cat"
val endRegex = "cat\\b".toRegex() // matches the part of the word that ends with "cat"
val wholeRegex = "\\bcat\\b".toRegex() // matches the whole word "cat"
```
- If you do not want to use shorthands, you can write the same regex as below:
```js
val regex = "[ \\t\\n\\x0B\\f\\r][a-zA-Z_0-9][0-9][ \\t\\n\\x0B\\f\\r]".toRegex()
```
- This regex, however, is long and not nearly as readable as the previous ones.
- It also has a lot of character repetitions. 
- You can use the predefined shorthands instead of commonly used sets and ranges to simplify your regexes and make them more readable.
