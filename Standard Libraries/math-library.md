# Math Library
```js
import kotlin.math.*
```
- Most of these functions work only with Floating-point types, so you need to convert Int or Long types to use them

## Basic functions
+ `abs(n)` returns the absolute value of its argument
+ `min(a, b)` returns the smaller value of two arguments
+ `max(a, b)` returns the greater value of two arguments
```js
val abs = abs(-10)     // 10
val dAbs = abs(-10.33) // 10.33

val min = min(11, 81) // 11
val max = max(20, 30) // 30
```
