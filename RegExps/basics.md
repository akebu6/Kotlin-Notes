# Basics
- A regular expression (regex or regexp for short) is a sequence of characters that describes a common pattern for a set of strings.
- Such patterns can be used to search, edit, and manipulate texts. 
- They can either check if a whole string or its substring matches the given pattern or replace the substring with another one.
- In regular expressions, the case of characters is relevant: park is not the same as PARK, i.e., they do not match.
- The real power of regular expressions comes when you start using special metacharacters called wildcards. 
- They allow you to define a pattern, so you can match strings that do not necessarily contain an identical sequence of characters.
- You can skip some characters in a string or match different characters in the same positions, or even repeat a character several times.
- regular expressions are case-sensitive.

### The dot character
- The dot character . matches any single character including letters, digits, and so on, except for the newline character, unless it is specified.

Example
<p>in the previous example, two words did not match the pattern because of one unsuitable character. Let's consider them and also add two additional words. Here is our new pattern .ARK with the dot character. It says: "there is any character followed by ARK".</p>
<img src="https://ucarecdn.com/4b680cb0-5ab1-4079-8a71-7eabecefc647/" width=200px height=200px />

### The question mark
- The question mark `?` is a special character that means “the preceding character or nothing".
- The question mark `?` signals that the character before it can occur once or zero times in a string to match the pattern. 
- The pattern `colou?r` will match the strings colour and color, but not the string coloor. 
- The word ARK does not match the .ARK pattern. But if we add ? right after the dot character .?ARK, the word ARK will match the new pattern since the first character is optional now.
