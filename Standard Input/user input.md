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
``

### reading boolean values
> use the toBoolean() function
