## A list of lists
> in order to create a multi-dimensional list, we need to present a list as an element of another list. Eventually, we get a multi-dimensional list.

### Creating 2-dimensional lists
> created by nesting lists inside one another and are represented in the form of a table or matrix
```js
val mutList2D = mutableListOf(
    mutableListOf<Int>(0, 0, 0, 0),
    mutableListOf<Int>(0, 0, 0, 0),
    mutableListOf<Int>(0, 0, 0, 0)
)
```
- the first list is called the main list
- netsed lists can have different sizes
```js
val mutList2D = mutableListOf(
    mutableListOf<Int>(0),
    mutableListOf<Int>(1, 2),
    mutableListOf<Int>(3, 4, 5)
)
```

### Accessing elements
> accessed the same way as 1D lists but these use two indices
```js
val mutList2D = mutableListOf(
    mutableListOf<Int>(0, 1, 2),   //[0]
    mutableListOf<Int>(3, 4, 5)    //[1]  
)

println(mutList2D[0][0])    // 0
```

### Creating 2D lists of different types
> can be a list of strings, characters, long, double and so forth
```js
// list of strings
val mutListOfString2D = mutableListOf(
    mutableListOf<String>("to", "be", "or"),
    mutableListOf<String>("not", "to", "be")
)

// list of characters
val mutListOfChar2D = mutableListOf(
    mutableListOf<Char>('A', 'R', 'R'),
    mutableListOf<Char>('A', 'Y', 'S')
)
```
- nested lists can also be of different types
```js
val mutListOfStringAndInt2D = mutableListOf(
    mutableListOf<String>("Practice", "makes", "perfect"),
    mutableListOf<Int>(1, 2)
)
```

### Features of working with 2D lists
```js
// working with joinToString
val mutListString = mutableListOf(
    mutableListOf<String>("A", "R", "R", "A", "Y")
)
print(mutListString[0].joinToString())    // A, R, R, A, Y
```
- not convinient for 2D list, instead just print the main list

### More than 2D Lists
- 3D lists are 2D lists with another list nested inside and needs 3 indices in order to get a particular element
```
val mutList3D = mutableListOf(
    mutableListOf(mutableListOf<Int>(0,1), mutableListOf<Int>(2,3)),
    mutableListOf(mutableListOf<Int>(4,5), mutableListOf<Int>(6,7))
)

println(mutList3D)  // [[[0, 1], [2, 3]], [[4, 5], [6, 7]]]
```




