# Nullability
There are just a few ways how NPE may occur in Kotlin:

1. explicit call of throw NullPointerException() ;
2. !! syntax;
3. bad initializations, such as constructors and superclass constructors.

- every reference in Kotlin can be either nullable or not
```js
var name: String = null
```
- the code above will not complie as a non-null variable was declared. to fix this, use ? amking it a nullable variable
```js
var name: String? = null
```
- without a ? sign in the type you can't assign null to a variable.


### Accessing nullable variables
```js
if (name != null) {
    print(name.length)
}

// another way of accessing the name variable
print(name?.length)
```
- This `?.` pair of symbols is called a safe call in Kotlin. 
