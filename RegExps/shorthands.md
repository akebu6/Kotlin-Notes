## List of shorthands
+ `\d` is any digit, short for [0-9];
+ `\s` is a whitespace character (including tab and newline), short for [ \t\n\x0B\f\r];
+ `\w` is an alphanumeric character (letter or numeral), short for [a-zA-Z_0-9];
+ `\b` is a word boundary. his one is a bit trickier: it doesn't match any specific character but rather matches the boundary between an alphanumeric character and a non-alphanumeric character
  - (for example, a whitespace character) or a boundary of a string (its end or start). 
  - This way, "\ba" matches all words (sequences of alphanumeric characters) starting with "a", "a\b" matches all words ending with "a", and "\ba\b" matches all separate "a" characters preceded and followed by non-alphanumeric characters.
