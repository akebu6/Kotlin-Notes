# Intro
- Arrays are useful when you need to process multiple values of the same type.
- You can save and process them together in an array as a single unit.
- It is convenient if you don't know how many elements the program will process during its runtime.
- You may consider an array as a collection of elements of one type. All elements are stored in the memory sequentially.
- The collection provides one name for all elements. 
- Once an array is created, it cannot be changed. 
- However, you can modify a stored element at any time.

### Creating an array with specified elements
- To create an array of a specified type, we need to invoke a special function and pass all elements to store them together:
 + intArrayOf creates IntArray
 + charArrayOf creates CharArray;
 + doubleArrayOf creates DoubleArray;
```js
val numbers = intArrayOf(1, 2, 3, 4, 5) // It stores 5 elements of the Int type
println(numbers.joinToString()) // 1, 2, 3, 4, 5

val characters = charArrayOf('K', 't', 'l') // It stores 3 elements of the Char type
println(characters.joinToString()) // K, t, l

val doubles = doubleArrayOf(1.25, 0.17, 0.4) // It stores 3 elements of the Double type
println(doubles.joinToString()) // 1.15, 0.17, 0.4

// output
1, 2, 3, 4, 5
K, t, l
1.25, 0.17, 0.4
```
- The `joinToString()` function converts an array into a string.
- When you initialize an array (or anything else) with a sequence of arguments, you can add a trailing comma. 
- It can be useful if you want to add or change some values.


### Creating an array of a specified size
