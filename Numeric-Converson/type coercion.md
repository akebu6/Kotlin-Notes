### Converting Int to Long
> will convert the smaller type to the larger type by default

```js
val num: Int = 100
val longNum: Long = 1000
val result = num + longNum // 1100, Long
```

<p>this is the same when working with long and double</p>

```js
val bigNum: Long = 100000
val doubleNum: Double = 0.0
val bigFraction = bigNum - doubleNum // 100000.0, Double
```

## NOTE
<p>1. when working with byte and short, the result produced will always be of type Int, unless you convert the result to either byte or short</p>

```js
val hundred: Short = 100
val five: Byte = 5
val zero = hundred % five // 0, Int
```

<p>2. Type coercion does not occur when a value is put into the variable. For example, val longValue: Long = 10.toInt() is incorrect, because 10 is Int and longValue requires Long type.</p>
