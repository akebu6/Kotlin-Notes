# Safe Calls
```js
print(city?.address?.street?.building?.name)
```
- simply add a `?` time right after a nullable reference to avoid a NPE
- `?` will compare its value to null and return null if that reference is null. In other words, these two lines are equal:
```js
city?.address
(if (city == null) null else city.address)
```
- As you can see from the example above, it's even more convenient for chains. Here is an example of two safe calls in a row:
```js
city?.address?.street
((if (city == null) null else city.address)?.street)
```

### Elvis Operator
```js
var name: String? = "Kotlin"
val length: Int? = name?.length
print(length ?: 0)
```
- The Elvis operator works like this: if the left-hand side of the expression is not null (name?.length), return it; otherwise, the right-hand side (0) is to return. You can also use return and throw expressions in the right part:
```js
val length: Int = name?.length
    ?: throw Exception("The name is null")
```

### The !! Operator
- There is an easy way to invoke an NPE: the !! operator. The code won't crash only if you're a 100% sure that your variable won't be null:
```js
var name: String? = "Kotlin"
print(name!!.length)
```
- This operator is used to stop the program when null is met.


note:
can be used in place of readln to avoid an NPE
```js
readlnOrNull() ?: error("No lines read")
```
