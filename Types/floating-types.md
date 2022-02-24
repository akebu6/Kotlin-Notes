# Double
> can store up to 14-16 significant numbers
```js
val one = 1.0
val negNumber = -1.75

val pi = 3.1415
```

# Floats
> can store up to 6-7 significant numbers
```js
val b: Float = 8.75f

val e = 2.71828f
```

### Reading Doubles & Floats
```js
val f = readln().toFloat()  // Float
val d = readln().toDouble() // Double
```

### Decimal separator
```js
import java.util.Locale

val floatNum = readln().format(Locale.US).toFloat()
```
