---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`charAt()`** method of [[String]] values returns a new string consisting of the single UTF-16 code unit at the given index. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/charAt)
```javascript
const sentence = 'The quick brown fox jumps over the lazy dog.';

const index = 4;

console.log(`The character at index ${index} is ${sentence.charAt(index)}`);
// Expected output: "The character at index 4 is q"
```
