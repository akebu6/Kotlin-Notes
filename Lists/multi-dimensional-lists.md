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
