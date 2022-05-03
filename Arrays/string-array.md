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


## Changing the array contents
- No matter if you're using val or var, you can edit the values of the existing elements through their index:
```js
val southernCross = arrayOf("Acrux", "Gacrux", "Imai", "Mimosa")
var stars = arrayOf("Ginan", "Mu Crucis")
southernCross[1] = "star"
stars[1] = "star"

println(southernCross[1]) // star
println(stars[1]) // star
```
- However, there is a great difference between val and var when it comes to reassignment. When you have a var array, you can change it by adding new elements to it.
- Suppose we created an empty string array:
```
var southernCross = emptyArray<String>()
```
- Even if your array is not empty to begin with, you can still add elements in the same way:
```js
var southernCross = arrayOf("Acrux", "Gacrux", "Imai")
southernCross += "Mimosa"
println(southernCross.joinToString())  //  Acrux, Gacrux, Imai, Mimosa
```

### NOTE
- In Kotlin, the arrays are in a way unchangeable. 
- Even if the array is declared with var, it cannot really be edited.
- In both examples, the array southernCross was actually re-created. In fact, we literally deleted the array and created another one instead.
- So, we can add new elements if the array is declared as var. If you're using val, that is not possible:
```js
val southernCross = arrayOf("Acrux", "Gacrux", "Imai", "Mimosa")
southernCross += "Ginan" // will not compile
```
