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
