## Sets of characters
- Each set consists of multiple characters but corresponds to a single character in the string.
- Sets are enclosed in square brackets [].
- For example, the set "[abc]" means that a single character "a", "b", or "c" can match it.
```js
val regex = Regex("[bcr]at") // it matches strings "bat", "cat", "rat", but not "fat"

"rat".matches(regex) // true
"fat".matches(regex) // false
```
