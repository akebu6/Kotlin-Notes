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
