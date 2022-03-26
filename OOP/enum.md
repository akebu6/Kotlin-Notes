# Emun
> represent a logical set of constants, and they make our code clearer and more readable.
- enum is a keyword, which allows us to create our own enumeration (the word that enum represents) just from a usual class:
```js
enum class Rainbow {
    RED, ORANGE, YELLOW, GREEN, BLUE, INDIGO, VIOLET
}
```
- According to Kotlin Coding Conventions, you can use either uppercase underscore-separated names (as usual Kotlin constants are RED_COLOR) or regular camel-humps names starting with an uppercase letter (RedColor).
- Initialising:
```js
enum class Rainbow(val color: String) {
    RED("Red"),
    ORANGE("Orange"),
    YELLOW("Yellow"),
    GREEN("Green"),
    BLUE("Blue"),
    INDIGO("Indigo"),
    VIOLET("Violet")
}

   val color = Rainbow.RED.color
```
- adding methods
```js
enum class Rainbow(val color: String, val rgb: String) {
    RED("Red", "#FF0000"),
    ORANGE("Orange", "#FF7F00"),
    YELLOW("Yellow", "#FFFF00"),
    GREEN("Green", "#00FF00"),
    BLUE("Blue", "#0000FF"),
    INDIGO("Indigo", "#4B0082"),
    VIOLET("Violet", "#8B00FF");

    fun printFullInfo() {
        println("Color - $color, rgb - $rgb")
    }
}
```
