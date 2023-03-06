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

