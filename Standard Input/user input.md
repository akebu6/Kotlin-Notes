## Reading User Input

<p>use the readLine() function. However, you can use the readLine()!! to make sure that there is no empty line being passed to the complier</p>

```js
val line = readLine()!!
```

### reading numeric input
> use the toInt() and dot operator

```js
println("Print any number: ") 
val number = readLine()!!.toInt() 
print("You printed the number: ")
print(number)
```

<p>use the toLong() function to read larger numbers and toDouble() to read numbers with a decimal point</p>

```js
// using toLong()
println("Print any number: ") 
val number = readLine()!!.toLong() 
print("You printed the number: ")
print(number)

// using toDouble()
println("Print any number: ") 
val number = readLine()!!.toDouble() 
print("You printed the number: ")
print(number)
```

### reading boolean values
> use the toBoolean() function

```js
println("The earth is flat. Print true or false:")
val answer = readLine()!!.toBoolean()
print("The earth is flat: ")
print(answer)
```

### user input on one line
> use the `readLine()!!.split(" ")` function but the output will be on different lines and the user does not press ***Enter***

```js
val (a, b) = readLine()!!.split(" ")
println(a)
println(b)
```

<p>note: you can also read upto five values of input</p>

```js

```
