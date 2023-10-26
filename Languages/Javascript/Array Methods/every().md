---
tags:
  - array
  - javascript
type: array method
---

# Basics
- The **`every()`** method of [[Array]] instances tests whether all elements in the array pass the test implemented by the provided function. It returns a Boolean value. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/every)
```javascript
const isBelowThreshold = (currentValue) => currentValue < 40;

const array1 = [1, 30, 39, 29, 10, 13];

console.log(array1.every(isBelowThreshold));
// Expected output: true
```
