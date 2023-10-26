---
tags:
  - array
  - javascript
type: array method
---
# Basics
- The **`unshift()`** method of [[Array]] instances adds the specified elements to the beginning of an array and returns the new length of the array. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/unshift)
```javascript
const array1 = [1, 2, 3];

console.log(array1.unshift(4, 5));
// Expected output: 5

console.log(array1);
// Expected output: Array [4, 5, 1, 2, 3]
```
