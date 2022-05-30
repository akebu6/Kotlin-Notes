## Writing files with writeText()
- to create a File(pathName: String) object, and use the writeText(text: String) function which sets the text content of a file
```js
val myFile = File("MyFile.txt") //file name must be indicated in parentheses 
myFile.writeText("It is awfully hard work doing nothing!")
```
- Mission accomplished: the text is in the file! You can see it in the current project directory where it was saved by default. 
- Notice, if you just create a File object, you will not create a file, it's just an object.
- Suppose we didn't write the file in the current directory but elsewhere. In that case, simply indicate the path to it like this:
```js
val myFile = File("D://Users/myFile.txt")
myFile.writeText("It is awfully hard work doing nothing!")
```
**Note**
- If the file has access restrictions or has already been opened in another process, `AccessDeniedException` is thrown.
- Last but not least, let’s talk about code style: the file name should be put into a separate string variable. You can also put the text into a variable. 
```js
val fileName = "myFile.txt"
val textToFile = "If we learn to process our code carefully, we’ll grow as programmers."
File(fileName).writeText(textToFile)
```

### Formatting and processing
