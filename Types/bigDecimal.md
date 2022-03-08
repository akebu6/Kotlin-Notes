# BigDecimal
> similar to BigInteger but works on floating-point types

### Creating objects of BigDecimal
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
