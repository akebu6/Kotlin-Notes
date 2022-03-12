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
