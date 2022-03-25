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











