# Singleton
- is a creational design pattern that allows you to keep only one instance of an object and provide global access to it.
- What does it mean and why you might have to use it? Well, it solves two problems:

**a.** Keeping only one instance of an object is useful when you want to control access to some shared resources. When you create one object of a class, if you use singleton pattern, you will always have that same object. In case you'll try to create another one, the code will return the first initiated object each time.

**b.** Providing global access point to allow all clients to use the initiated instances. When you address this problem, you also should squeeze all the code regarding the first problem in one class, to avoid it being scattered all over your code.

<img src="https://ucarecdn.com/fbe8dd71-892f-43c2-9471-d689d90cf806/" width="500px" height="300px" />


- Usually, to implement this pattern, we create a Singleton class that is connected to other parts of our application.
- It consists of Object constructor and getInstance() method.
- Through our constructor, we create instances when an application first needs it. 
- Then we check the presence of this instance with our method getInstance() and pass it to our application. 
- This helps us to avoid creating other instances.

### Example
```js
global instance

class Object is
  constructor of Object...

  method getInstance() is
    if (instance == null) then
      instance = new Object()
    return instance
```
- Instead of trying to maintain one instance of a class, you can maintain few instances. 
- All it takes is a bit of change to getInstance() method and keeping more than one instance. 
- But by doing this, you'll now work with different design pattern called multiton.


### Usage of singleton
- singleton should be used in situations when you need to keep only one instance of a class that is available to all clients
- Another time when this pattern should be implemented is when you need to isolate your instance and have only singleton class control over it.


### Problems
+ Singleton violates SRP (Single Responsibility Principle) by solving two problems at once. This could have a negative impact on your code because the solution for one problem can interfere with the solution for another.
+ Components of a program can have a bit too much information about each other.
+ It has a negative impact on a unit-testing and makes it harder.


### Object declaration
- This is a special class with an object keyword that creates a singleton. This keyword hides all complicated steps so you don't have to think about the ways to implement this pattern: just use object declaration.
```js
object PlayingField {

    fun getAllPlayers(): Array<Player> {
        /* ... */
    }
    
    fun isPlayerInGame(player: Player): Boolean {
        /* ... */
    }

}
```
- When you use object declaration, the constructor is not available because Kotlin does it itself. 
- To get an instance of our playing field, use PlayingField declaration. We can use it anywhere and it will return the same object every time.
```js
fun startNewGameTurn() {
    val players = PlayingField.getAllPlayers()
    if (players.length < 2) {
        return println("The game cannot be continued without players")
    }
    for (player in players) {
        nextPlayerTurn(player)
    }
}

fun nextPlayerTurn(player: Player) {
    if (!PlayingField.isPlayerInGame(player)) {
        return println("Current player lost. Next...")
    }
    /* Player actions here */
}
```

### Nested object
- Object declaration can be nested in a class declaration. 
- A nested class is created inside another class; it cannot be accessed without an outer class declaration.
```js
class OuterClass {  
   //outer class code  
    class NestedClass {  
      //nested class code  
    }  
} 
```
- nested object construction
```js
class Player(val id: Int) {
    object Properties {
        /* Default player speed in playing field – 7 cells per turn */
        val defaultSpeed = 7

        fun calcMovePenalty(cell: Int): Int {
            /* calc move speed penalty */
        }
    }
}

/* prints 7 */
println(Player.Properties.defaultSpeed)
```
- The object Properties has the scope Player, which means we can access it only through Player.Properties. That's how you can create a singleton connected to a special class.
- You can also use properties and functions from a nested object in the outer class. You can also use properties and functions from a nested object in the outer class.
```js
class Player(val id: Int) {
    object Properties {
        val defaultSpeed = 7
    }
    
    val superSpeed = Properties.defaultSpeed * 2 // 14
}
```
- You cannot use the properties and the functions of the outer class in the inner. 
- As you can see, it's similar to static in the other languages. Kotlin doesn't provide static members by default, but you may use nested objects if you need something related to the class.


### Idioms
```js
object Resource {
    val name = "Name"
}
```

### Companion object
- A companion object is a singleton attached to an outer class, and hence it cannot be accessed without accessing the outer class.
- It allows us to understand that the current object is somehow connected with the outer class.
```js
class Player(val id: Int) {
    companion object Properties {
        /* Default player speed in playing field - 7 cells per turn */
        val defaultSpeed = 7

        fun calcMovePenalty(cell: Int): Int {
            /* calc move speed penalty */
        }
    }
}

/* prints 7 */
println(Player.Properties.defaultSpeed)
```
- Until now, we've worked with a named companion object. However, unlike the case of a nested object, the name can be omitted.
```js
class Player(val id: Int) {
    companion object {
        /* Default player speed in playing field - 7 cells per turn */
        val defaultSpeed = 7

        fun calcMovePenalty(cell: Int): Int {
            /* calc move speed penalty */
        }
    }
}

/* prints 7 */
println(Player.defaultSpeed)
```
- accessing companion object
```js
/* prints 7 too */
println(Player.Companion.defaultSpeed)
```

### Companion object and outer class
- A companion is really closely associated with the outer class. You may freely use properties and functions from the companion object in the outer class.
```js
class Deck {
    companion object {
        val size = 10
        val height = 2
        fun volume(bottom: Int, height: Int) = bottom * height
    }

    val square = size * size             //100
    val volume = volume(square, height)  //200
}
```
- In this case, if you want to use a property from the companion, you must use the companion's name, or, if it wasn't named, the default name Companion:
```js
class Deck {
    companion object {
        val size = 10
    }
    val size = 2
    val square = Companion.size * Companion.size // 100
}
```

### Limitations of Companion Objects
- Only one companion object is available for each class.
- However, we can create one companion object and several nested objects:
```js
class Player(val id: Int) {
    companion object Properties {
        /* Default player speed in playing field - 7 cells per turn */
        val defaultSpeed = 7

        fun calcMovePenalty(cell: Int): Int {
            /* calc move speed penalty */
        }
    }

    /* creates a new instance of Player */
    object Factory {
        fun create(playerId: Int): Player {
            return Player(playerId)
        }
    }
}

/* prints 7 */
println(Player.Properties.defaultSpeed)

/* also prints 7 */
println(Player.defaultSpeed)

/* prints 13 */
println(Player.Factory.create(13).id)
```
- we cannot create a companion object inside another singleton (or a companion object) because that violates the global access principle.







