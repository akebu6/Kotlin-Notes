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







