# Inheritanve
- Inheritance is a relation between entities that we interpret as "is a" or "is a kind of" relation.
- In the case of programming methods and attributes, it means that a child entity has every feature of the parent entity.
- However, we can also change inherited features or define new ones for child classes.

### Open it
- all classes are closed for inheritance by default
- opening the class for inheritance
```js
open class Book(val pages: Int, val author: String)
```
- a full extended class
```js
open class Book(val pages: Int, val author: String, var cost: Float = 0F) {
    fun getFullInfo(): String {
        return "$pages pages, $author author, $$cost cost"
    }
}

class Comics(pages: Int, author: String, cost: Float) : Book(pages, author, cost)

fun main() {
    val spidermanBook = Comics(60, "The Universe", 8.99F)
    print(spidermanBook.getFullInfo())
}
// output: 60 pages, The Universe author, $8.99 cost
```

### Overriding
- open both the class and methods using the `open` keyword
```js
open class Transport(val cost: Int) {
    open fun getFullInfo(): String {
        return "$$cost cost"
    }

    fun getTax(): String {
        return "$${(cost * 0.25).roundToInt()} tax"
    }

```
- to oveeride the methods inside the class, use the `override` keyowrd
```ja
open class Ship(cost: Int, val color: String) : Transport(cost) {
    override fun getFullInfo(): String {
        return super.getFullInfo() + ", $color color"
    }
}
```
- By default any overridden function in Kotlin is open. 
- It means that you can override functions in sub-child classes too.
- Also, if you want to call a parent function, you can use super, as we did it in the example above. Two more things:
 1. if you forget about override keyword, the compiler will warn you because there cannot be two functions getFullInfo() with the same parameters.
 2. You also cannot override the getTax() function because it's not open.
```js
fun main() {
    val transport = Transport(1000)
    val ship = Ship(2000, "marine")
    println(transport.getFullInfo())
    println(ship.getFullInfo())
}
```
