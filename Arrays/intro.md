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
- To create an array of a certain size, we need to write its type and pass it after the type name in round brackets (the constructor):
```js
val numbers = IntArray(5) // an array of 5 integer numbers
println(numbers.joinToString())

val doubles = DoubleArray(7) // an array of 7 doubles
println(doubles.joinToString())
```
- You cannot change the size of an array, but you can modify the elements.


### Reading array from input
- To read an array of a certain size from the console, we first need to create an array of some type with a known size.
- Inside the parentheses, we should place readln(), with the help of which we can read input from the console.
```js
val numbers = IntArray(5) { readln().toInt() } // on each line single numbers from 1 to 5
println(numbers.joinToString()) // 1, 2, 3, 4, 5
```
- If you want to read an array in a single line, use the following approach. 
```js
// here we have an input string "1 2 3 4 5"

val numbers = readln().split(" ").map { it.toInt() }.toTypedArray()
println(numbers.joinToString()) // 1, 2, 3, 4, 5
```
- There is also a way that allows you to ignore line breaks and extra spaces in the input string. You can do this with the help of regular expressions, which are often used in text searching and editing.
```js
val regex = "\\s+".toRegex()
val str = "1 2\t\t3  4\t5  6"
val nums = str.split(regex).map { it.toInt() }.toTypedArray()
println(nums.joinToString()) // 1, 2, 3, 4, 5, 6
```

### Array size
- An array always has a size, that is, the number of elements. To obtain it, we need to take the value of the size property. It is a number of the Int type.
```js
val numbers = intArrayOf(1, 2, 3, 4, 5)
println(numbers.size) // 5 
```

### Accessing elements
- You can change the values of array elements. Use the index to set a value in the array.
- Setting the value by the index:
```js
array[index] = elem
```
- Getting the value by the index:
```js
val elem = array[index]
```
- Example
```js
val numbers = IntArray(3) // numbers: 0, 0, 0

numbers[0] = 1 // numbers: 1, 0, 0
numbers[1] = 2 // numbers: 1, 2, 0
numbers[2] = numbers[0] + numbers[1] // numbers: 1, 2, 3

println(numbers[0]) // 1, the first element
println(numbers[2]) // 3, the last element
```
- Kotlin provides several convenient ways to access the first and the last elements of an array as well as to access the last index:
```ja
println(alphabet.first())   // 'a'
println(alphabet.last())    // 'd'
println(alphabet.lastIndex) // 3
```

### Comparing arrays
