## An array of arrays
- a multi-dimensional array is an array of arrays.
- in order to create a multidimensional array, we need to present an array as an element of another array.

## Creating 2-dimensional arrays
- creating a 2D array
```js
val array2D = arrayOf(
    arrayOf(0, 0, 0, 0),
    arrayOf(0, 0, 0, 0),
    arrayOf(0, 0, 0, 0)
)
```
- the main array that contains other arrays is called the main array.
- Note an interesting feature: nested arrays do not necessarily have to be the same size. In the example below, each new embedded array has different lengths:
```js
val array2D = arrayOf(
    arrayOf(0),
    arrayOf(1, 2),
    arrayOf(3, 4, 5))
```
- creating an empty 2D array
```js
val empty2DInt = arrayOf<Array<Int>>()
```

## Accessing elements
- The principle is exactly the same as for one-dimensional arrays. 
- Only now we have to write two indices: first the index of the element of the main array, and then the index of the nested array.
```js
val array2D = arrayOf(
    arrayOf(0, 1, 2),   // [0]
    arrayOf(3, 4, 5)    // [1]
)

println(array2D[0][0])	// 0
print(array2D[0][1])  // 1
print(array2D[0][2])  // 2
print(array2D[1][0])  // 3
print(array2D[1][1])  // 4
print(array2D[1][2])  // 5
```

## Creating 2D arrays of different types
- You also can clearly define the type of elements of nested arrays:
```js
val arrayOfString2D = arrayOf(
    arrayOf<String>("to", "be", "or"),
    arrayOf<String>("not", "to", "be")
)
```
- It is better to explicitly define the type of arrays using the arrayOf() constructor where necessary.
- In order to create nested arrays of primitives, you can use arrays of a certain type, as we did for one-dimensional arrays: IntArray, LongArray, DoubleArray, FloatArray, CharArray, ShortArray, ByteArray, BooleanArray.
- Example:
```js
val arrayOfChar2D = arrayOf(
    charArrayOf('A', 'R', 'R'),
    charArrayOf('A', 'Y', 'S')
)
```
- nested arrays be can of different types
```js
val arrayOfString2D = arrayOf(
    arrayOf("Practice", "makes", "perfect"),
    arrayOf(1, 2)
)
```

## Features of working with 2D arrays
- you can use the `joinToString()` function. For nested arrays, it will also work. Only now you must specify the index of the nested array that you want to convert to a string:
```js
val arrayString = arrayOf(
    arrayOf("A", "R", "R", "A", "Y")
)
print(arrayString[0].joinToString())    // A, R, R, A, Y
```
- In the case of multi-dimensional arrays, this will not always be convenient. In order to get all array contents in a single string, you can use the function `contentDeepToString()`:
```js
val arrayOfChar2D = arrayOf(
charArrayOf('k'),
charArrayOf('o', 't'),
charArrayOf('l', 'i', 'n'))

println(arrayOfChar2D.contentDeepToString())	// [[k], [o, t], [l, i, n]]
```

## Multi-dimensional arrays (>2)
- In each element of a two-dimensional array, you have another nested array.
- You can imagine it as a cube or a box: it has exactly three dimensions — length, width and height.
```js
val array3D = arrayOf(
    arrayOf(arrayOf(0,1), arrayOf(2,3)),
    arrayOf(arrayOf(4,5), arrayOf(6,7))
)

println(array3D.contentDeepToString())  // [[[0, 1], [2, 3]], [[4, 5], [6, 7]]]
```
- Accordingly, in order to refer to an element of such an array, we need three indices:
```js
println(array3D[0][0][1])   // 1
println(array3D[1][0][1])   // 5
println(array3D[1][1][1])   // 7
```
- You can create arrays of other dimensions by analogy — 4, 5, 6, and so on — as you need. Just remember that an element of a multidimensional array has as many indices as dimensions of that array.
