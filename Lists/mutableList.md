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

### Outputting a list
1. `joinToString()`
  + helps us output our list in different ways using the separator attribute. 
  + It takes elements from a mutable list in the order in which they are stored and presents them as a comma-delimited string line.
```js
val southernCross = mutableListOf("Acrux", "Gacrux", "Imai", "Mimosa")
println(southernCross.joinToString())   //  Acrux, Gacrux, Imai, Mimosa
```
  + You can also use another delimiter to separate elements
```js
println(southernCross.joinToString(" -> "))   //  Acrux -> Gacrux -> Imai -> Mimosa
```

### Working with multiple lists
+ mutable lists can be joined using the `+` operator
```js
val southernCross = mutableListOf("Acrux", "Gacrux", "Imai", "Mimosa")
val stars = mutableListOf("Ginan", "Mu Crucis")

val newList = southernCross + stars
println(newList.joinToString())    //  Acrux, Gacrux, Imai, Mimosa, Ginan, Mu Crucis
```
+ mutable lists can be compared using the `==` and the `!=` operators
```js
// returns true if both lists contain the same information and it's arranged in the same way
val firstList = mutableListOf("result", "is", "true")
val secondList = mutableListOf("result", "is", "true")
val thirdList = mutableListOf("result")

println(firstList == secondList)  //  true
println(firstList == thirdList)   //  false
println(secondList != thirdList)  //  true
```

### Changing the list contents
> The keywords val and var tell you how the value/reference of a variable should be handled but the contents can still be updated using the index
```js
val southernCross = mutableListOf("Acrux", "Gacrux", "Imai", "Mimosa")
var stars = mutableListOf("Ginan", "Mu Crucis")
southernCross[1] = "star"
stars[1] = "star"

println(southernCross[1]) // star
println(stars[1]) // star
```
+ you can use `add()`, `remove()`, `clear()` to add, remove or clear elements from a list
```js
  val southernCross = mutableListOf("Acrux", "Gacrux", "Imai", "Mimosa")
  val stars = mutableListOf("Ginan", "Mu Crucis")
  val names = mutableListOf("Jack", "John", "Katie")
  val food = mutableListOf("Bread", "Cheese", "Meat")
  val fruits = mutableListOf("Apple", "Banana", "Grape", "Mango")

  southernCross.removeAt(0)
  southernCross.remove("Mimosa")

  stars.add("New star")
  stars.add(0, "First star")

  names.clear()

  food.addAll(fruits)

  println(names) // []
  println(southernCross.joinToString()) // Gacrux, Imai
  println(stars.joinToString()) // First star, Ginan, Mu Crucis, New star
  println(food.joinToString()) // Bread, Cheese, Meat, Apple, Banana, Grape, Mango
```
+ `add(element)` and `add(index, element)` insert new items at any position in the list. If you don't specify the index, the item will be added to the end of the list.
+ `list1.addAll(list2)` adds all elements from list2 to the end of the list1.
+ `remove(element)` and `removeAt(index)` delete an item from the list. The former function deletes a single instance of the specified element from the list (it returns true if item was successfully removed, otherwise it returns false). The latter function deletes the element at the specified position and returns the element that has been removed.
+ `clear()` deletes all elements from the list.

Also, you can use += to add new elements to the list:
```js
val vowels = mutableListOf('a', 'o', 'i', 'e', 'u')
val intList1 = mutableListOf(1, 2, 3, 4, 5)
val intList2 = mutableListOf(5, 4, 3, 2, 1)
    
vowels += 'y'
intList1 += intList2

println(vowels)   // [a, o, i, e, u, y]
println(intList1) // [1, 2, 3, 4, 5, 5, 4, 3, 2, 1]
```

### Copy list content
Kotlin doesn't have any functions to copy existing lists. However, you can do it using the `toMutableList()` function
```js
val list = mutableListOf(1, 2, 3, 4, 5)
val copyList = list.toMutableList()

print(copyList) // [1, 2, 3, 4, 5]
```

### Other useful functions
+ `list.isEmpty()` and `list.isNotEmpty()` – check whether the list is empty.
+ `list.sublist(from, to)` – creates a smaller list (sublist), which includes items of the original list with the following indexes: from, from + 1, ..., to - 2, to - 1. The element with the index to is not included.
```js
val numbers = mutableListOf(1, 2, 3, 4, 5)
val sublist = mutableListOf<Int>()
if (numbers.isNotEmpty() && numbers.size >= 4) {
     sublist = numbers.subList(1, 4)
}

print(sublist) // [2, 3, 4]
```
+ `element in list` – checks if an element belongs to the list.
+ `list.indexOf(element)` – searches for the index of an element in the list. The result of this function is -1 if there is no such element in the list. Otherwise, when we access the list by the calculated index, we get the element.
```js
val numbers = mutableListOf(1, 2, 3, 4, 5)

if (5 in numbers) {
    println(numbers.indexOf(5)) // 4
}

print(numbers.indexOf(7)) // -1
```
+ `list.minOrNull()` and `list.maxOrNull()` – search for the minimum and maximum elements in the list.
+ `list.sum()` – returns the sum of the elements in the list.
+ `list.sorted()` and `list.sortedDescending()` – build a sorted list (ascending or descending) from the available list.
```js
val numbers = mutableListOf(1, 2, 3, 4, 5)
    
val vowels = mutableListOf('e', 'a', 'y', 'i', 'u', 'o')
    
println(numbers.minOrNull()) // 1
println(numbers.maxOrNull()) // 5
println(numbers.sum())      // 15
    
println(vowels.sorted()) // [a, e, i, o, u, y]
println(vowels.sortedDescending()) // [y, u, o, i, e, a]
```

### Mutable List Alternative
+ `sort()` similar to `sorted()`
+ `reverse()` similar to `reversed()`
+ `shuffle()` similar to `shuffled()`
