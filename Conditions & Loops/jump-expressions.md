# structural jump expressions
> allow you to jump out of a loop

## The Break Statement
> is used to terminate the nearest enclosing loop. 
```js
for (i in 1..10) {  
   // do something
   if (checkCondition){  
       break 
   }  
}
```

## The Continue Statement
> lets us proceed to the next iteration of the enclosing loop. In other words
```js
var result = ""
for (i in "hello world") {
    if (i == 'o') continue
    result += i
}
println(result)
```

### Inner loops and structural jump expressions
```js
for (i in 1..4) {
    for (j in 1..4) {
        if (j == 2) continue // you want to ignore j = 2
        if (i <= j) break    // you will print the string if i is greater than j
        println("i = $i, j = $j")
    }
    println("Finished to examine i = $i")
}
```

## Labels
> t's just an identifier with the @ sign at the end and help us terminate both inner and outer loops
```js
loop@ for (i in 1..10) {
    // do something
}
```
+ ow labels behave with jump expreassions
```js
loop@ for (i in 1..3) { 
    for (j in 1..3) {
        println("i = $i, j = $j")   
        if (j == 3) break@loop  
    }  
}
```
+ break with a label terminates the execution of the labeled loop.
+ labels withn the continue
```js
loop@ for (i in 1..3) {
    for (j in 1..3) {
        for (k in 1..3) {
            if (k == 2) continue@loop
            println("i = $i, j = $j, k = $k")
        }
    }
}
```

## When and structural jump expressions
```js
for (i in 1..10) {
    when (i) {
        3 -> continue
        6 -> break
        else -> println(i)
    }
}
```

## The Return Statement
> lets us return the result to the nearest enclosing function
```js
fun main() {
    for (i in 1..10) {
        for (j in 1..10) {
            println("i = $i, j = $j")
            if (j == 3) return
        }
    }
}
```

