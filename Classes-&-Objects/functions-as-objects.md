# First-class citizen
- First-class citizens in programming are the objects that:
1. can be stored as variables,
2. can be returned by a function,
3. can be passed to a function as an argument,
4. don't depend on their name,
5. can be created at the program runtime (the time when the program is working).

- For example, an Int is a first-class citizen in Ko
- To clarify the fourth requirement, an Int with the ten name doesn't need to be 10. And vice versa: the 10 value doesn't need to be stored under the ten name
- You can create as many differently named variables for the same value as you need and the value won't change because of the name changing.
- In fact, functions are first-class citizens in the Kotlin language too.

## Function types
- Syntax of a function type: 
- `(parameters' types) -> return value type`
- In a function type there are arrow symbols (->) in the middle, also, there are parenthesized parameters' types split by commas on the left, and, finally, the return value type is written on the right.
- Thus the arrow seems to point from what the function takes to what it returns.

## Function references as objects
- Kotlin allows getting references to functions.
- To get a reference to a top-level function, we simply need to write double colon (::) before its name and we don't write parentheses and arguments after the name.
- Take a look at the example: ::sum gives us an object of the (Int, Int) -> Int type.
- Now we are ready to assign function references to values! We can create values this way:
```js
val sumObject = ::sum
```
- Don't confuse this assignment with saving function result to a value like this: `val sumResult = sum(1, 2)`
- The sumResult value has the Int type because the result of the invoked sum function is just a number.
- Meanwhile, the sumObject value is initialized with a reference to the sum function `(::sum)`, so it has the type of the sum function.
- We can also specify the type of the sumObject value explicitly:
```js
val sumObject: (Int, Int) -> Int = ::sum
```

## Functions returning other functions
- function that returns an object
 ```js
 fun getRealGrade(x: Double) = x
fun getGradeWithPenalty(x: Double) = x - 1

fun getScoringFunction(isCheater: Boolean): (Double) -> Double {
    if (isCheater) {
        return ::getGradeWithPenalty
    }

    return ::getRealGrade
}
```
- Here we have a real grade function, which returns its argument, and a grade with penalty function, which returns its argument minus one (in other words, the decrement of its argument).
- Also, we have another function which provides us one of the previous two functions.
- So if we do val wantedFunction = getScoringFunction(false), the wantedFunction value will contain a reference to a grade function for an honest student.
- Seeing the getScoringFunction function implementation, we can say that in this case the wantedFunction value contains a reference to the getRealGrade function.


## Function references as function parameters
- Also, you can create functions that take other functions as arguments. Let's create such function:
```js
fun applyAndSum(a: Int, b: Int, transformation: (Int) -> Int): Int {
    return transformation(a) + transformation(b)
}
```
- It receives two integers, transforms them using the received transformation function, and returns the sum of the transformed integers. We can declare some transformation functions:
```jsfun same(x: Int) = x
fun square(x: Int) = x * x
fun triple(x: Int) = 3 * x
```
- And then pass them to the former function:
```js
applyAndSum(1, 2, ::same)    // returns 3 = 1 + 2
applyAndSum(1, 2, ::square)  // returns 5 = 1 * 1 + 2 * 2
applyAndSum(1, 2, ::triple)  // returns 9 = 3 * 1 + 3 * 2
```

### Real-world usage
- The String type has the filter method to filter symbols. How does it know which symbols to remove from the string and which ones to leave in it?
- The answer is simple: this method takes a predicate as an argument and then uses it for internal computations.
- A predicate is a function that takes an argument and returns a Boolean result. 
- So in the filter method, the predicate says if the symbol should be left and has the `(Char) -> Boolean` type.
- Let's try to use this method. If we want to remove dots from a string, we declare this predicate:
```js
fun isNotDot(c: Char): Boolean = c != '.'
```
- Then we can do something like this:
```js
val originalText = "I don't know... what to say..."
val textWithoutDots = originalText.filter(::isNotDot)
```
- As a result, the textWithoutDots string is equal to "I don't know what to say".
