# Random Numbers
> A random number is a number that is almost impossible to predict

### Types of random numbers
- You can set some restrictions for your random number by choosing a specific type. 
- Everything you need for this purpose is located in the kotlin.random package
```js
import kotlin.random.Random

fun main() {
    // generates an integer value between Int.MIN_VALUE and Int.MAX_VALUE (inclusive)
    println( Random.nextInt() ) 
    // generates a long value between Long.MIN_VALUE and Long.MAX_VALUE (inclusive).
    println( Random.nextLong() ) 
    // generates a float value between 0 (inclusive) and 1.0 (exclusive)
    println( Random.nextFloat() )
    // generates a double value between 0 (inclusive) and 1.0 (exclusive)
    println( Random.nextDouble() )
    // same thing one more time
    println( Random.nextDouble() )
}
```

## Custom ranges
```js
// generates a non-negative integer value less than 100 
Random.nextInt(100) 
// generates an integer value between 1 (inclusive) and 100 (exclusive)
Random.nextInt(1, 100) 

// generates a non-negative long value less than 100
Random.nextLong(100)
// generates a long value between 1 (inclusive) and 100 (exclusive)
Random.nextLong(1, 100) 
 
// generates a non-negative double value less than 5.0 
Random.nextDouble(5.0) 
// generates a double value between 0.0 (inclusive) and 5.0 (exclusive)
Random.nextDouble(0.0, 5.0) 
```
- extFloat is the only function that doesn't allow specifying the custom range, in this case use the nextDouble()


## Pseudorandom numbers and seeding
- Every time the function is called, it gives us the next number in a predefined sequence. These numbers are called pseudorandom, and they are not completely unpredictable.
- We can calculate them all if we know the initial value and the algorithm of the sequence
- the initial value is called the **Seed**
- itself is never returned by a next[......] function but it defines all the subsequent numbers.
```js
val randomGenerator42 = Random(42) // the generator takes the seed
for (i in 0..5) {
    randomGenerator42.nextInt(100)
}
```
- In Kotlin 1.4, this code will always generate the same five numbers — 33, 40, 41, 2, 41, 32 — even on different machines
- In contrast, the default generator will give us a new sequence every time.
```js
// the same generator we use when we call Random.nextInt(), Random.nextFloat() etc.
val defaultGenerator = Random.Default 
for (i in 0..5) {                      
    defaultGenerator.nextInt(100)
}
```

