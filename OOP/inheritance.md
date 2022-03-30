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
