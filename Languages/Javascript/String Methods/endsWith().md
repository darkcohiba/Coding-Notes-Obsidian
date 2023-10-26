---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`endsWith()`** method of [[String]] values determines whether a string ends with the characters of this string, returning `true` or `false` as appropriate. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/endsWith)
```javascript
const str1 = 'Cats are the best!';

console.log(str1.endsWith('best!'));
// Expected output: true

console.log(str1.endsWith('best', 17));
// Expected output: true
// endsWith(searchString, endPosition)

const str2 = 'Is this a question?';

console.log(str2.endsWith('question'));
// Expected output: false

```
