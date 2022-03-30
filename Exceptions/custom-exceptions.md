# Throwing an exception
+ Throwing an exception without any parameters. This isn't a really useful case because there is no information about the error here.
```js
throw Exception()
```
+ Throwing an exception with a message.
```js
throw Exception("My error message")
```
+ Throwing an exception with a message and a cause, which usually is another exception.
```js
throw Exception("My error message", cause)
```
+ Throwing an exception with the cause parameter only.
```js
throw Exception(e)  // where e is another exception
```
+ Throwing a subtype of the exception object. In the following example, we throw NullPointerException with our custom message.
```js
throw NullPointerException("NPE at Alpha point")
```

# Creating custom Exceptions
- We can create our own exception classes as mere subclasses of the Exception class.
```js
class LessThanZero: Exception("Parameter less than zero")

class GreaterThanTen: Exception("Parameter greater than ten")


fun myFunction(par: Int) {
    if (par < 0) throw LessThanZero()
    else if (par > 10) throw GreaterThanTen()
    ...
    ...
}

fun main() {
    myFunction(-3)
}
```
+ Note that a custom exception can be a subclass of any preexistent exception subclass,
```js
class MyException: ArithmeticException("My message")
```
+ Also, if we want to be able to create subclasses of our custom exception, then it should be defined as open, 
```js
open class MyException: ArithmeticException("My message")
class MySubclassException: MyException()
```

### Catching custom Exceptions
- Custom exceptions are handled in exactly the same way as normal exceptions.
```js
class BetweenOneAndFive: Exception("Value between 1 and 5")
class BetweenSixAndTen: Exception("Value between 6 and 10")

fun myFunction() {
    val randomInteger = (1..10).shuffled().first()  // Get a random integer between 1 and 10
    if (randomInteger <= 5) throw BetweenOneAndFive()
    else throw BetweenSixAndTen()
}

fun main() {
    try {
        myFunction()
    } catch (e: BetweenOneAndFive) {
        println("BetweenOneAndFive was thrown")
    } catch (e: BetweenSixAndTen) {
        println("BetweenSixAndTen was thrown")
    }
}
```
- The try-catch statement catches the relevant exception and prints the appropriate message.

### Multiple constructors
- In the following example, we implement multiple constructors by using the keyword super.
- This calls the constructor of the base type. In order to use this method, the derived exception should not have any primary constructor. 
- For each constructor, the relevant base exception constructor is initialized (or delegated to the new constructor).
- The syntax for each secondary constructor is illustrated in the following example code.  
- The new constructor is followed by : and then by the super keyword with the appropriate parameters.  
```js
class MyCustomException: Exception {
    constructor() : super()  // No parameters
    constructor(message: String?) : super(message)  // Only the String parameter
    constructor(message: String?, cause: Throwable?) : super(message, cause) // Both parameters
    constructor(cause: Throwable?) : super(cause)  // Only the exception parameter
}
```
- Our new exception has 4 constructors and can be thrown in the following ways:
```js
throw MyCustomException()

throw MyCustomException("My exception message")

throw MyCustomException("My exception message", otherException)

throw MyCustomException(otherException)
```
+ In the following example, we create a custom exception derived from ArithmeticException. It has only 2 constructors:
```js
class MyArithmeticException: ArithmeticException {
    constructor() : super()
    constructor(message: String?) : super(message)
}
```

