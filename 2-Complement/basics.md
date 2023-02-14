# Getting the two's complement
> Two's complement is one's complement plus one

- In two's complement notation, a non-negative number is represented by its ordinary binary representation.
- The two's complement form of a negative number can be easily gotten from one's complement.
- Simply find N-bit's one's complement of a number and add 1 to it.


### Steps to Get 2's Complement
1. Find the binary form for the given decimal number.
2. Find the one's complement by inverting all bits of the binary form (replace 0 → 1, 1 → 0);
3. Add 1 to the one's complement to get the two's complement.


#### Example
Suppose, we would like to get the two's complement of the decimal number -5.

1. The binary form of 5 is `00000101` (using the 1 byte = 8 bits);
2. The one's complement form is `11111010`;
3. So, the two's complement is `11111011`;

**NOTE**
The result is a signed binary number representing the decimal value −5 in the two's-complement form. The first bit equal to 1 means that the presented value is negative.

One's complement can be converted from two's complement by subtracting 1.
