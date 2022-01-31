## Reading a boolean value

> only available in Kotlin 1.4 and later

```js
// returns true if input is "true" and false otherwise
 val b: Boolean =  readLine().toBoolean()

```

> when using Kotlin 1.3 or older

```js
val b: Boolean = readLine()!!.toBoolean()

```

#### toBooleanStrict()
this is used to convert a string to a boolean value. It returns true if the string is equal to "true" and false if the string is "false" but will crash with the  `java.lang.IllegalArgumentException` error