## Working with Ranges
> helps when you want to work with particular ranges
```js
val within = c in a..b
```

```js
println(5 in 5..15)  // true
println(12 in 5..15) // true
println(15 in 5..15) // true
println(20 in 5..15) // false
```

#### excluding values from a range
```js
// subtract 1 from the range
val withinExclRight = c in a..b - 1 // a <= c && c < b
```

#### checking if a value is not in the range
```js
val notWithin = 100 !in 10..99 // true
```

> combining ranges using logical operators
```js
val within = c in 5..10 || c in 20..30 || c in 40..50 // true if c is within at least one range
```

> you can also assign a range to a variable
```js
val range = 100..200
println(300 in range) // false
```
