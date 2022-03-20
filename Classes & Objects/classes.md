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
