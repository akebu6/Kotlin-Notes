## Sets of characters
- Each set consists of multiple characters but corresponds to a single character in the string.
- Sets are enclosed in square brackets [].
- For example, the set "[abc]" means that a single character "a", "b", or "c" can match it.
```js
val regex = Regex("[bcr]at") // it matches strings "bat", "cat", "rat", but not "fat"

"rat".matches(regex) // true
"fat".matches(regex) // false
```
- You can use as many sets as you want and combine them with regular characters. There are two sets in the following example:
```js
val pattern = "[ab]x[12]" // can match a or b followed by x followed by either 1 or 2
```
- This pattern can be successfully matched by the following strings:
```js
"ax1", "ax2", "bx1", "bx2"
```
- Meanwhile, the following strings do not match the pattern:
```js
"xa1", "aax1", "bx"
```
- the order of sets in regular expressions is important.
- On the other hand, the order of characters within the set does not matter.


## Ranges of characters
- we can specify a range designated by the hyphen symbol `-`.
- The character that precedes the hyphen denotes the starting point of the range; the character after the hyphen is the last character that falls into the range.
- We can put characters into a set as a range if they immediately follow each other in the ASCII/Unicode encoding table.
- This includes both alphabetically ordered letters and numeric values.
```js
val anyDigitPattern = "[0-9]" // matches any digit from 0 to 9
```
- The same works for letter ranges, such as `[a-z]` or `[A-Z]`
- These patterns are case-sensitive; for a case-insensitive match, we can write the following regex:
```js
val anyLetterPattern = "[a-zA-Z]" // matches any letter "a", "b", ..., "A", "B", ...
```
- Note that although the range [A-z] is technically valid, it includes additional symbols that are placed between uppercase and lowercase letters in the ASCII table.
- As you can see, you can easily put several ranges in one set and mix them with separate characters in any order:
```js
val anyLetterPattern = "[a-z!?.A-Z]" // matches any letter as well as "!", "?", and "."
```


## Excluding characters
