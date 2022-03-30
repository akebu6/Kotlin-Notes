# Data class
```js
data class Client(val name: String, val age: Int, val gender: String)
```
- This keyword will also provide toString() and copy() functions with default behavior. 
- We'll look at copy() a bit later, but right now you need to remember several rules here:
  1. You can only count on properties that are inside the constructor. For example, this modified Client class:
  ```js
  data class Client(val name: String, val age: Int, val gender: String) {
    var balance: Int = 0
  }
  ```
  2. You can override all those functions, except for copy():
  ```js
  data class Client(val name: String, val age: Int, val gender: String) {
    var balance: Int = 0

    override fun toString(): String {
        return "Client(name='$name', age=$age, gender='$gender', balance=$balance)"
    }

  }
  ```
  - Now balance field is involved in the toString() function.

   3. The primary constructor of a data class must have at least one parameter and all of those parameters must be val or var.

### Copy
```js
fun main() {
    val bob = Client("Bob", 29, "Male")
    val john = bob.copy(name = "John")
    println(bob)
    println(john)
}
```
- As you may see, we just used our copy() function, which will be provided automatically with the data keyword. And the output will be the following
```js
Client(name='Bob', age=29, gender='Male', balance=0)
Client(name='John', age=29, gender='Male', balance=0)
```
