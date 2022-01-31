### toInt()
> when converting any number to an integer of 32 bits

<p> you can convert a larger number to a smaller one as follows
  
```js
val d: Double = 10.2
val n: Long = 15

val res1: Int = d.toInt() // 10
val res2: Int = n.toInt() // 15
```

### toLong()
> when converting a smaller number into a larger one

```js
val num: Int = 100
val bigNum: Long = num.toLong() // 100
```

<p> you can also convert a float value into an integer as follows</p>

```js
val d: Double = 12.5
val n: Long = d.toLong() // 12
```

### toDouble()
> when converting an integer to a double

<p>does not modify the value passed to it but creates a new value of type double</p>

```js
val num: Int = 100

val res: Double = sqrt(num.toDouble())
println(res) // 10.0
```

### toChar()
> when converting a number into a character

```js
val n1: Int = 125
val ch: Char = n1.toChar() // '}'
val n2: Int = ch.toInt()   // 125
```
