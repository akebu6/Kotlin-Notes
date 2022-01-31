### toInt()

### toLong()
> when converting a smaller number into a larger one

```js
val num: Int = 100
val bigNum: Long = num.toLong() // 100
```

### toDouble()
> when converting an integer to a double
<p>does not modify the value passed to it but creates a new value of type double</p>

```js
val num: Int = 100

val res: Double = sqrt(num.toDouble())
println(res) // 10.0
```
