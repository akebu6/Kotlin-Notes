## Property getter
- getters are called when accessing a class' properties
```js
class Client {
    val name = "Unknown"
        get() {
            return field
        }
}

// or with omitted curly brackets and the body of the get() function

class Client {
    val name = "Unknown"
        get() = field
}
```
- Every property in Kotlin has its own backing field, which contains a property value that can be accessed with the special keyword field.


### Custom getter
- Another use for a custom getter is if you want to return something else.
```js
class Client {
    val name = "Unknown"
        get() {
            println("Somebody wants to know $field name")
            return field
        }
}

val client = Client()

val name = client.name // prints Somebody wants to know Unknown name
println(name)
```


## Property setter
```js
class Client {
    var name = "Unknown"
        set(value) {
            field = value
        }
}
```
- In this case, your setter will simply change the value of the name variable to the received value. This is the expected behavior and Kotlin generates this function for us, you don't need to write the setter yourself.


### Custom setter
- the setter is only called when you're trying to change the property, not when initializing it.
```js
class Client {
    var name = "Unknown"
        set(value) {
            println("The name is changing. Old value is $field. New value is $value.")
            field = value
        }
}

val client = Client()
client.name = "Ann"   // The name is changing. Old value is Unknown. New value is Ann.
```
- Another way to use a custom setter is if you wanted to assign a different value.
```js
class Client {
    var name = "Unknown"
    var age = 18
        set(value) {                      
            field = if (value < 0) {
                println("Age cannot be negative. Set to $defaultAge")
                defaultAge
            } else
                value
        }
    val defaultAge = 18
}

val client = Client()
client.age = -1      // Age cannot be negative. Set to 18.
println(client.age)  // 18
```

- You may implement both a setter and a getter for your property:
```js
class Client {
    var name = "Unknown"
        get() {
            println("Somebody wants to know $field name")
            return field
        }
        set(value) {
            println("The name is changing. Old value is $field. New value is $value.")
            field = value
        }
}
```

- If you want to add a getter and/or a setter to a property in a constructor, just "move" the property out
- Remember that in this case, you need to use another variable, not the property from the constructor:
```js
class Client(name: String, age: Int) {
    var fullName: String = name
        set(value) {
            println("The name is changing. Old value is $field. New value is $value.")
            field = value
        }
    var age: Int = age   // this is a new property, not a property from the constructor
        set(value) {
            println("The age is changing. Old value is $field. New value is $value.")
            field = value
        }
}
```
- Keep in mind that when initializing your property, the setter will not be called. This is also true for constructors since they initialize properties.
- You cannot use a setter for val variables
```js
class Passport(number: String) {
    var number = number
    set(value) {
        println("Passport number has changed.")
        field = value
    }
}

class Client {
    val passport = Passport("1234567")
}

val client = Client()
println(client.passport.number)       // 1234567
/*
client.passport = Passport("2345678") // This will not work.
*/
client.passport.number = "2345678"    // This will change the passport number
                                      // prints Passport number has changed
println(client.passport.number)       // 2345678
```










