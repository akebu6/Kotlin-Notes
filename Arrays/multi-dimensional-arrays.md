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

