# MutableList
+ MutableList is an ordered set of variables of the same type.
+ You can access the list items by their indexes.
+ A mutable list is a data structure of elements that can be accessed by index;
```js
val numbers = mutableListOf(10.8, 14.3, 13.5, 12.1, 9.7) 

println(numbers) // [10.8, 14.3, 13.5, 12.1, 9.7]
```
+ you create a mutable list by using the `mutableListOf()` function
```js 
//declaring a mutable list of integers
val mutableListA = mutableListOf<Int>(1, 2, 3, 4, 3)
println(mutableListA)
  
//declaring a mutable list of strings
val mutableListB = mutableListOf<String>("Kotlin", "JetBrains")
println(mutableListB)
  
//declaring an empty mutable list of booleans
val mutableListC = mutableListOf<Boolean>()
println("Empty list $mutableListC")
```
+ the `<>` are used to explicitly specify the type of the elements

### Reading list from input
+ To read a list of a certain size from the console, we first need to create a MutableList of some type with a known size.
+ then you can add the `readLine()` function making sure to convert it to the type you want
```js
val numbers = MutableList(5) { readLine()!!.toInt() } // on each line single numbers from 1 to 5
println(numbers) // [1, 2, 3, 4, 5]
```
+ reading user input on a single line
```js
// here we have an input string "1 2 3 4 5"

val numbers = readLine()!!.split(" ").map { it.toInt() }.toMutableList()
println(numbers) // [1, 2, 3, 4, 5]
```
+ you can also ignore line breaks and whitespaces using regular expressions
```js
val regex = "\\s+".toRegex()  // 1 or more whitespace character (space, tabs etc.)
val str = "1 2\t\t3  4\t5  6"
val nums = str.split(regex).map { it.toInt() }.toMutableList()
println(nums.joinToString()) // 1, 2, 3, 4, 5, 6
```

### MutableList size
```js
val list = MutableList(5) {0}

println(list) // [0, 0, 0, 0, 0]
```
+ use the `.size` to get the size of a mutable list

### Accessing elements
> you can access or reassign values of a mutable list by using the index
```js
// setting a value
list[index] = elem

// getting a vlue
val elem = list[index]
```
+ working with lists
```js
val numbers = mutableListOf(0, 0, 0) // numbers: 0, 0, 0

numbers[0] = 1 // numbers: 1, 0, 0
numbers[1] = 2 // numbers: 1, 2, 0
numbers[2] = numbers[0] + numbers[1] // numbers: 1, 2, 3

println(numbers[0]) // 1, the first element
println(numbers[2]) // 3, the last element
```
more functions to work with mutable lists
+`first()` // returns the first element in the list
+ `last()` // returns the last element in the list
+ `lastIndex()` // returns the index of the last element in the list
