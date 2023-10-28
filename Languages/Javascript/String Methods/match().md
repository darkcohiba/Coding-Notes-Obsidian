---
tags:
  - string
  - javascript
type: string method
---
# Basics
- The **`match()`** method of [[String]] values retrieves the result of matching this string against a [regular expression](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions). [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/match)
```javascript
const paragraph = 'The quick brown fox jumps over the lazy dog. It barked.';
// match capitals
const Capregex = /[A-Z]/g;
const found = paragraph.match(regex);

console.log(found);
// Expected output: Array ["T", "I"]
```
