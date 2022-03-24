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

## Constructors
> are class members that initialize a new object of the class.

```js
val size = Size()
```
- Every class needs to have a constructor, so if it isn't explicitly defined, the compiler automatically generates a default constructor, which only creates an object and doesn't have any logic inside.

### Primary constructor
- it just initializes an instance of a class and its properties
- To define a primary constructor, you should put class initialization arguments in the parentheses after the class name.
```js
class Size(width: Int, height: Int) {
    val width: Int = width
    val height: Int = height
    val area: Int = width * height
}
```
- Kotlin's primary constructor allows you to omit the keyword.
- You can also define a constructor as follows:
```js
class Size constructor(width: Int, height: Int) {
    val width: Int = width
    val height: Int = height
    val area: Int = width * height
}
```

### Property declarations
- You can put simple property declarations inside the primary constructor.
- To declare a read-only property, put the keyword val in the parentheses before the argument name. For a mutable property, use the keyword var
```js
class Size(val width: Int, height: Int) {
    val height: Int = height
    val area: Int = width * height
}
```

### Default and named arguments
```js
class Size(var width: Int = 1, var height: Int = 1) {
    val area: Int = width * height
}
```
- When creating an object of a class with default values in the primary constructor, you can use the default values by omitting the arguments
- You can either provide values without property names or use named arguments when creating instances of a class
```js
val size1 = Size(3, 5) // width == 3, height == 5
val size2 = Size(width = 3, height = 5) // width == 3, height == 5
val size3 = Size(height = 5, width = 3) // width == 3, height == 5
```
- You can also omit some of the properties with default values when creating an object. Keep it in mind though, if you break the order of the arguments in the primary constructor, you should always use named arguments:
```js
val sizeWide = Size(10) // width == 10, height == 1
val sizeHigh = Size(height = 10) // width == 1, height == 10
```

### Single line classes
- If there are no other class members left except the ones in the primary constructor, we can omit empty curly braces. Imagine that the area property is missing in our example
```js
class Size(val width: Int, val height: Int)
```

### Init
- Primary constructors cannot contain any code: they only set the values of class properties based on the passed arguments
- Sometimes, we want to set some of our properties based on other properties' values or other sources of information. In such cases, we would use initializer blocks, which are prefixed with the keyword init:
```js
class Size(_width: Int, _height: Int) {
    var width: Int = 0
    var height: Int = 0

    init {
        width = if (_width >= 0) _width else {
            println("Error, the width should be a non-negative value")
            0
        }
        height = if (_height >= 0) _height else {
            println("Error, the height should be a non-negative value")
            0
        }
    }

```
- The keyword init signifies a block of code that serves as an extension of the primary constructor
- There may be several initializer blocks in the class body. In this case, property initializers and init blocks are executed in the order of their appearance:
```js
class Size(_width: Int, _height: Int) {
    // 1: the width property is initialized
    val width = _width

    // 2: 1st init block is executed
    init {
        println("First initializer block that prints the width $width")
    }

    // 3: the height property is initialized
    val height = _height

    // 4: 2nd init block is executed
    init {
        println("Second initializer block that prints the height $height")
    }

    // 5: the area property is initialized
    val area = width * height
}
```

### Nested Classes
```js
class Superhero {
    class MagicCloak {
    }

    class Hammer {
    }
}
```
- the top class is known as the outer class
- to access the elements, you need to create objects
```js
val cloak = Superhero.MagicCloak()
val hammer = Superhero.Hammer()
```

### Inner Classes
- A regular nested class cannot access members of its outer class. But a nested class marked as an inner class can.
```js
class Cat(val name: String) {
    inner class Bow(val color: String) {
        fun printColor() {
            println("The cat named $name has a $color bow.")
        }
    }
}
```

- You may encounter inner classes that have members with the same names as their outer classes. For example, both Cat and Bow may have the property color. How can you access the outer class members from the inner class in such cases? The qualified this expression will help! Write this@Cat.color in the inner class code and you will get the color of the outer class, while using color or this.color will always give you the color property of the current class
```js
class Cat(val name: String, val color: String) {
    inner class Bow(val color: String) {
        fun printColor() {
            println("The cat named $name is ${this@Cat.color} and has a $color bow.")
        }
    }
}
```
- An inner class can access all members of its outer class.
- To access the inner class, you need to instantiate the outer class first, as inner classes are associated with an instance of their enclosing class.
















