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
