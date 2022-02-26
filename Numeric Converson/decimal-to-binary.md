# Decimal To Binary Conversion

### Division Method
> the only thing that you need to be able to do is divide by 2 with a remainder. 
+ divide the number by 2,
+ get the quotient for the next iteration,
+ remember the remainder for the binary digit,
+ repeat the steps until the quotient is equal to 0,
+ write the remainders in the reverse order.

| Quotient | Remainder|
|--------- | -------- |
| 42 | 0 |
| 21 | 1 |
| 10 | 0 |
| 5 | 1 |
| 2 | 0 |
| 1 | 1 |

42 in base 2 is = 101010

### Subtraction Methode
+ make the list of all the powers of 2 that are smaller or equal to the number
+ subtract the biggest power from the number if it is possible
+ get the result for the next iteration
+ remember the 1 if you did the subtraction. If not, remember the 0
+ repeat the steps until the end of the list.
+ 42 in base 2 using subtraction method

| 32 | 16 | 8 | 4 | 2 | 1 | 
| -- | -- | -- | -- | -- | -- |
| 1 | 0 | 1 | 0 | 1 | 0 | 

