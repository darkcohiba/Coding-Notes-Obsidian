---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`substring()`** method of [[String]] values returns the part of this string from the start index up to and excluding the end index, or to the end of the string if no end index is supplied. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/substring)
```javascript
const str = 'Mozilla';

console.log(str.substring(1, 3));
// Expected output: "oz"

console.log(str.substring(2));
// Expected output: "zilla"
```
