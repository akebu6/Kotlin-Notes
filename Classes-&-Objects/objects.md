# Working with Objects
> Objects are complex structures that can store some data and do something
+ it is a part of memory that stores some sort of information.
+ objects are made up of states, properties and member functions/methods

### Copying by reference
If you create a variable and assign an object to it, another variable can point to the same object as well.
```js
val msg1 = "Hi"
val msg2 = msg1
```
use the `=` to copy a reference of one object to another

**NOTE:**
+ An object can be either mutable or immutable.
+ If the object is immutable, you cannot change it, but you can use another object and assign this new object to the same variable. When you reassign the variable, it will point to a new object and other variables will still point to the old object. 
+ Mutable objects on the other hand can be changed and the object will now point to a different variable
+ String, Int, Char, Boolean are all immutable objects

