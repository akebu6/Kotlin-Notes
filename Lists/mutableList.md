# MutableList
+ MutableList is an ordered set of variables of the same type.
+ You can access the list items by their indexes.
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
