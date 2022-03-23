# Member Functions
- implement a common behavior for the whole set of objects which belong to the same class.
```js
class MyClass {
    fun print() = println("Hello from print")
}
```
- Just like functions, member functions can take arguments and return a value of any type including the same type as the defined class.

### Calling member functions
- accessed using the dot operator
```js
val myObject = MyClassWithProperty(10)
myObject.printProperty()  // prints "10"
```
