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
