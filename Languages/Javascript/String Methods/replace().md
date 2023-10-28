---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`replace()`** method of [[String]] values returns a new string with one, some, or all matches of a `pattern` replaced by a `replacement`. The `pattern` can be a string or a [`RegExp`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/RegExp), and the `replacement` can be a string or a function called for each match. If `pattern` is a string, only the first occurrence will be replaced. The original string is left unchanged. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/replace)
```javascript
let text = "Hello World!"; 

// Replace a simple string 
let newText = text.replace("World", "Universe"); 
console.log(newText); 
// "Hello Universe!" 

// Replace using a regular expression (case-insensitive) 
let caseInsensitive = text.replace(/hello/i, "Hi"); console.log(caseInsensitive); 
// "Hi World!" 

// Replace all occurrences of a letter 
let replaceAll = text.replace(/l/g, "x"); 
console.log(replaceAll); 
// "Hexxo Worxd!"
```
