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


## Accessing elements
- you can access a certain element by its index:
```js
val stringArray = arrayOf("sagacity", "and", "bravery")
print(stringArray[2])   // bravery
```
- Similar to working with any type of array


## Outputting an array
- To see what we get as a result, and, for example, print a string array, use the familiar function `joinToString()`:
```js
val southernCross = arrayOf("Acrux", "Gacrux", "Imai", "Mimosa")
println(southernCross.joinToString())   //  Acrux, Gacrux, Imai, Mimosa
```
- Keep it in mind that `joinToString()` processes a single string of elements listed orderly and separated by a comma.


## Working with multiple arrays
+ String arrays can be added
```js
val southernCross = arrayOf("Acrux", "Gacrux", "Imai", "Mimosa")
val stars = arrayOf("Ginan", "Mu Crucis")

val newArray = southernCross + stars
println(newArray.joinToString())    //  Acrux, Gacrux, Imai, Mimosa, Ginan, Mu Crucis
```
+ String arrays can be compared
 - You cannot use the operators == and != to compare arrays because they simply do not compare their contents. 
 - With arrays, use the function contentEquals() instead:
```js
val firstArray = arrayOf("result", "is", "true")
val secondArray = arrayOf("result", "is", "true")
val thirdArray = arrayOf("result")

println(firstArray.contentEquals(secondArray))  //  true
println(firstArray.contentEquals(thirdArray))   //  false
```
- Note that it returns true only if the elements of the two arrays match completely and are arranged in the same order.


##
