# BigDecimal
> similar to BigInteger but works on floating-point types

### 1. Creating objects of BigDecimal
- import the library using the following statenent from the `java.math` package
```js
import java.math.BigDecimal
```
- The first way is creating it from the String object and specifying the desired number in double-quotes. And you can immediately convert the input string to BigDecimal:
```js
val firstBigDecimal = BigDecimal("10000000000000.5897654329")
val secondBigDecimal = BigDecimal(readln()) // Store the input number
```
- The second option is creating it from Double:
```js
val bigDecimal = BigDecimal(10000000000000.5897654329)
```
- You can convert numbers of other types to BigDecimal as follows:
```js
val number = 100000.50000
val bigDecimal = number.toBigDecimal()
```
- BigDecimal has several useful constants, just like BigInteger:
```js
val zero = BigDecimal.ZERO // 0
val one = BigDecimal.ONE   // 1
val ten = BigDecimal.TEN   // 10
```


### 2. Arithmetic operations
> BigDecimal is an immutable class.
- removes the problems that arise when dealing with floating point types.
- Binary and unary operations are available for BigDecimal. Using the binary operations
```js
val first = BigDecimal("0.2")
val second = BigDecimal("0.1")

val addition = first + second   // 0.3
val subtraction = first - second   // 0.1
val multiplication = first * second // 0.02
val division = first / second   // 2.0
val remainder = first % second // 0.0
```
- using the unary operation
```js
var first = BigDecimal("0.2")

// decrement
val decrement = --first //  -0.8
// increment
val increment = ++first //  0.2
// unary minus, turning to opposite sign
val reverse = -first  //  -0.2
// absolute value
val module = first.abs()  //  0.2
// raise to the power, works only with Int
val power = first.pow(3) 
```
- It is also possible to use increment (++) and decrement (--) operators in their postfix forms















