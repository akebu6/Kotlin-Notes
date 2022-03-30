# Subtype and supertype
- subtype is a datatype that is related to another datatype (supertype) and shares common characteristics and rules of behavior with it.
- the rules of behavior of different subtypes may vary.
- supertype is a type that specifies the characteristics and rules of behavior that every subtype will follow.

### Type checking
```js
fun calculate(number: Number) {}

val number: Int = 1
calculate(number)
```

### Root type Any
- In Kotlin, type Any is a supertype for all types that don't support null.
```js
val message: Any = "Important message"
```
- you cannot assign a null value to the Any type
- Type Any is also a supertype for primitives such as Boolean:
```js
val isNull: Any = false
```

### Root type Any?
- If you want a variable to store any value including null, use type Any?.
```js
val number2: Number? = null // OK
```
- Any? is a supertype for types that can be either null or not.
- From this fact, it follows that type Any? is a supertype for type Any
- Non-null type is a subtype of its nullable equivalents, for example, type Number is a subtype of type Number?, and type Int is a subtype of type Int?.

### Unit
- Unit type can be used as the return type of a function that does not return any meaningful value
```js
fun logCurrentState(): Unit { 
    println("Current state of a program: $state")
}
```
- If you write a function and the return type is not specified, the compiler will treat it as a Unit function
- Unit is a subtype of Any. It can also be a nullable Unit?, which is a subtype of Any?.
- Unit? is a type that can be two values: the Unit value and null.


### Nothing
- At the very bottom of the Kotlin type hierarchy is the type Nothing.
- Nothing is a type that has no instances
```js
fun fail(): Nothing {
    throw Exception("Fail!")
}
```
- a throw is an expression of type Nothing.
- With the Nothing type, which can be a subtype of Any type, the type system allows any expression to fail while doing some work
```js
fun throwIfNull(name: String?) {
    if (name == null){
      throw Exception("Name can't be null!")
    }
}
```
- Like any other type, Nothing can be nullable with the help of a question mark suffix. Nothing? can only contain one value, null:

**Summary**
<p><img src="https://ucarecdn.com/d365efa2-c7bb-42cc-82ca-9be2ea2e6e90/" width=600px height=500px /></p>
