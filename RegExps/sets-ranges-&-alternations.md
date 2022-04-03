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


### Ranges of characters
