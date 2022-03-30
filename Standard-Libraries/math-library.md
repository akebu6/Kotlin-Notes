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

## Power and exponential functions
+ `sqrt(x)` returns the square root of its argument (works with Float and Double types);
+ `x.pow(n)` returns the value of x raised to the power of n, where x can be Float or Double and n can be Int, Long, Float, or Double.
+ `exp(x)` returns the exponential function of x;
+ `ln(x)` returns the natural logarithm of x;
+ `log(x, base)` returns the logarithm of x to base.
```js
val sqrt = sqrt(2.0)      // 1.4142...
val square = 5.0.pow(2.0) // 25.0
val cube = 2.0.pow(3.0)   // 8.0


val e = E        // 2.718
val ln = ln(e)   // 1
val log = log(16.0, 4.0)  // 2
val logSum = ln(exp(2.0) * exp(3.0))  // 5
```

## Trigonometric functions
The following functions work with Float and Double types and accept angles in radians:
+ `sin(x)` returns the trigonometric sine of the given angle in radians;
+ `cos(x)` returns the trigonometric cosine of the given angle in radians;
+ `tan(x)` returns the trigonometric tangent of the given angle in radians.
+ the library provides the constant PI that is the ratio of the circumference of a circle to its diameter.
```js
val pi = PI // pi is 3.1415...

val sin = sin(pi / 2) // 1.0
val cos = cos(pi) // -1.0
val tan = tan(pi / 4) // 0.99999999... (an inaccurate result)
```
+ calculating the hypotunese
```js
val a = 3.toDouble()
val b = 4.toDouble()
val c = hypot(a, b) // c is 5.0, function works with Double or Float
```
+ for more math functions, refer to the following link
https://kotlinlang.org/api/latest/jvm/stdlib/kotlin.math/


## Rounding functions
> Rounding functions work with Float and Double types:

+ `floor(x)` returns the largest double value that is less than or equal to its argument and is equal to an integer;
+ `ceil(x)` returns the smallest double value that is greater than or equal to its argument and is equal to an integer;
+ `round(x)` returns the closest double value that is equal to an integer. Numbers like 3.5 or 4.5 are rounded to the nearest even integer. Also, you can use roundToInt() to round number and convert it to Int in one function!
```js
val floor = floor(3.78) // 3.0
val ceil = ceil(4.15)   // 5.0

val negativeFloor = floor(-3.78)  // -4.0
val negativeCeil = ceil(-4.15)    // -4.0

val roundDown = round(4.15)       // 4.0
val roundUp = (4.75).roundToInt() // 5, Int 

val roundDownToEven = round(2.5)  // 2.0
val roundUpToEven = round(3.5)    // 4.0
```


#### Example
```js
val size1 = 6
val size2 = 6
val angle = 60

val a = size1.toDouble()  // pow works with double
val b = size2.toDouble()
val radianAngle = angle * PI / 180 // cos requires an angle in radians

val c = sqrt(a.pow(2.0) + b.pow(2.0) - 2 * a * b * cos(radianAngle))
print(c) // 5.999999999999999, inaccurate, but the correct result
```
