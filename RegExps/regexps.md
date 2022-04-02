## Creating a regular expression
- The first way is creating a String instance and then calling the method `toRegex()`, which will make a regex out of that string:
```js
val string = "cat" // creating the "cat" string
val regex = string.toRegex() // creating the "cat" regex
```
- Another way is calling the Regex constructor:
```js
val regex = Regex("cat") // creating a "cat" regex
```

## Simple matching
- The first method we will consider is matches(). It is used for finding a full match, that is, the whole string has to match the pattern.
- Signature: `fun String.matches(regex: String): Boolean`
```js
val regex = Regex("cat") // creating the "cat" regex
    
val stringCat = "cat"
val stringDog = "dog"
val stringCats = "cats"

println(stringCat.matches(regex))   // true
println(stringDog.matches(regex))   // false
println(stringCats.matches(regex))  // false
```
- As you can see in the example above, when our regex is just a sequence of simple characters, the result will be true only when the string matches the regex perfectly.

## The dot character
- The only character it cannot match is the newline character \n. Other control characters such as \b and \t will still match.
```js
val regex = Regex("cat.") // creating the "cat." regex

val stringCat = "cat."
val stringEmotionalCat = "cat!"
val stringCatWithSpace = "cat "
val stringCatN = "cat\n"

println(stringCat.matches(regex))   // true
println(stringEmotionalCat.matches(regex))   // true
println(stringCatWithSpace.matches(regex))  // true
println(stringCatN.matches(regex))  //false
```

## The question mark
- The question mark ? is a special character that denotes optionality. It means “the preceding character or nothing”.
```js
val regex = Regex("cats?") // creating the "cats?" regex

val stringCat = "cat"
val stringManyCats = "cats"

println(stringCat.matches(regex))   // true
println(stringManyCats.matches(regex))   // true
```
- You can also combine the dot character . and the question mark ? in one regex pattern. 
- This combination basically means that there can be any single character or no character at all:
```js
val regex = Regex("cat.?") // creating the "cat.?" regex

val stringCat = "cat"
val stringManyCats = "cats"
val stringEmotionalCat = "cat!"
val stringCot = "cot"

println(stringCat.matches(regex))   // true
println(stringManyCats.matches(regex))   // true
println(stringEmotionalCat.matches(regex))  // true
println(stringCot.matches(regex))   // false
```

## The escape character
- If part of the actual regex happens to be a special character, this can be managed with the escape character. 
- When you create strings with special characters, you can escape them using a double backslash \\:
```js
val regex = Regex("cats\\?") 

val stringCat = "cat"
val stringManyCats = "cats"
val stringEmotionalCats = "cats?"

println(stringCat.matches(regex))   // false
println(stringManyCats.matches(regex))   // false
println(stringEmotionalCats.matches(regex))  // true
```

