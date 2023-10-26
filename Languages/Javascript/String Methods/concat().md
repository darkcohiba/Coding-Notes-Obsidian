---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`concat()`** method of [[String]] values concatenates the string arguments to this string and returns a new string. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/concat)
```javascript
const str1 = 'Hello';
const str2 = 'World';

console.log(str1.concat(' ', str2));
// Expected output: "Hello World"

console.log(str2.concat(', ', str1));
// Expected output: "World, Hello"

```
