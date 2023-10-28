---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`startsWith()`** method of [[String]] values determines whether this string begins with the characters of a specified string, returning `true` or `false` as appropriate. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/startsWith)
```javascript
const str1 = 'Saturday night plans';

console.log(str1.startsWith('Sat'));
// Expected output: true

console.log(str1.startsWith('Sat', 3));
// Expected output: false

```
