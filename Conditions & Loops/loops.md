## for loop
> used when you want to loop through a fixed range or items in an array

```js
// loops through from 10 all the way to 100
for (x in 10..100) println(x)
```
## in operator
> checks if the item is in the given list

**downTo**
> reverses the order of how items are printed, from to to bottom
```js
// will print from 100 all the way to 10
for (x in 100 downTo 10) println(x)
```

**.. operator**
> specifies a range
```js
for (x in 10..100) println(x)
```

**until**
> specifies a range to be printed but excludes the last value
```js
// will print from 10 all the way to 99
for (x in 10 until 100) println(x)
```

**step**
> steps through the list by a given value
```js
// will print x by 2
for (x in 10..100 step 2) println(x)
```

**Extra Notes**
- you can also use a for loop to return items in an array as shown below
```js
// iterates through the items in an array
for (items in myArray)
```
- you can also use a for loop to return the item and its index in an array
```js
// returning an item and its index 
for ((itemm index) in myArray)
```
