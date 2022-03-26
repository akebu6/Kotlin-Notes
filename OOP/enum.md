# Enum
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

val rgb = Rainbow.RED
rgb.printFullInfo() // Color - Red, rgb - #FF0000
```

### Enum Properties
1. `name` allows you to get the name of Enum's instance, for example:
```js
val color: Rainbow = Rainbow.RED
println(color.name)
```

2. `ordinal` contains a position of Enum's instance, for example:
```js
val color: Rainbow = Rainbow.GREEN
println(color.ordinal)
```

3. `values()` returns an array of all instances of Enum. It might be helpful if you want to iterate through Enum instances. Now we can check if any specific color is part of the Rainbow or not:
```js
fun isRainbow(color: String) : Boolean {
    for (enum in Rainbow.values()) {
        if (color.toUpperCase() == enum.name) return true
    }
    return false
}
```

4. `valueOf()` returns an instance of Enum by its name with String type and case sensitivity:
```js
println(Rainbow.valueOf("RED"))
```
- If there isn't any appropriate instance of Enum then IllegalArgumentException will be thrown.
- If you want to extend your Enum but with a static context, then you need to wrap your method with companion object keywords
```js
enum class Rainbow(val color: String, val rgb: String) {
    RED("Red", "#FF0000"),
    ORANGE("Orange", "#FF7F00"),
    YELLOW("Yellow", "#FFFF00"),
    GREEN("Green", "#00FF00"),
    BLUE("Blue", "#0000FF"),
    INDIGO("Indigo", "#4B0082"),
    VIOLET("Violet", "#8B00FF"),
    NULL("", "");

    companion object {
        fun findByRgb(rgb: String): Rainbow {
            for (enum in Rainbow.values()) {
                if (rgb == enum.rgb) return enum
            }
            return NULL
        }
    }

    fun printFullInfo() {
        println("Color - $color, rgb - $rgb")
    }
}

println(Rainbow.findByRgb("#FF0001")) // NULL
```

