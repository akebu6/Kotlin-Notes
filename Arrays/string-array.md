## Initialization
- Kotlin does not provide a special function to create an array of strings, so you need to use the function arrayOf
```js
val stringArray = arrayOf("array", "of", "strings")
```
- you can achieve strict behaviour by explicitly specifying the type as String
```js
val stringArray = arrayOf<String>("array", "of", "strings")
```
- You can also initialize an empty array to be filled with strings later. For this, you need the function emptyArray:
```js
val newEmptyArray = emptyArray<String>()
```
- Note that if you choose to use this function, you have to define the type of elements.
- The same actually applies to other types: an array created with emptyArray() can be filled with elements of any type that is defined.


##
