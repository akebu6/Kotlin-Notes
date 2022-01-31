### toInt()
> when converting any number to an integer of 32 bits

<p> you can convert a larger number to a smaller one as follows
  
```js
val d: Double = 10.2
val n: Long = 15

val res1: Int = d.toInt() // 10
val res2: Int = n.toInt() // 15
```
  
<p><strong>type overflow</strong> occurs when the new type is too small to hold the initial value's type</p>

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

### toByte() and toShort()
> used when converting a number to an integer of size 8 bits or 16 bytes and should be avoided

<p>is not advisable and should not be used in Kotlin version 1.4 or higher</p>

```js
val floatNumber = 10f
val doubleNumber = 1.0

val shortNumber = floatNumber.toShort() // avoid this
val byteNumber = doubleNumber.toByte()  // avoid this

val shortNumber = floatNumber.toInt().toShort() // correct way
val byteNumber = doubleNumber.toInt().toByte()  // correct way
```

### toString()
> used when converting a number to it's string representation

```js
val n = 8     // Int
val d = 10.09 // Double
val c = '@'   // Char
val b = true  // Boolean

val s1 = n.toString() // "8"
val s2 = d.toString() // "10.09"
val s3 = c.toString() // "@"
val s4 = b.toString() // "true"
```

<p>you can also convert a string into a number as follows</p>

```js
val n = "8".toInt() // Int
val d = "10.09".toDouble() // Double
val b = "true".toBoolean() // Boolean
```

#### NOTE
<p>you can note convert a string into a character</p>

