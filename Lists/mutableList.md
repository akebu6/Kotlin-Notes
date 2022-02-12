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
