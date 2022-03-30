#toString()
- The toString() function exists specifically to represent objects as strings.


### Default behavior
- The toString() function is defined for the type Any?.
- The point is that toString() for Any? returns the class name and memory location as a string.
```js
val nonString = 1.0

println(nonString.toString())   // 1.0
println(nonString)  // 1.0

/* The output is the same: println just implicitly called toString() for Double object */ 
```
- However, for most classes, by default, toString() still returns the name of the class and the address where the object is located in the memory.
- Usually, we want to get text information about objects in another way, so it makes sense to override toString() for our data type.


### Overriding toString()
```js
class BerryHolder(val weight: Int) {
    override fun toString(): String {
        return weight.toString()
    }
}
println(BerryHolder(10)) // 10
```
- another example
```js
class User(val id: Int, val login: String, val email: String) {
    override fun toString(): String {
            return "User{id=$id, login=$login, email=$email}"
    }
}
    
val user = User(1, "uncle_bob", "rmartin@objectmentor.com")
println(user) // User{id=1, login=uncle_bob, email=rmartin@objectmentor.com}
```

### Overriding toString(): Inheritance
- Another reason for the overriding the toString() method is working with superclasses, or parent classes
```js
open class User(val id: Int, val login: String, val email: String) {
    override fun toString(): String {
        return "User{id=$id, login=$login, email=$email}"
    }
}

class Author(id: Int, login: String, email: String, val books: String): User(id, login, email) {

}

val user = User(1, "marys01", "mary0101@gmail.com")
val author = Author(2, "srafael", "rsabatini@gmail.com", "Captain Blood: His Odyssey")

println(user)   // User{id=1, login=marys01, email=mary0101@gmail.com}
println(author) // User{id=2, login=srafael, email=rsabatini@gmail.com}
````
- The toString() method is not defined for the class Author. It may seem that the function will work by default. 
- However, since Author is inherited from the parent class User, the override for the parent class will be used.
```js
class Author(id: Int, login: String, email: String, val books: String): User(id, login, email) {
    override fun toString(): String {
        return "Author{id=$id, login=$login, email=$email}, books: $books"
    }
}

val user = User(1, "marys01", "mary0101@gmail.com")
val author = Author(2, "ohwilde", "wilde1854@mail.ie", "Someone’s portrait")
    
println(user)   // User{id=1, login=marys01, email=mary0101@gmail.com}
println(author) // Author{id=2, login=ohwilde, email=wilde1854@mail.ie}, books: Someone’s portrait
```


### Using the superclass definition
- It may be necessary to invoke the toString() parent implementation in the child class. It can be done with super, as you remember from inheritance:
```js
class Author(id: Int, login: String, email: String, val books: String): User(id, login, email) {
        override fun toString(): String {
            return "Author: ${super.toString()};\nBooks: $books"
        }
}
```

**Note**
- The toString() function is used to create a string view of non-string objects. It comes in handy in various situations, for example, in debugging.
