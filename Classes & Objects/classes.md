## Classes
> A class is another important notion of OOP. A class describes a common structure of similar objects: their fields and methods. It may be considered a template or a blueprint for similar objects. An object is an individual instance of a class.

- In accordance with the principle of encapsulation mentioned above, any class should be considered as a blackbox, that is, the user of the class should see and use only the interface part of the class, namely, the list of declared properties and methods, and should not delve into the internal implementation.

### Declaring Classes
```js
// defining a class
class MyClass() {
  // some code
}
```
+ when a class has an empty body, curly braces can be omitted.

### Object creation
```js
val empty: MyClass = MyClass()

val empty = MyClass()
```

### Writing properties
+ Properties are pretty similar to variables and values.
+ If you want to assign a value to a property during runtime, you declare it as a var, otherwise, a val is your choice.
+ Also, any property has a strict type. It can be a standard type, like a number or a string, or a custom type. So a property type can be your own class and even the same class where the property is declared.
+ A property that just stores data must somehow receive an initial value

```js
class Patient {
    var name: String = "Unknown"
    var age: Int = 0
    var height: Double = 0.0
}
```

### Accessing properties
- first create an object
```js
var patient = Patient()
```
- to get those properties' values, type in a dot and the property name after the object name:


### Changing properties
```js
class Patient {
    var name: String = "Unknown"
    var age: Int = 0
    var height: Double = 0.0
}

fun main() {
    val john = Patient()
    john.name = "John"
    john.age = 30
    john.height = 180.0

    val alice = Patient()
    alice.name = "Alice"
    alice.age = 22
    alice.height = 165.0

    println("${john.name}: ${john.age} yrs, ${john.height} cm")
    println("${alice.name}: ${alice.age} yrs, ${alice.height} cm")
}
```

### Constructors
> are class members that initialize a new object of the class.

```js
val size = Size()
```
- Every class needs to have a constructor, so if it isn't explicitly defined, the compiler automatically generates a default constructor, which only creates an object and doesn't have any logic inside.



























