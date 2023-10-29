---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`trim()`** method of [[String]] values removes whitespace from both ends of this string and returns a new string, without modifying the original string. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/trim)
```javascript
const greeting = '   Hello world!   ';

console.log(greeting);
// Expected output: "   Hello world!   ";

console.log(greeting.trim());
// Expected output: "Hello world!";

```
