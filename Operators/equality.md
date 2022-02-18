## Strutural Equality
> when two or more varibales have the same inner state
+ you can check for equality using the `==` operator
+ you can also check for inequality using the `!=` operator

## Referential equality
> `===` checks whether the two or more variables point to the same object
```js
val blueBox = Box(3)
val azureBox = blueBox 
val cyanBox = Box(3)
println(blueBox == azureBox)  // true
println(blueBox === azureBox) // true, azureBox points to the same object
println(blueBox == cyanBox)   // true
println(blueBox === cyanBox)  // false, cyanBox points to another object
```
+ you can also check for referential inequality by using the `!==` operator
+ you also check for equality of immutable objects
```js
var two = 2
var anotherTwo = 2
println(two === anotherTwo) // true
```
