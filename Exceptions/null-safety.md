# Safe Calls
```js
print(city?.address?.street?.building?.name)
```
- simply add a `?` time right after a nullable reference to avoid a NPE
- `?` will compare its value to null and return null if that reference is null. In other words, these two lines are equal:
```js
city?.address
(if (city == null) null else city.address)
```
- As you can see from the example above, it's even more convenient for chains. Here is an example of two safe calls in a row:
```js
city?.address?.street
((if (city == null) null else city.address)?.street)
```
