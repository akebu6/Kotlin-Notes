# BigInteger
> used for processing very large numbers (both positive and negative) and the size of a stored number is limited only by the available amount of memory.
+ it is immutable
+ BigInteger operations are slower than operations on built-in integer types.
+ it belongs to the java.math package.

### Creating objects of BigInteger
+ in order to use the BigInteger, you need to import the package
```js
import java.math.BigInteger
```
+ creating a value of type BigInteger
```js
// method one
val number = BigInteger("62957291795228763406253098")

// method two: passing long values
val number = BigInteger.valueOf(1000000000)
```
+ constants that belong to BigInteger and make it faster working with it
```js
val zero = BigInteger.ZERO // 0
val one = BigInteger.ONE   // 1
val ten = BigInteger.TEN   // 10
```
+ converting from standard numbers and strings to BigInteger:
```js
val numToBigInt = 1234.toBigInteger()
val strToBigInt = "1234".toBigInteger()
```

### Arithmetic operations
```js
val eleven = ten + one             // 10 + 1 = 11
val nine = ten - one               // 10 - 1 = 9
val oneHundredTen = ten * eleven   // 10 * 11 = 110
val twelve = oneHundredTen / nine  // integer division = 12
val two = oneHundredTen % nine     // remainder = 2
```
+ The unary minus operator returns a new BigInteger that has an opposite sign.
```js
val minusOne = -one // -1
```
+ it is possible to use increment (++) and decrement (--) operators in prefix and postfix forms.

### Functions of BigInteger
1. `divideAndRemainder` function
+ returns an array consisting of two numbers: the result of integer division and the remainder:
```js
val (result, remainder) = oneHundredTen.divideAndRemainder(nine) // 12 and 2
```
2. `abs` function
+ returns a new BigInteger whose value is the absolute value of this BigInteger:
```j
val number = BigInteger("-8")
println(number.abs()) // 8
```
3. `gcd` function
+ returns the greatest common divisor of two numbers.
```js
val eight = BigInteger.valueOf(8)
val six = BigInteger.valueOf(6)
println(eight.gcd(six)) // 2
```

















