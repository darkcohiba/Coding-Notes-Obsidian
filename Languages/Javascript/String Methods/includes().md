---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`includes()`** method of [[String]] values performs a case-sensitive search to determine whether a given string may be found within this string, returning `true` or `false` as appropriate. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/includes)
```javascript
const sentence = 'The quick brown fox jumps over the lazy dog.';

const word = 'fox';

console.log(`The word "${word}" ${sentence.includes(word) ? 'is' : 'is not'} in the sentence`);
// Expected output: "The word "fox" is in the sentence"
```
