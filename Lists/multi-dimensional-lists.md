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
