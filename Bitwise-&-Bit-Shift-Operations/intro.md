# Bitwise operators
> There are four bitwise operators: `inv()` **(bitwise NOT, inversion, complement)**, `or` **(bitwise OR)**, `and` **(bitwise AND)** and `xor` **(bitwise XOR)**. Each of these operators goes through all bits of both operands (numbers) one by one (i.e., bitwise) and produces a new number as a result.

+ `inv()` is a unary operator that inverses bits in the binary format of the number, turning every `0` into `1` and every `1` into `0`. It also changes the sign bit of the value.

+ `or` is a binary operator that performs bitwise OR: the result digit is `1` if at least one operand digit is `1`, otherwise, it is `0`.

+ `and` is a binary operator that performs bitwise AND: the result digit is `1` if both operand digits are `1`, otherwise, it is `0`.

+ `xor` is a binary operator that performs bitwise XOR: the result digit is `1` if exactly one operand is `1`, otherwise, it is `0`.

**NOTE:** The listed operators can be applied to both integer and boolean operands. If both operands are integers, then bitwise operations will be performed. If both operands are booleans, the corresponding logical operations are performed (except ~).

### Example
Let's assume we have two integer numbers: 15 and 10. The first number has a binary representation 1111, the second one is 1010. Note, we will ignore unimportant zeros in numbers for brevity. The example below illustrates the use of and, or, and xor operators:
```js
val first = 15  // binary format 1111
val second = 10 // binary format 1010

val bitwiseAnd = first and second // 1111 & 1010 = 1010, the result is 10
val bitwiseOr = first or second  // 1111 | 1010 = 1111, the result is 15
val bitwiseXor = first xor second // 1111 ^ 1010 = 0101, the result is 5
```
+ And here are two examples of inversion:
```js
val first = 35  // binary format 0..00100011
val second = -35 // binary format 1..11011101

val inverseFirst = first.inv() // ~ 0..00100011 = 1..11011100, the result is -36
val inverseSecond = second.inv()  // ~ 1..11011101 = 0..00100010, the result is 34
```
+ Why do we get the output `-36` in the first example? It's because the compiler works with 2's complement of numbers.

+ For any positive integer `n`, the inversion of n will be `-(n+1)`. So, the bitwise complement of `35` is `-36`.

+ The second case with the number `-35` is similar: the inversion of a negative number `-n` is `n-1`, so the result is `34`.

+ Why do we need these operations? For example, you can check if a number is divisible by 2 using `and`:
```js
val a = 5
val b = 4

val bitwiseAndA = a and 1 // 101 & 001 = 001, the result is 1 =>
// a is divided by 2 with a remainder equal to one

val bitwiseAndB = b and 1 // 100 & 001 = 000, the result is 0 => 
// b is divided by 2 without a remainder
```

# Bit-shift operators
> In addition to the bitwise operators, Kotlin also provides bit-shift operators that can be used to shift the bits of an integer number from one position to another.
> There are three bit-shift operators:

+ `shl` shifts the bit representation to the left by a certain number of specified bits, and zero bits are shifted into the low-order positions;

+ `shr` shifts the bit representation to the right by a certain number of specified bits. It fills the empty place with the value of the sign bit.

+ `ushr` is an unsigned bit-shift operator that shifts the bit pattern to the right by a certain number of specified bits. It is almost like shr, but the shifted values are filled up with zeros. The result of the ushr operator is always positive.
+ The following example illustrates how to perform fast multiplication and division by two using bit-shift operators:
```js
var value = 25   // binary: 0001 1001, decimal: 25

value = value shl 1 // binary: 0011 0010, decimal: 50
value = value shl 2 // binary: 1100 1000, decimal: 200

var anotherVal = 14   // binary: 1110, decimal: 14
anotherVal = anotherVal shr 1 // binary: 0111, decimal: 7
```
+ As you can see, the result of the left-shift operator `shl` is equivalent to multiplication by two, and the result of the right-shift operator is equivalent to division by two. Let's generalize: when we use signed bit-shift operators, we perform multiplication or division of the left operand by 2 in the power of the right operand.
```js
var newVal = 25

newVal = newVal shl 1 // 25 * 2^1 = 50
newVal = newVal shl 3 // 50 * 2^3 = 400
newVal = newVal shr 2 // 400 / 2^2 = 100
```
+ Another example shows the calculation of the middle of a positive integer interval.
```js
val left = 10
val right = 20

val mid = (left + right) shr 1 // this is 15!
```

+ Of course, this magic produces the same result as `(left + right) / 2`, but the bit-shift version is often considered a faster way to do that.

+ One more example illustrates the difference between `shr` and `ushr`:
```js
val number1 = 5
val number2 = -5

val shrNumber1 = number1 shr 1 // 0..0101 shr 1 = 0..0010, the result is 2
val ushrNumber1 = number1 ushr 1 // 0..0101 ushr 1 = 0..0010, the result is 2
val shrNumber2 = number2 shr 1 // 1..1011 shr 1 = 1..1101, the result is -3
val ushrNumber2 = number2 ushr 1 // 1..1011 ushr 1 = 01..1101, the result is 2147483645

```
+ `shr` shifts your bits to the right.

+ `ushr` also shifts to the right but fills up the leftmost bit with a zero.


+ As you can see, if you're doing bit shifts on positive values only, there is no difference between the operators. If you're also working with negative values, there is a big difference. In this case, `ushr` will flip the leftmost bit, so you'll get a positive value.

+ Since Kotlin 1.6, you can use `rotateLeft()` and `rotateRight()` for shifting a certain number of specified bits:
```js
val a = 4

val shiftRight = a.rotateRight(1) // 0..0100.rotateRight(1) = 0..0010, the result is 2
val shiftLeft = a.rotateLeft(1) // 0..0100.rotateLeft(1) = 0..1000, the result is 8
```

+ Also here can be the following example:
```js
val b = 3

val shiftLeft = a.rotateLeft(1) // 0..0011.rotateLeft(1) = 0..0110, the result is 6
val shiftRight = a.rotateRight(1) // 0..0011.rotateRight(1) = 1..0001, the result is -2147483647
```
+ `rotateRight()` changed our value in a strange way. What's the matter? It happens because int type represents a 32-bit integer value, so, when you shift your last bit by `rotateRight()`, bit on position 31 will be `1` and bit on position 0 will be 1.


# Precedence of bitwise and bit-shift operations
+ Like arithmetic operators, bitwise and bit-shift operators follow so-called precedence rules, which determine the order of performing and grouping operations in an expression. Operations with higher precedence are performed before those with lower precedence. Take a look at the list of operations in decreasing order of priority:

1. Parentheses ( `(expr)` );

2. Postfix increment/decrement `(expr++, expr--)`;

3. Unary plus/minus, prefix increment/decrement `(-expr, ++expr, --expr)`;

4. Multiplication, division, and modulus `( *, /, % )`;

5. Addition and subtraction `( +, - )`;

6. Assignment operations `( =, +=, -=, *=, /=, %=)`;

7. bitwise and bit-shift operators (`and, or, xor, shr, shl, ushr)`.

+ `and`, `or`, `xor`, `shr`, `shl`, `ushr` are not operators themselves, and their order of execution in an expression is from left to right.

**NOTE:** When operators have equal precedence, another rule is used to determine whether the evaluation should be performed from left to right or vice versa. It is called associativity.

+ All operators we have considered so far are evaluated from left to right, that is, in the way most familiar to you.
+ This means that in the following two expressions: `first or second and third` and `first or (second and third)`, operations will be executed in a different order and hence results may vary. If you go back to the example above `left + right shr 1` in a code snippet, you can see that here we don't need to use brackets, unlike in the case of its equivalent `(left + right) / 2`, because addition has higher precedence than all bit-shift operations. Remember these priorities when you combine arithmetic operations with the operations on bits.
