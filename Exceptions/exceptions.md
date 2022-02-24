# Exception
> an exception is an unexpected and non-standard event, which occurs in different situations

## Reading an exception text
+ a stack trace and they show where the exception happened
+ a stack trace element contains something that is called a canonical name of a class

## Ordering of stack trace elements
+ the order of stack trace elements is vital.
A trace begins with the nearest place to the event and goes down to the first place of the functions call.


# Subtype and supertype
+ The subtype is a datatype that is related to another datatype (supertype) and inherits common characteristics and rules of behavior from it
+ Logically, a supertype is a type whose properties and methods specify the characteristics and rules of behavior that its subtypes will follow.
+ The type Throwable has two direct subtypes: Error and Exception.

### RuntimeException
+ is a rather special subtype of Exception
+ Subtypes of RuntimeException, such as ArithmeticException and NumberFormatException, can be thrown during the normal program execution.

1. ArithmeticException
- is the runtime exception that is thrown when the code attempts an illegal arithmetic operation. 
```js
val example = 2 / 0 // throws ArithmeticException
```

2. NumberFormatException
- It is thrown when a method expects to receive a number, but the actual input is something else.
```js
val string = "It's not a number"
val number = string.toInt() // throws NumberFormatException
```

3. IndexOutOfBoundsException
- occurs when you access some non-existent index
```js 
// StringIndexOutOfBoundsException

val sequence = "string"
println(sequence[10])   // throws StringIndexOutOfBoundsException
```

+ the `throw` keyword is used to create an exception
```js
fun calculateSpentMoney(total: Int, itemPrice: Int): Int {
    if (total < 0) {
        throw Exception("Total can't be negative")
    }
    if (itemPrice < 0) {
        throw Exception("Item price can't be negative")
    }
    if (itemPrice == 0) {
        return 0
    }
    val amountToBuy = total / itemPrice
    return amountToBuy * itemPrice
}
```


# The try-catch statement
```js
try {
    // code that may throw an exception
} catch (e: SomeException) {
    // code for handling the exception
}
```
+ The `try` block is used to wrap the code that may throw an exception
+ The catch block is a handler for the specified type of exception and all its subtypes. This block is executed when an exception of the corresponding type occurs in the try block.
```js
println("Before the try-catch block") // it will be printed
try {
    println("Inside the try block before an exception") // it will be printed
    println(2 / 0) // it throws ArithmeticException
    println("Inside the try block after the exception") // it won't be printed
} 
catch (e: ArithmeticException) {
    println("Division by zero!") // it will be printed
}

println("After the try-catch block") // it will be printed
```
### Getting info about exceptions
+ the `message` is used to get information about the exception caught by the catch block
```js
try {
    val d = (2 / 0).toDouble()
} 
catch (e: Exception) {
    println(e.message)
}
```
### Catching multiple exception
```js
try {
    // code that throws exceptions
}
catch (e: IOException) {
    // handling the IOException and its subtypes   
}
catch (e: Exception) {
    // handling the Exception and its subtypes
}
```
**Note:** 
The catch block with the base type has to be written below all the blocks with subtypes. In other words, more specialized handlers (like IOException) must be written before the more general ones (like Exception). Otherwise, the block with the subtype will be ignored.


# The finally block
- All the statements present in this block will always execute regardless of whether an exception occurs in the try block or not.
```js 
try {
    // code that may throw an exception
}
catch (e: Exception) {
    // exception handler
}
finally {
    // code is always executed
}
```
- you can also write a try and finally block without the catch block as follows:
```js
try {
    // code that may throw an exception
} 
finally {   
    // code will always be executed
}
```

### Try is an expression
```js
val number: Int = try { "abc".toInt() } catch (e: NumberFormatException) { 0 }
println(number) // 0
```
- The contents of the finally block do not affect the result of the expression:
```js
val number: Int = try { "2a".toInt() } catch (e: NumberFormatException) { 0 }
finally { println("Inside the finally block") }
println(number)
```
- Another useful technique is to rethrow exceptions to the caller. You need to add a way to handle exceptions in the code snippet where you call the function that can throw an exception. Here is an example of how to do this with an expression-style try:
```js
fun test() {
    val result = try {
        countSomething()
    } catch (e: ArithmeticException) {
        throw IllegalStateException(e) // do not forget to deal with it
    }

    // Working with result
}


try {
    test()
} catch (e: IllegalStateException) {
    ...
}
```















